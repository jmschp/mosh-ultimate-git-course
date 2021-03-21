# 09- Amending an Earlier Commit

To amend an earlier commit we use interactive rebasing. With rebasing we can replay other commits on top of a commit. First we choose the commit we need to amend and pass it parent to the `rebase` command with the `-i` option, like `git rebase -i <commit>`.

We can modify one or more commits. Git will recreate each commit that goes through the rebase operation even if the are not edit.

![Rebasing](./images/09-01.png "Rebasing")

In the above image suppose we only changed commit `B`, Git will recreate `C` and `D` to point not the new `B` commit.

Rebasing is a destructive operation because it rewrites history.

The `-i` option means we are going to interact with the rebase operation, stop it, make changes, continue it or abort it.

This command will open de default editor with a script, listing all the commits we need to rebase, and instructions to perform the `rebase` operation.

```zsh
❯ git rebase -i 8527033
Stopped at 8441b05...  Add a reference to Google Map SDK.
You can amend the commit now, with

  git commit --amend '-S'

Once you are satisfied with your changes, run

  git rebase --continue
```

Here we can make the necessary changes, and then amend the commit. when we are done we run `git rebase --continue`, to continue the operation.

To abort the rebase operation in any point use the `--abort` option. `git rebase --abort`.

In a rebase operation, a change introduced in a earlier commit will be carried on thought the history.
