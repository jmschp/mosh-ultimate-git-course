# 16- Unstaging Files

When we want to unstage a file (remove the file from the **Staging Area**), in other word undo the `git add` command, we use the `git restore --staged`command. We can pass to it as arguments a specific file or multiple files, with a `.` (dot) for all files, or patterns like for example `*.txt` for all text files.

In this example I have the `02 Creating Snapshots/16- Unstaging Files.md` file changes in the **Staging Area**. We can see that with `git status` the file is marked as modified.

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    modified:   02 Creating Snapshots/16- Unstaging Files.md
```

Running `git restore --staged "02 Creating Snapshots/16- Unstaging Files.md"` will remove this changes from the **Staging Area**.

When we run `git status` again, we can see the changes are not staged for commit.

```zsh
❯ git status
On branch main

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
    modified:   02 Creating Snapshots/16- Unstaging Files.md

no changes added to commit (use "git add" and/or "git commit -a")
```

When we run the `git restore --staged` git removes that file from the **Staging Area** and places there the copy from the last commit with that file.
