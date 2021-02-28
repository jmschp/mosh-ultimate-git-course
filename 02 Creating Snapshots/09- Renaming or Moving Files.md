# 09- Renaming or Moving Files

When we rename a file and the run `git status` we will see the following output:

```zsh
❯ git status
On branch main

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	deleted:    02 Creating Snapshots/09- Renaming or Moving.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	02 Creating Snapshots/09- Renaming or Moving Files.md

no changes added to commit (use "git add" and/or "git commit -a")
```

We have to changes and both are unstaged. One that is a delete operation, and a new untracked file.

If we 