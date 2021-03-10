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

The `*` in front of the ***main*** means that at the momment we are in that branch. It is also possible to view the current branch with `git status`.

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


