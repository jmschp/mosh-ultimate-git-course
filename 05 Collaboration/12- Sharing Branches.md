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

To set the remote tracking branch we run the command Git suggested `git push --set-upstream origin <name-of-branch>`, we only have to pass `--set-upstream` option the first time.

We can abbreviate the option `--set-upstream` to `-u`.

```zsh
❯ git push -u origin bugfix
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 1.56 KiB | 1.56 MiB/s, done.
Total 4 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'bugfix' on GitHub by visiting:
remote:      https://github.com/jmschp/mosh-ultimate-git-course/pull/new/bugfix
remote:
To https://github.com/jmschp/mosh-ultimate-git-course.git
 * [new branch]      bugfix -> bugfix
Branch 'bugfix' set up to track remote branch 'bugfix' from 'origin'.
```

And them again `git branch -vv` to see the result.

```zsh
❯ gb -vv
* bugfix 9edbb2f [origin/bugfix] lesson complete
  main   9edbb2f [origin/main] lesson complete
```

## Delete a branch from **Remote Repository**

To delete a branch from the **Remote Repository** we run `git push -d origin <name-of-branch>`. This will only detete the branch in the **Remote Repository**, it will still be available in the **Local Repository**.

```zsh
git push -d origin bugfix
```

We can check with `git branch -vv`.

```zsh
❯ gb -vv
* bugfix 133c99c [origin/bugfix: gone] add details to lesson
  main   9edbb2f [origin/main] lesson complete
```
