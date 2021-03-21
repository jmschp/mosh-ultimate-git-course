# 08- Amending the Last Commit

In situations where we made a mistake in the last commit, like a typo in the message, or adding a file that shouldn't be there, we can amend the commit. We don't actually modify the last commit, in really Git creates a new commit, because git commits are immutable.

## Amend a commit message or include changes

With the `--amend` option we can add more changes to the last commit or modify the commit message. In case we need to add more changes in the code to the last commit, first we need to stage them and the run `git commit --amend -m <message>`. Optionally we can omit the message and accept the last message, so run `git commit --amend` will open the default editor with the previous commit message.

```zsh
git commit --amend
```

## Remove a file from the last commit

To remove a file from the last commit, first we need to use the `reset` command with the `--mixed` option, `git reset --mixed HEAD~1`. With this command Git will unstage our changes, but the **Working Directory** will not be affected.

Then we can restage the changed we need and perform a normal commit.

```zsh
git reset --mixed HEAD~1

git add <files>

git commit -m <commit message>
```

Here we do not use the `--amend` option, because we have reseated the `HEAD`, so the last commit is not there anymore.
