# 05- Comparing Branches

We can compare branches to see different commits between them. To do so use the command `git log <first-branch>..<second-branch>`. This will return all the commits that are in `<second-branch>`, and not in `<first-branch>`.

```zsh
❯ git log main..bugfix-signup-form

```
