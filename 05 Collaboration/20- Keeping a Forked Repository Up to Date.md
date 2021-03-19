# 20- Keeping a Forked Repository Up to Date

## Add a **Remote Repository**

To keep a fork up to date we can add a remote repository linked to the original repository. To do that we use the `remote` command. With `git remote -v` we can list all the **Remote Repositories**. To add a new remote we use the `add` command, like so `git remote add <remote-name> <url>`. We can name the **Remote Repository** what ever we want, but in this situations is is usually called `upstream`.

```zsh
git remote add upstream https://github.com/username/repository-name.git
```

## Rename a **Remote Repository**

To rename a remote repository use the `rename` command, `git remote rename <remote-old-name> <remote-new-name>`.

```zsh
git remote rename upstream base
```

In this example we rename the **Remote Repository** `upstream` to `base`.

## Removing a **Remote Repository**

To remove a remote **Remote Repository** we use the `rm` command. `git remote rm <remote-name>`

```zsh
git remote rm base
```
