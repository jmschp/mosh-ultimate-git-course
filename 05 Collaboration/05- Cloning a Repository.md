# 05- Cloning a Repository

To clone a repository we need the repository url. For example: **_`https://github.com/jmschp/mosh-ultimate-git-course.git`_**.

Then in our machine we run the command `git clone <url>`, this will create a local copy of the repository. This command only copies the **_`main`_** branch, even if there are other branches in the **Central Repository**.

```zsh
git clone https://github.com/jmschp/mosh-ultimate-git-course.git
```

## Changing the default directory

When using the `clone` command Git will create a directory with the same name of the repository. In ths case `mosh-ultimate-git-course`. We can change it by passing a new name after the url `git clone <url> <my-folder>`

```zsh
git clone https://github.com/jmschp/mosh-ultimate-git-course.git mosh-git
```

The above command will copy the repository to a new folder called `mosh-git`.