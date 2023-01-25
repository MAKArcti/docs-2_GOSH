# Git Remote Helper

Git Remote Helper is a [`git-client helper`](https://git-scm.com/docs/gitremote-helpers#_description) to interact with remote repositories hosted on the GOSH blockchain.

## Setup helper from source

1. Prerequisites:

      - Rust v1.65+
      - Protobuf Compiler
      - `git`
      - `make`

2. Clone [`git-remote-gosh`](https://github.com/gosh-sh/gosh) repo
3. `cd git-remote-gosh` and run `make build`
4. Add path with `git-remote-gosh` for availability via `$PATH`:

```
export PATH="<path/to/git-remote-gosh>:$PATH"
```

or use symlink  (e.g. into`/usr/local/bin`):

```
ln -s /path/to/git-remote-gosh /usr/local/bin/git-remote-gosh
```

Run the following command to make sure it's available:

```
which git-remote-gosh
```

## Setup helper from binary releases

1. Prerequisites:

      - wget

2. Download latest version:

      `wget https://github.com/gosh-sh/gosh/releases/latest/download/git-remote-gosh-arm64`

3. Set executable flag:

      `chmod +x git-remote-gosh-amd64`

4. Copy binary to any searchable path:

      `cp git-remote-gosh-amd64 /usr/local/bin/git-remote-gosh`

### Setup user account

When creating your account in [Docker extension](docker-extension.md) or [GOSH Web](gosh-web.md) you received a GOSH wallet address and keys.

To be able to push to Gosh repositories, you need to set up these credentials for Git Remote Helper.

The helper expects that the wallet credentials are in the file `~/.gosh/config.json` or in the file specified in the environment variable `GOSH_CONFIG_PATH`:

```
{
  "ipfs": "https://ipfs.network.gosh.sh",
  "primary-network": "goshnet",
  "networks": {
    "goshnet": {
      "user-wallet": {
        "profile": "USERNAME",
        "pubkey": "655b120c996b4f69c686cb3b769fbdfa0141006ce6a88dc012bf323c30265924",
        "secret": "6bdc38c0ecd6f74399f6b8ff2486f0e2abb32fca712caf3e4a47ef4a2634c4e8"
      },
      "endpoints": ["https://network.gosh.sh/"]
    }
  }
}
```

## Use GOSH as remote

For correct usage of the helper you should refer to remote in the following form:

```
gosh://GOSH_ROOT/REPO_NAME
```

### Set remote for existing local repository

```
git remote add origin gosh://0:a6af961f2973bb00fe1d3d6cfee2f2f9c89897719c2887b31ef5ac4fd060638f/my-user-name/my-repo
```

### Clone repository

```
git clone gosh://0:a6af961f2973bb00fe1d3d6cfee2f2f9c89897719c2887b31ef5ac4fd060638f/my-user-name/my-repo
```

## Ever SDK protocol

By default, the SDK in Remote Helper uses the WebSocket protocol. If for some reason this does not suit you (for example, you are using Alpine Linux), then set the environment variable `GOSH_PROTO` to `http`

```
export GOSH_PROTO=http
```
