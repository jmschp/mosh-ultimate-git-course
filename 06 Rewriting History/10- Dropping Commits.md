# 10- Dropping Commits

To drop commits we use interactive `rebase` operation. So we have to pass to the `rebase` operation the parent of the commit we want to drop, like `git rebase- i <parent-commit>`.

In interactive `rebase` operations conflicts might arise. For this example we want to drop the commit `72856ea`, but this commit introduces a new file that is used in the next commit `111bd75`, so this will provoque a conflict.

```zsh
❯ git log --oneline --graph --all
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

To select the parent of commit `72856ea`, we can use several syntaxes, `72856ea~1`, or `72856ea^`. When we run the interactive `rebase` operations, and select `drop` in the script operation, we will be prompt with the conflict warning message.

```git
❯ git rebase -i 72856ea~1
CONFLICT (modify/delete): terms.txt deleted in HEAD and modified in 111bd75 (Update terms of service and Google Map SDK version.). Version 111bd75 (Update terms of service and Google Map SDK version.) of terms.txt left in tree.
error: could not apply 111bd75... Update terms of service and Google Map SDK version.
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 111bd75... Update terms of service and Google Map SDK version.
```

In the short status we can see the `terms.txt` file as two changes `D` for `deleted`, because the rebase operations drops the commit where the file was introduced, and `M` for `modified`, because these file is modified in the next commit.

```zsh
❯ git status -s
M  package.txt
DU terms.txt
```

To resolve this conflict we use the `mergetool` command.

```zsh
❯ g mergetool

This message is displayed because 'merge.tool' is not configured.
See 'git mergetool --tool-help' or 'git help config' for more details.
'git mergetool' will now attempt to use one of the following tools:
tortoisemerge emerge vimdiff nvimdiff
Merging:
terms.txt

Deleted merge conflict for 'terms.txt':
  {local}: deleted
  {remote}: modified file
Use (m)odified or (d)eleted file, or (a)bort?
```

In this case we want the `m` option for modified. Then we continue the rebase operation, with `git rebase --continue`.
