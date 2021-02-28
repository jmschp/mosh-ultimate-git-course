# 04- Staging Files

Git those not track files automatically we have to tell Git to track new files we add. Even when we start a new repository with `git init`, in project that already as several files, Git will only track them, we need to add them.

We can run the `git status` command to see the status of the **Working Directory** and **Staging Area**.

The output will be something like these:

```zsh
❯ git status
On branch main

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	02 Creating Snapshots/04- Staging Files.md

nothing added to commit but untracked files present (use "git add" to track)
```

The above message is telling us we have untracked files.

Use the `git add` command to stage that file. In my case I have to quotation marks `""`, because there are whitespace, in the file path

```zsh
git add "02 Creating Snapshots/04- Staging Files.md"
```

We can also use patterns to add files.

```zsh
git add *.md
```

These will add all the files with an `.md` extension.

Now if we run `git status` again, we will have the following output:

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   02 Creating Snapshots/04- Staging Files.md
```

If we make changes to the same file, after adding it to the **Staging Area** and run `git status`, we will have the following output:

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   02 Creating Snapshots/04- Staging Files.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   02 Creating Snapshots/04- Staging Files.md
```

We have the same file in the **Staging Area** and also marked as modified, and not staged. When we run the `git add` command Git took a snapshot of that file and added it to the **Staging Area**. So now we have a one version of the file in the staging area and another version in the **Working Directory**.

We can run `git add` one more time to add our changes to the **Staging Area**.

```zsh
❯ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   02 Creating Snapshots/04- Staging Files.md
```
