# 04- Working with Branches

## Create new branch

To create a new branch run `git branch <name-of-branch>`

```zsh
git branch bugfix
```

## View Branches

To view all the available branch run `git branch`

```zsh
❯ git branch
  bugfix
* main
```

The `*` in front of the **_main_** means that at the momment we are in that branch. It is also possible to view the current branch with `git status`.

## Change branches

Nowadays the command to changes branches is `git switch <name-of-branch>`. It used to be `git checkout <name-of-branch>`, it is possible to still use the old command.

```zsh
❯ git switch bugfix
Switched to branch 'bugfix'
```

## Rename a branch `-m`

The branches name should represent the work that is being performed on it. To rename a branch run the command `git branch -m <old-name> <new-name>`

```zsh
git branch -m bugfix bugfix-signup-form
```

## Commit to branch

When we commit to a branch this branch moves forward and the **_main_** branch stays where it is, we can see that with `git log --oneline`. The **_HEAD_** pointer will be pointing to the new branch head of **_main_**.

```zsh
54bb974 (HEAD -> bugfix-signup-form) start new lesson
6d5df20 (main) lesson complete
b89cef8 lesson complete
b4ef25f restore file
dacc1ec delete file
33bceb5 start new lesson
1ce178a lesson complete
b5f716e lesson complete
```

If we switch back to **_main_** our **Working Directory** will be restored to that point.

## Delete a brach `-d` or `-D`

To delete a branch we use the `-d` option, but if this branch as unmerged changes with master, Git will throw an error warning us