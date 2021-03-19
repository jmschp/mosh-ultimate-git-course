# 12- Sharing Branches

## Push branch to **Remote Repository**

When we create a new branch it will only be available in our **Local Repository**. If we want to share our branches with team members we have to `push` them to the **Remote Repository**.

If we try to `push` a branch, that it is not in the **Remote Repository**, with `git push`, we will get an error.

For example I have created a branch named `bugfix` and tried to `push` it. Git will throw an error:

```zsh
❯ git push
fatal: The current branch bugfix has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin bugfix
```

The error message **_`The current branch bugfix has no upstream branch.`_** means that this branch is not linked to a remote tracking branch in origin, if we run `git branch -vv`, we can see this.

```zsh
❯ git branch -vv
* bugfix 9edbb2f lesson complete
  main   9edbb2f [origin/main] lesson complete
```

To set the remote tracking branch we run the command Git suggested `git push --set-upstream origin <name-of-branch>`, we can abbreviate the option `--set-upstream` to `-u`.

```zsh
git push -u origin bugfix
```

And them again `git branch -vv` to see the result.

```zsh
❯ gb -vv
* bugfix 9edbb2f [origin/bugfix] lesson complete
  main   9edbb2f [origin/main] lesson complete
```

## Delete a branch from **Remote Repository**

To delete a branch from the **Remote Repository** we run `git push -d origin <name-of-branch>`.

```zsh
git push -d origin bugfix
```