# 17- Discarding Local Changes

When we want to discard local changes, in other others, changes in the **Working Directory**, we use the `git restore`, without the `--staged` flag.

When we run this command, Git is going to take a copy from the next environment in this case the **Staging Area**, and copy it in the **Working Directory**.

We can pass to it as arguments a specific file or multiple files, with a `.` (dot) for all files, or patterns like for example `*.txt` for all text files.

In case of new files (untracked files), Git does not change anything, because it does not know where to get a previous version of this file, it does not exist in the **Staging Area** or **Repository**. To remove untracked files we can use `git clean` with the `-fd` flags, `-f` for force and `-d` for whole directories.

If we run this command without the flags on untracked files we will get a fat error:

```zsh
fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; refusing to clean
```

This is a way of git ro warns us that this can not be undone.
