# __GOSH Web__

[GOSH Web](https://app.gosh.sh/) is also a good way to get started with GOSH.

It implements GOSH repository management as a simple web interface.

You will be able to create your GOSH account and Decentralized Autonomous Organization (DAO), set up and manage repositories. Repositories stored in GOSH can then be interacted with like any regular remote repository, with a few small configurations to git, making decentralized code management easily available to anyone.

## __Create account__

To get started with GOSH, you need an active Github-account.

Click **Create account with Github** to start registering on GOSH

![](../images/gosh_web_Authorize_Gosh_01.jpg)


After click **Authorize gosh-sh**

![](../images/gosh_web_Authorize_Gosh_02.jpg)

!!! info
    The special GOSH DAO Bot will help with registration in Gosh.
    It will deploy your DAO and upload your selected repositories to GOSH.

In the list of organizations received from Github, click on the organization

![](../images/gosh_web_Authorize_Gosh_03.jpg)

and select repositories for upload into Gosh.

![](../images/gosh_web_Authorize_Gosh_04.jpg)

Do this **for each** organization for which you want to upload repositories to Gosh.

!!! danger
    After registering on GOSH you will not be able to return to this step in this release.

    This will be available later

!!! info
    If you want other GOSH users to be able to find you by your email, give permission.

Then click **Upload**

![](../images/gosh_web_Authorize_Gosh_05.jpg)

​If you are familiar with blockchain, you know what to do with a seed phrase.

If you're new to blockchain, all you need to know, is that this is the key to your account and all your assets on GOSH. Your public key, which can identify you on the blockchain and the secret key you'll use to sign your actions can always be calculated from your seed phrase.

To create the GOSH-account, the seed phrase will be generated for you. If you already have the GOSH-account, click **Clear** and enter your own one seed phrase.

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

When entering the GOSH will ask you to set up a PIN code:

!!! info
    Set a new PIN code for each new session.

![](../images/gosh_web_Authorize_Gosh_10_pin.jpg)

And unlock with PIN code.

The Organizations page will open after your account is created.

![](../images/gosh_web_Authorize_Gosh_08_wellcom.jpg)


!!! info
    __When the repositories are uploaded, a notification will be sent to your email.__

Follow the link in the letter.

![](../images/docker_ext_create_acc_02_welcom_letter.jpg)

Enter the saved seed phrase and click **Sign in**.

![](../images/gosh_web_Authorize_Gosh_09_signIn.jpg)

Also set up a PIN code and unlock with PIN code.

## __Create Organization__

<!-- The Organizations page will open after your account is created. -->

Click **New organization** button in the Organizations section.

![](../images/gosh_web_Create_ORG_01.jpg)

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

![](../images/gosh_web_Create_ORG_03_list_orgs.jpg)


## __Create Repository__

To create a repository in your organization click **New repository** in the Repositories section.​

![](../images/gosh_web_Create_Repo_01_new_repo.jpg)

Enter repository name and click **Create repository**.

!!! warning
    The repository name must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

![](../images/gosh_web_Create_Repo_02_name_repo.jpg)

## __​Create Branch__

Repository is created with default main branch. To create another branch, click on the **branches** counter.​

![](../images/gosh_web_Create_branch_01.jpg)

Select the branch to be forked, enter new branch name, and click​ **Create branch**.

!!! warning
    The branch name must contain only Latin letters, numbers, hyphen, underscore character `( a...z, 0...9, -, _ )`

![](../images/gosh_web_Create_branch_02_name.jpg)

Once the branch is created, it will appear in the branches list.

![](../images/gosh_web_Create_branch_03_list_dranches.jpg)

Switch to it via drop down list.

![](../images/gosh_web_Create_branch_04_switch_branches.jpg)

## __Create File__

To create file, click **Add file** button.

![](../images/gosh_web_Create_file_01_new_file.jpg)

Enter file contents and name.

![](../images/gosh_web_Create_file_02_name_contents.jpg)

You can use **Preview** if needed. MD syntax is supported for preview.

Once done, scroll down to **Commit data**, enter commit info and click **Commit changes**.​

![](../images/gosh_web_Create_file_03_commit_data.jpg)

Commit status will be displayed below.

![](../images/gosh_web_Create_file_04_proces_create_file.jpg)

If the branch you are working in requires no voting to confirm commits, the file will be added. Otherwise a DAO [vote](gosh-web.md#voting-in-smv-soft-majority-vote) will be initiated.

## __Create Pull Request__
 <!-- <a href="#create-pull-request" id="create-pull-request"></a> -->

Click on the **Pull requests** tab and set up the pull request: what branch to merge from and to. Once selected, click **Compare**.

![](../images/gosh_web_Create_PR_01.jpg)

The branches will be compared. Review the changes, set up the pull request and click Commit changes.

![](../images/gosh_web_Create_PR_02_comparing.jpg)


!!! info
    **Note**: When merging into the main branch, and in some other cases (depending on DAO setup), a DAO proposal will be initiated by trying to commit.

    Organization Tokens have to be sent to the DAO Soft Majority Vote contract to start a proposal for DAO members to [vote](gosh-web.md#voting-in-smv-soft-majority-vote) on.

## __Voting in SMV (Soft Majority Vote)__

Actions that require a DAO vote, such as merging into main, are performed by creating a proposal.

To create a proposal, or to vote for a proposal someone else created, some of your tokens need to be [allocated to SMV](gosh-web.md#send-tokens-to-smv) (once the proposal is completed), you can get them back.

For example, to merge into main, [create a pull request](gosh-web.md#create-pull-request) from some other branch. A proposal will be generated and will appear on the **Events** page.

![](../images/gosh_web_Voiting_SMV_01.jpg)

Open the proposal and review the contents.

![](../images/docker_ext_Voiting_SMV_02_proposal.jpg)

The voting period is indicated on the proposal page. This is the time allotted for [voting](../on-chain-architecture/organizations-gosh-dao-and-smv.md#soft-majority-voting). Unless a decisive majority of >50% is achieved early, votes will be counted at the end of this period.

Voting statistics are located under the status **Running**. The green and red counters indicate how many tokens have been used at the moment to vote for and against the proposal.

The green indicator in the top right corner means that the SMV smart contracts are not currently processing any new votes. It turns red when the SMV contracts are busy.

Once you have made a decision, select the amount of tokens with which you are ready to vote and click **Vote for proposal**


The red and green numbers next to **Running** status indicate how many tokens were used by now to vote for and against the proposal.

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
