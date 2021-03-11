# 06- Stashing

[Git stashing docs](https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)
## Create stash

When we switch branches Git restores our **Working Directory** to the last snapshot of the target branch. In case we have local changes in the **Working Directory** that have not yet been committed, they could be lost. In such situations Git does not allows us to switch branch, ti will throw an erro if we try.

```zsh
❯ git switch main
error: Your local changes to the following files would be overwritten by checkout:
    04 Branching (76m)/06- Stashing.md
Please commit your changes or stash them before you switch branches.
Aborting
```

Let's imagine that this changes are still work in progress, and we do not want to commit them yet. In this situation we should stash our changes. Stashing changes means save them in a Git safe place, but they will be not part of the history. To do so we run `git stash push -m <stashing-message>`. For example:

```zsh
❯ git stash push -m "lesson details"
Saved working directory and index state On bugfix-lesson: lesson details
```

This command will stash (save) our changes, but they will not be displayed in the **Working Directory**. At this point we could switch branches and the changes will be safe.

If we have new untracked files, by default, they are not included in the stash, to include them we have to use the `--all` or `-a` option.

```zsh
❯ git stash push -a -m "lesson details"
```

## List stashes

To view the stashes we run `git stash list`. Each stash as a unique identifier, `stash@{0}`.

```zsh
❯ git stash list
stash@{0}: On bugfix-lesson: lesson details stash list
stash@{1}: On bugfix-lesson: lesson details
```

## Show stash changes

Before applying the changes to the **Working Directory** we can view them with the command `git stash show stash@{i}`, where `i` is the stash index. Or we just pass the index, like so:

```zsh
❯ git stash show 1
04 Branching (76m)/06- Stashing.md | 19 +++++++++++++++++++
1 file changed, 19 insertions(+)
```

## Apply stash changes to Working Direcotry

To apply the stash we use `git stash apply i` like so:

```zsh
❯ git stash apply 0
On branch bugfix-lesson
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   04 Branching (76m)/06- Stashing.md

no changes added to commit (use "git add" and/or "git commit -a")
```

## Delete a stash

After applying the stash we can delete it running `git stash drop i`. Or we may not need to apply the changes from the stash, so we can delete it without applying.

```zsh
❯ git stash drop 0
Dropped refs/stash@{0} (9206126462da8a1cfc1777768c767edf54c49cdd)
```

Alternately we can delete all stash running `git stash clear`.