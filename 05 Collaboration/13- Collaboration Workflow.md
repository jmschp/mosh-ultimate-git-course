# 13- Collaboration Workflow

For this example I have created a new branch directly on GitHub, we can use the `fetch` command to download this new branch.

```zsh
❯ git fetch
From https://github.com/jmschp/mosh-ultimate-git-course
 * [new branch]      feature    -> origin/feature
```

When we run `fetch` we got a remote tracking branch. We can run `git branch` to list all the local branches, but this new fetched branch will not be displayed, because it is a remote tracking branch. We can see it with `git branch -r`

```zsh
❯ git branch -r
  origin/HEAD -> origin/main
  origin/feature
  origin/main
```

Now we can create a new local branch that maps to this remote tracking branch. To do that we use the the following command, `git switch -c <local-branch> <remote-tracking-branch>`.

```zsh
❯ git switch -c feature origin/feature
Branch 'feature' set up to track remote branch 'feature' from 'origin'.
Switched to a new branch 'feature'
```

After all team members have set up the branch in their local machine, they can collaborate in this branch.

If one team member deletes this branch from the **Remote Repository**, other team member will still have the the remote tracking branch in their machine. To remve remote tracking branches that are not in the **Remote Repository**, run `git remote prune <remote-repository>`.

```zsh
git remote prune origin
```
