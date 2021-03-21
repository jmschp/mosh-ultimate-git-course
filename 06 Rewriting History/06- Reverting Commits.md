# 06- Reverting Commits

In case we have pushed our commits to a public **Remote Repository** we should not use the `reset` command. We should use the `revert` command, this will create a new commit base on our target commit.

## Revert one commit

To revert a single commit we pass that commit to the revert command. Either by the commit ID or by the `HEAD~n` syntax. This will create new commit.

History before revert:

```zsh
❯ git log --oneline --graph
* 088455d (HEAD -> master) .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```

```zsh
❯ git revert HEAD~1
[master 1b7aed7] Revert "WIP"
 1 file changed, 1 deletion(-)
```

History after revert:

```zsh
❯ git log --oneline --graph
* 1b7aed7 (HEAD -> master) Revert "WIP"
* 088455d .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```

The above command reverts the last commit, so it will create a new commit undoing the changes made by the last commit.

## Revert a range of commits

We can revert a range of commits using the `..` notation, like:

```zsh
git revert HEAD~4..HEAD
```

or

```zsh
git revert 8441b05..1b7aed7
```

Note that the first commit `HEAD~4` or `111bd75`, in the above example are not included.

This operation will create a new commit for each commit reverted.

History before revert:

```zsh
❯ git log --oneline --graph
* 088455d (HEAD -> master) .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```

History after revert:

```zsh
❯ git log --oneline --graph
* 645357e (HEAD -> master) Revert "WIP"
* 685ec4e Revert "Update terms of service and Google Map SDK version."
* 6a65dda Revert "WIP"
* a0262f0 Revert "."
* 088455d .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```

### Range revert with single commit `--no-commit`

Instead of creating one new commit for each reverted commit (which might pollute the history) we can use the option `--no-commit`, that will create only one commit, for all the reverted commits. With this options Git will add the required changes to the **Staging Area**, for each reverted commit.

```zsh
git revert --no-commit HEAD~4..HEAD
```

If we run `git status`, we can see the changes of the reverse of the last 4 commits.

```zsh
❯ git status
On branch master
You are currently reverting commit 72856ea.
  (all conflicts fixed: run "git revert --continue")
  (use "git revert --skip" to skip this patch)
  (use "git revert --abort" to cancel the revert operation)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    modified:   map.txt
    modified:   package.txt
    deleted:    terms.txt
```

If we are happy with the changes we use the `--continue` option.

```zsh
git revert --continue
```

Or if we want to abort we use th `--abort` option.

```zsh
git revert --abort
```

History after revert:

```zsh
❯ git log --oneline --graph
* b7ed3ee (HEAD -> master) Revert last 4 commits
* 088455d .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```
