Connect to an online repository to share your work with others. On GitHub, you'll need to create a remote repository using your GitHub account and generate a token for validating Git operations. Finally, on your local machine, you'll need to clone that repository using the access token you generated.

# Create a remote repository
You can either figure it out on your own, as it's quite simple, or follow this [quickstart guide](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories) in GitHub's official documentation.


# Generate an access token
Follow the [steps](https://docs.github.com/en/enterprise-server@3.9/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token) described in the "Managing your personal access token" topic in GitHub's official documentation.

>You can view a list of all the tokens you've created by following the same steps described previously. At some point along the way, you'll see a list of all your tokens.

# Clone the remote repo
Before cloning the remote repository, it's advisable to run the following code in your Git Bash.

```
$ ~ > git config --global credential.helper store
```

This will enable you to save the credentials you'll use in the future to a plain-text file on your disk, ensuring they never expire. This means that as long as you don't change your access token for the Git host, you won’t need to enter your credentials again. However, it's important to note that this approach stores your passwords in cleartext in a plain file in your home directory.

For more information on Git's credentials system, access Git's documentation on [Credential Storage](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage).

Now, follow [steps](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository#cloning-a-repository) described in the "cloning a repository" topic in GitHub's official documentation. At some point along the way, you'll be prompted to enter your credentials. For the password, use the access token you've created. If you've executed the previous command, you won't need to enter your credentials again thereafter.

# Connect to an empty remote repo
In addition to cloning an existing remote repository, you can also connect your local repository to an empty remote repository on GitHub.

Run the following command in your local repository to initialize a Git repository.
```
$ ~/local-repo > git init
```

As advised in the previous topic, it's also recommended to run `git config --global credential.helper store` in your Git Bash before proceeding to the next step.

Add the URL for the remote repository where your local repository will be pushed:
```
$ ~/local-repo > git remote add origin [remote_url]
```

Once you've done this, your code is no longer confined to your local machine. Now, you have the option to share your changes with others online by using Git commands such as `git push origin`.