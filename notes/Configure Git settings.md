Get and set some Git variables to customize your Git operations. You'll configure the `user.name`, `user.email`, and `init.defaultBranch` variables. The `user.name` and `user.email` variables dictate what appears in the author and committer fields of commit objects. The `init.defaultBranch` variable enables overriding the default branch name, for example, when initializing a new repository.

> Access [git-config documentation](https://git-scm.com/docs/git-config) for more details and configurations.

# Set initial configurations
**git config**: shows an overview of the command
```
$ ~ > git config
```

**Set a user name globally**: sets the user name to be used on all repositories created under that same computer user account
```
$ ~ > git config --global user.name [user_name]
```

> Remember to wrap your user name around double quotes if it contains blank spaces

**Set an email globally**: sets the email to be used on all repositories created under that same computer user account
```
$ ~ > git config --global user.email [user_email]
```

**Change the default branch name globally**: sets the default branch name to be used on all repositories created under that same computer user account
```
$ ~ > git config --global init.defaultBranch [default_branch_name]
```

# Check the set variables
Check the set variables all at once:
```
$ ~ > git config --global --list
```

Check the set variables one by one
```
$ ~ > git config --global [variable_name]
```

# Find the origin
Find where these configuration are stored:
```
$ ~ > git config --global --show-origin [variable_name]
```