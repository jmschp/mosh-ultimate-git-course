# 18- Restoring a File to an Earlier Version

Once git tracks a file it stores every version of that file in the database. With Git there are two way to restore a earlier version of file:

1. Restore a file to previous version
2. Undoing a commit

In this lesson we are going to look at restoring a file. For example if we delete a file by accident.

Using the `git rm` command I have deleted a file. And ist now marked as `deleted` in the **Staging Area**. We can see ti with `git status`

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    02 Creating Snapshots/17- Discarding Local Changes.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        02 Creating Snapshots/18- Restoring a File to an Earlier Version.md
```

After committing `git commit -m 'delete file'`, and fi we do a `git log --oneline`

```zsh
b02e494 (HEAD -> main) delete file
cb02fd6 Lesson complete
9b67da8 Lesson start
001ce95 Lesson complete
0746554 Start lesson
[...]
```

We can recover that file with `git restore`. By default git will restore a file from the next environment, so if the file we want to restore is in the **Working Directory**, Git will restore it from the **Staging Area**, and if it is in the **Staging Area** Git will restore it from the repository, or last commit.

In this case with `git restore --source=HEAD~1 "02 Creating Snapshots/17- Discarding Local Changes.md"`, we override the default behavior and restore the last commit that is when we deleted the file. With `git status` we will see the recovered file marked as untracked.

```zsh
❯ git status
On branch main

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        02 Creating Snapshots/17- Discarding Local Changes.md
        02 Creating Snapshots/18- Restoring a File to an Earlier Version.md

nothing added to commit but untracked files present (use "git add" to track)
```
