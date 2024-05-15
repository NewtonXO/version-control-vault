Connect to an online repository to share your work with others. On GitHub, you'll need to create a remote repository using your GitHub account and generate a token for validating Git operations. Finally, on your local machine, you'll need to clone that repository using the access token you generated.

# Connect to an existing remote repo
This remote repo can be yours or someone else's.

## Clone the remote repo
Before cloning the remote repository, it's advisable to run the following code in your Git Bash.

```
$ ~ > git config --global credential.helper store
```

This will enable you to save the credentials you'll use in the future to a plain-text file on your disk, ensuring they never expire. This means that as long as you don't change your access token for the Git host, you won’t need to enter your credentials again. However, it's important to note that this approach stores your passwords in cleartext in a plain file in your home directory.

For more information on Git's credentials system, access Git's documentation on [Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage).

Now, follow [steps](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository#cloning-a-repository) described in the "cloning a repository" topic in GitHub's official documentation. At some point along the way, you'll be prompted to enter your credentials, but if you have executed the previous "git config" command, you won't need to enter your credentials thereafter.

> [!info]
> - You can use an access token as your password. If your organization requires it, you can either request an access token or create one yourself (see "Generate an access token" on this page).
> - If you already have a saved access token and need to change it, refer to "How to locally change your Access Token" on this page.

# Connect to a brand new repo

## Create a remote repository
You can either figure it out on your own, once it's quite simple, or follow this [quickstart guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories) in GitHub's official documentation. Follow the next title's steps to connect to your new repo.

## Connect to an empty remote repo
In addition to cloning an existing remote repository, you can also connect your local repository to an empty remote repository on GitHub.

> [!note]
> If you need to change your local repository's remote repository, skip the first two commands and run `git remote set-url origin [new_remote_url]` instead. Then, continue with the remaining steps as usual. If your access token has expired or needs to be changed for any reason, refer to "How to locally change your Access Token" on this page before starting.

Run the following command in your local repository to initialize a Git repository.
```
$ ~/local-repo > git init
```

As advised in the previous topic, it's also recommended to run `git config --global credential.helper store` in your Git Bash before proceeding to the next step.

Run the following command to add a remote (repositories whose branches you track) named `origin` for the repository at `remote_url`. You may be asked to enter your credentials on this step, but if you have executed the previous "git config" command, you won't need to enter your credentials thereafter.

> [!info]
> - You can use an access token as your password. If your organization requires it, you can either request an access token or create one yourself (see "Generate an access token" on this page).
> - If your access token has expired or needs to be changed for any reason, refer to "How to locally change your Access Token" on this page before starting.

```
$ ~/local-repo > git remote add origin [remote_url]
```

Push the commits from your local branch (`main` in this case) to the remote repository (`origin`). The `-u` flag, short for `--set-upstream`, establishes a tracking connection between your local branch (`main`) and the remote branch (`main` on `origin`). After setting the upstream, you can simply use `git push` or `git pull` without specifying the remote and branch names.
```
$ ~/local-repo > git push -u origin main
```

Once you've done this, your code is no longer confined to your local machine. Now, you have the option to share your changes with others online by using Git commands such as `git push`.

# Access Token

## How to create an Access Token
Follow the [steps](https://docs.github.com/en/enterprise-server@3.9/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token) described in the "Managing your personal access token" topic in GitHub's official documentation.

>[!info]
>You can view a list of all the tokens you've created by following the same steps described previously. At some point along the way, you'll see a list of all your tokens.

## How to locally change your Access Token
1. If you have access to the tokens, delete the previous one.
2. Create a new access token or ask your repository manager for a new one.
3. When you try to connect to a remote repository, you will be asked for your credentials. Enter the new access token as your password. If you were not asked for your credentials but encounter an authentication error, such as the one below when trying to run git commands, proceed to the next step:
	> remote: Invalid username or password.
	> fatal: Authentication failed for `[remote_repo_url]`
4. Edit the .git-credentials file (it's usually located in your user's folder, e.g., C:\Users\newton) and replace the previous access token with the new one.