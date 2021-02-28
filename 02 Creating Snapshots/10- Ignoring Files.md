# 10- Ignoring Files

In almost every project there are some files we do not want git to track them. Like for example `.log` files.

For example I added a `logs` folder and a `.log` file, in te root directory of the project. `git status` will mark the new folder as untracked.

```zsh
❯ git status
On branch main

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	logs/

nothing added to commit but untracked files present (use "git add" to track)
```

To ignore files we must create a special file called `.gitignore` in the root of the project. This file as no name just as an extension. In that we will add the files or folders we want git to ignore.

We can include as many files or folder we want and use patterns as well like `*.log` to include all log files.

In this case we add the folder `logs/` to `.gitignore`. Now if we run `git status` we will no longer see the `logs/` folder, Instead it marks a new file `.gitignore`.

```zsh
❯ git status
On branch main
Your branch is ahead of 'origin/main' by 14 commits.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	.gitignore

nothing added to commit but untracked files present (use "git add" to track)
```

Now we must add and commit the `.gitignore` to the repository.

This only works if the file or directory to be ignored has not been included in the repository. If by accident we included a file in the repository and only later add it to `.gitignore`, Git is not going to ignore it, because it is already in the repository.

To ignore first we have to remove it from the **Staging Area**, with the `git rm --cached`. So lets suppose we had added the `logs/` folder the repository by accident. We can run:

```zsh
git rm --cached -r logs/
```

And them commit the changes. The `-r` flag is to allow recursive removal.

In GitHub repository [gitignore](https://github.com/github/gitignore) we can see a list of `.gitignore` templates for different programming languages.
