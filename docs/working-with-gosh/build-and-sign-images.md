---
description: BuildKit frontend for GOSH
---

# Build and Sign Images

With the Help of a custom [Buildkit](https://github.com/tonlabs/gosh/tree/main/buildkit), you can build your Docker images directly from GOSH, and sign them so they can be verified by the GOSH docker extension.

Instead of a dockerfile, this Buildkit uses a special [goshfile](build-and-sign-images.md#2.-write-goshfile.yaml-this-specification-is-a-work-in-progress-and-subject-to-change) to ensure code is taken from GOSH.

## How to build from GOSH

#### 1. Setup environment variables with your wallet

```
export WALLET=...
export WALLET_PUBLIC=...
export WALLET_SECRET=...
```

You received these when creating your account in [GOSH Web](gosh-web.md) or [Docker Extension](docker-extension.md).

#### 2. Create `goshfile.yaml` (this specification is a work in progress and subject to change)

```
# syntax=teamgosh/goshfile

apiVersion: 1
image: bash:latest
steps:
  - name: print date
    run:
      command: ["/usr/local/bin/bash"]
      args:
        - -c
        - >-
          (date +'%s %H:%M:%S %Z'; echo "Hi there") | tee /message.txt
```

#### 3. Now to build an image

```
TARGET_IMAGE="my-target-super-image"

docker buildx build \
    --push \
    --label WALLET_PUBLIC="$WALLET_PUBLIC" \
    -f goshfile.yaml \
    -t "$TARGET_IMAGE" \
    .

## OR more complicated way via buildctl directly
# # run buildkitd containered
# docker run -d --name buildkitd --privileged moby/buildkit:latest
# # build image
# buildctl --addr=docker-container://buildkitd build \
#         --frontend gateway.v0 \
#         --local dockerfile=. \
#         --local context=. \
#         --opt source=teamgosh/goshfile \
#         --opt filename=goshfile.yaml \
#         --opt wallet_public="$WALLET_PUBLIC" \
#         --output type=image,name="$TARGET_IMAGE",push=true
```

Here we parameterize the image build process with our wallet credentials.

#### 4. Sign the image (WIP: will be part of build image process)

```
docker pull $TARGET_IMAGE # buildkit push image directly to the registry and it doesn't persist locally

# my-target-super-image's sha256
TARGET_IMAGE_SHA=`docker inspect --format='{{index (split (index .RepoDigests 0) "@") 1}}' $TARGET_IMAGE`

docker run --rm teamgosh/sign-cli sign \
    -n <blockchain_network e.g. https://gra01.net.everos.dev> \
    -g $WALLET \
    -s $WALLET_SECRET \
    $WALLET_SECRET \  # signer secret can be different
    $TARGET_IMAGE_SHA
```

Now you have signed the image.

### You can check the image signature with your public key

```
TARGET_IMAGE="my-target-super-image"
# or IMAGE_NAME="my_repo:5000/library/my-target-super-image:latest@sha256:..."

WALLET_PUBLIC=$(docker inspect --format='{{.Config.Labels.WALLET_PUBLIC}}' $TARGET_IMAGE)

TARGET_IMAGE_SHA=$(docker inspect --format='{{index (split (index .RepoDigests 0) "@") 1}}' $TARGET_IMAGE)

docker run --rm teamgosh/sign-cli check \
    -n <blockchain_network e.g. https://gra01.net.everos.dev> \
    $WALLET_PUBLIC \
    $TARGET_IMAGE_SHA
```

**NOTE**: Anyone who has the image can [validate](verify-images-in-docker-extension.md) it. The image has label WALLET\_PUBLIC and image's sha256 also publicly available.

Additionally, [signer tool](https://github.com/tonlabs/gosh/tree/main/content-signature) can deploy a proof contract to GOSH blockchain that will be publicly available to all wanting to verify the image they pull from dockerhub.

### Examples

[Publisher example](https://github.com/tonlabs/gosh/blob/main/buildkit/examples/publisher)
