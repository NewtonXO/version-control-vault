You can utilize Git to version control any repository, whether it contains programming code or other content. You can also version control your repository locally, without the need to always connect to a remote repository. Therefore, the commands below are categorized as `local` and `remote` for easier reference.

For more commands and detailed information, refer to [Git documentation](https://git-scm.com/docs).

# Basic Snapshotting
**STATUS** `local` - Show the working tree status
```
$ ~/Vaults/Version Control > git status
```

**ADD** `local` - Add file contents to the index
- Add all the current file contents found in the working tree at once
	```
	$ ~/Vaults/Version Control > git add .
	```
- Add an specific file in the working tree
	```
	$ ~/Vaults/Version Control > git add [file_path]
	```

**RM** `local` - Remove files from the index, or from the working tree and the index
- Remove all the current file contents found in the index, or the working tree and the index
	```
	$ ~/Vaults/Version Control > git rm .
	```
- Remove an specific file in the index, or the working tree and the index
	```
	$ ~/Vaults/Version Control > git rm [file_path]
	```

**COMMIT** `local` - Record the current contents of the index and the given log message describing the changes
```
$ ~/Vaults/Version Control > git commit -m "[message]"
```

# Branching and Merging

**LOG** `local` - List all commits to the current branch
```
$ ~/Vaults/Version Control > git log
```

# Undoing local changes
**Undoing GIT INIT** `local` - Make your repository a simple directory again. Use `rm` to delete all Git-related content from your current directory. Use `-r` and `-f` options to apply the `rm` command recursively and by force, respectively.
```
$ ~/Vaults/Version Control > rm -rf .git
```

**Restore** `local` - Restore working tree files. This action will undo any changes made to your local repository that have not been committed or added to the index for committing. This includes undoing file additions or removals, as well as changes to existing files.
- Restore all the current file contents found in the working tree at once
	```
	$ ~/Vaults/Version Control > git restore .
	```
- Restore an specific file in the working tree
	```
	$ ~/Vaults/Version Control > git restore [file_path]
	```

**Change a commit's message** `local` - Change the massege of your last commit to the current branch
```
$ ~/Vaults/Version Control > git commit --amend -m "[new_message]"
```

**RESET** `local` -  Reset the head to `[commit]`
- Reset the head to a commit, but do not modify the index file or the working tree. This leaves all changes made in your selected commit's files in the "Changes to be committed" state, as indicated by `git status`
	```
	$ ~/Vaults/Version Control > git reset --soft [commit_hash]
	```
- Reset the index but not the working tree, which results in the changed files being preserved but not marked for commit. This is the default aciton
	```
	$ ~/Vaults/Version Control > git reset --mixed [commit_hash]
	```
- Reset the index and working tree, which results in the changed files being completed discarded.
	```
	$ ~/Vaults/Version Control > git reset --hard [commit_hash]
	```
