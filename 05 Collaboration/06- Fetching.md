# 06- Fetching

The **Local Repository** and **Remote Repository** work independently. If we have new commits in our **Remote Repository**, because another team member pushed is work, our **Local Repository** will not be aware of it.

We have to use the `git fetch <remote-repository>` command to download the new commits. When we do so the **_`origin/main`_** pointer will move forward, and point to the new commits. But our working directory will not be updated

```zsh
git fetch origin
```

Optionally we can specify a branch to the `fetch` command, like `git fetch <remote-repository> <branch-name>`.

```zsh
git fetch origin bugfix
```

![Fetching](./images/06-01.png "Fetching")

To update our branch with the changes downloaded from the `fetch` command, we have to merge them with our branch, with the command:

```zsh
git merge origin/master
```

![Merge origin](./images/06-02.png "Merge origin")

## Remote and Local branches

With the command `git branch -vv` we can se how the remote and local branches are diverging.

```zsh
❯ git branch -vv
* main bbe3812 [origin/main: ahead 2] add details to lesson
```

In the above output from the `git branch -vv` we can see that our local **_`main`_** branch is connect to the remote **_`origin/main`_** branch. And the local branch is ahead by 2 commits.
