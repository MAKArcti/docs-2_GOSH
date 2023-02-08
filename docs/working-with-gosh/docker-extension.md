# __Docker Extension__

GOSH Docker Extension implements GOSH repository management and image verification as the newest feature of Docker - a Docker Extension.

You will be able to create your GOSH account and Decentralized Autonomous Organization (DAO), set up and manage repositories through a graphical interface directly in Docker Desktop. Repositories stored in GOSH can then be interacted with like any regular remote repository, with a few small configurations to git, making decentralized code management easily available to anyone.

Images built directly from code stored in GOSH can be verified as GOSH-sourced in the Docker Extension, ensuring security of the software supply chain. You will always know what code specifically is running in your containers, and that none of it was tampered with during build.

## __Installation__

Get the latest [Docker Desktop](https://www.docker.com/products/docker-desktop/) (4.8.0 or later), which supports extensions.

Launch the Desktop, go to the **Extensions** section, and click **Add Extensions**.

![](../images/docker_ext_install_01.jpg)

Select and install **Gosh** extension on the marketplace.

## __Create account__

Open the **Gosh verified images** extension in Docker Desktop. 
If you have a Gosh account, then enter your own one seed phrase, if not, you can create it by clicking on the link app.gosh.sh.

![](../images/docker_ext_create_acc_01.jpg)

To get started with GOSH, you need an active Github-account.

Click **Create account with Github.**

![](../images/gosh_web_Authorize_Gosh_01.jpg)

After click **Authorize gosh-sh**

![](../images/gosh_web_Authorize_Gosh_02.jpg)

In the list of organizations received from Github, click on the organization

![](../images/gosh_web_Authorize_Gosh_03.jpg)

and select repositories for upload into Gosh

![](../images/gosh_web_Authorize_Gosh_04.jpg)

Do this **for each** organization for which you want to upload repositories to Gosh.

!!! danger
    After registering on GOSH you will not be able to return to this step in this release.

    This will be available later

Then click **Upload**

![](../images/gosh_web_Authorize_Gosh_05.jpg)

​If you are familiar with blockchain, you know what to do with a seed phrase.

If you're new to blockchain, all you need to know, is that this is the key to your account and all your assets on GOSH. Your public key, which can identify you on the blockchain and the secret key you'll use to sign your actions can always be calculated from your seed phrase.

To create the GOSH-account, the seed phrase will be generated for you.

![](../images/gosh_web_Authorize_Gosh_06_seedF.jpg)

!!! danger
    Write your seed phrase down and store it somewhere safe, and never share it with anyone. Avoid storing it in plain text or screenshots, or any other non-secure way. If you lose it, you lose access to your assets. Anyone who gets it, gets full access to your assets.

!!! info
    Your seed phrase will be used to log into GOSH.

Once you have written down your seed phrase, click **Continue.**

Then choose a short nickname or create a new one and click **Create account**.

!!! warning
    The Usernames must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

![](../images/gosh_web_Authorize_Gosh_07_createAk.jpg)

!!! info
    __When the repositories are uploaded, a notification will be sent to your email.__

Follow the link in the email.
![](../images/docker_ext_create_acc_02_welcom_letter.jpg)


To log into Gosh open the **Gosh verified images** extension in Docker Desktop and enter the saved seed phrase and click **Sign in**.

![](../images/docker_ext_create_acc_03_signIn.jpg)

GOSH will ask you to set up a PIN code:

![](../images/gosh_web_Authorize_Gosh_10_pin.jpg)

And unlock with PIN code.

Once done, you will be logged into GOSH.

!!! info
    The GOSH DAO Bot will be a member of your organization.
    In the future, it will track changes in your repositories on Github and synchronize them with Gosh.

    The Bot can be removed from the DAO members by voting.
    But then there will be no automatic synchronization of repositories in GOSH if they have been changed in Github.


## __Create Organization__

The Organizations page will open after your account is created.

Click **New organization** button in the Organizations section.

![](../images/docker_ext_create_org_01_new_org.jpg)

​Input Organization name and members.

!!! warning
    The Organizations name must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

The first mandatory member is the creator, identified by their username.

The second member is the GOSH DAO Bot. It will synchronize repositories with github on Gosh.

Any other members can be added at creation - just enter the username of each member in new line.

At any later time the list of members [can be expanded](gosh-web.md#add-members-to-organization) by voting.

Click **Create organization**.

![](../images/gosh_web_Create_ORG_02_name_members.jpg)

​Once created, your organization will appear in the organization list. Click on it to continue.

![](../images/docker_ext_create_org_03_list_org.jpg)


## __​Create Repository__

To create a repository in your organization click **Create** in the Repositories section.

![](../images/docker_ext_create_repo_01_new_repo.jpg)

Enter repository name and click **Create repository**.

!!! warning
    The repository name must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

![](../images/gosh_web_Create_Repo_02_name_repo.jpg)


## __Create Branch__

Repository is created with default main branch. To create another branch, click on the **branches** counter.

![](../images/docker_ext_create_branch_01.jpg)

Select the branch to be forked, enter new branch name, and click​ **Create branch**.

!!! warning
    The branch name must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

![](../images/docker_ext_create_branch_02_name.jpg)

Once the branch is created, it will appear in the branches list.

![](../images/gosh_web_Create_branch_03_list_dranches.jpg)

Switch to it via drop down list.

![](../images/gosh_web_Create_branch_04_switch_branches.jpg)

## __Create File__

To create file, click **Add file** button.

![](../images/docker_ext_create_file_01_new_file.jpg)

Enter file contents and name. MD syntax is supported for preview.

![](../images/gosh_web_Create_file_02_name_contents.jpg)

Once done, scroll down to **Commit data**, enter commit info and click **Commit changes** button.

![](../images/gosh_web_Create_file_03_commit_data.jpg)

Commit status will be displayed below.

![](../images/gosh_web_Create_file_04_proces_create_file.jpg)

If the branch you are working in requires no vote to commit to, the changes will be commited immediately/ Otherwise a DAO [vote](docker-extension.md#voting-in-smv-soft-majority-vote) will be initiated.

## __Create Pull Request__

Click on the **Pull requests** tab and set up the pull request: what branch to merge from and to.

![](../images/docker_ext_create_PR_01.jpg)

View the diff, scroll down to **Commit data**, enter details and click **Commit changes**.

![](../images/docker_ext_create_PR_02_comparing.jpg)

!!! info
    When merging into the main branch, and in some other cases (depending on DAO setup), a DAO proposal will be initiated by trying to commit.

    Organization Tokens have to be sent to the DAO Soft Majority Vote contract to start a proposal for DAO members to [vote](docker-extension.md#voting-in-smv-soft-majority-vote) on.

## __Voting in SMV (Soft Majority Vote)__

Actions that require a DAO vote, such as merging into main, are performed by creating a proposal.

To create a proposal, or to vote for a proposal someone else created, some of your tokens need to be allocated to SMV (once the proposal is completed), you can get them back.

For example, to merge into main, [create a pull request](docker-extension.md#create-pull-request) from some other branch. A proposal will be generated and will appear on the **Events** page.

![](../images/docker_ext_Voiting_SMV_01.jpg)

Open the proposal and review the contents.

![](../images/docker_ext_Voiting_SMV_02_proposal.jpg)

The voting period is indicated on the proposal page. This is the time allotted for [voting](../on-chain-architecture/organizations-gosh-dao-and-smv.md#soft-majority-voting). Unless a decisive majority of >50% is achieved early, votes will be counted at the end of this period.

Voting statistics are located under the status **Running**. The green and red counters indicate how many tokens have been used at the moment to vote for and against the proposal.

The green indicator in the top right corner means that the SMV smart contracts are not currently processing any new votes. It turns red when the SMV contracts are busy.

Once you have made a decision, input the amount of tokens, select **Approve** or **Reject** and click **Vote for proposal**. Vote registration can take a bit of time.

!!! info
    As per the rules of Soft Majority Voting, to have a proposal approved early, you need at least 50% of the total supply of tokens in the repository + 1 token used to vote for the proposal.

    For example, in a repository with two members, where the total supply of tokens is 200, 101 token needs to be used to instantly approve a proposal. Thus with every member holding 100 tokens a proposal can never be instantly completed without the participation of members other than the proposal's author.

    On the other hand, so as not to depend on all members of an organization to vote, soft majority vote will complete with an approval at the end of the voting period, if 10% of the total token supply were used to vote for, and no one voted against.

    The more tokens are sent against the proposal, the higher the approving amount needs to be (up to 50% of the total supply  + 1 token) for the proposal to pass.

Other members of the Organization, who have transferred their tokens to SMV, will be able to vote for the proposal on this page in their own accounts.

!!! info
    Currently, even in organizations with a single member, voting still takes place when a proposal is created. 51 tokens are needed to approve a proposal in such a repository.

Once a majority has been reached early, or the voting period ended and the soft majority vote result was decided, the proposal completes and the proposed action is performed.

![](../images/docker_ext_Voiting_SMV_03_result.jpg)

## __View Public Key__

A user needs to know their public key, for example, when joining an organization.

To view your public key go to the main page of your account and click [**Settings**](https://app.gosh.sh/a/settings).

!!! danger
    Avoid storing your private key and seed phrase in plain text or screenshots, or any other non-secure way. If you lose it, you lose access to your assets. Anyone who gets it, gets full access to your assets.

![](../images/gosh_web_View_Public_Key_01.jpg)


## __Add Members to Organization__

Go to Organization **Settings** to the **Members** tab to manage your organization.

To add member enter the username of each candidate from a new line and click **Add members** button.

![](../images/gosh_web_Add_Members_01.jpg)

## __What's next?__

Set up [Git Remote Helper](git-remote-helper.md) and continue working with your repository.

You'll need your wallet credentials. Go to the main page of your account and click [**Settings**](https://app.gosh.sh/a/settings).
Scroll down and copy them.

![](../images/gosh_web_Whats_next_01.jpg)

To view the command to clone your repo, click the **Clone** button on your repo page.

![](../images/gosh_web_Whats_next_02.jpg)


## __Update Docker Extension__

When you need to update the Gosh verified images extension in Docker Desktop, you will see an orange indicator.

To update the extension, go to the menu and select **Manage**
![](../images/docker_ext_update_01.jpg)

В открывшейся вкладке нажмите **Update**

![](../images/docker_ext_update_02.jpg)

After downloading the update, click **Open**

![](../images/docker_ext_update_03.jpg)