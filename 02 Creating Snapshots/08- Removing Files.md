# 08- Removing Files

To delete a file from the project we use the same workflow. Just delete teh file normally, then we add the changes to the **Staging Area** and the we commit.

I have added and committed a file names `test.txt` and then deleted that file. When we run `git status`, we will get the following output:

```zsh
❯ git status
On branch main

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   02 Creating Snapshots/08- Removing Files.md
	deleted:    test.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

In the example we have one file marked **modified** and another file marked as **deleted**.

If we run `git ls-files`we will see a list of files in the **Staging Area**, in my case:

```zsh
❯ git ls-files
01 Getting Started/01- Introduction.md
01 Getting Started/02- How to Take This Course.md
01 Getting Started/03- What is Git.md
01 Getting Started/04- Using Git.md
01 Getting Started/05- Installing Git.md
01 Getting Started/06- Configuring Git.md
01 Getting Started/07- Getting Help.md
01 Getting Started/images/03-01.png
01 Getting Started/images/03-02.png
01 Getting Started/images/03-03.png
01 Getting Started/images/06-01.png
02 Creating Snapshots/01- Introduction.md
02 Creating Snapshots/02- Initializing a Repository.md
02 Creating Snapshots/03- Git Workflow.md
02 Creating Snapshots/04- Staging Files.md
02 Creating Snapshots/05- Committing Changes.md
02 Creating Snapshots/06- Committing Best Practices.md
02 Creating Snapshots/07- Skipping the Staging Area.md
02 Creating Snapshots/08- Removing Files.md
02 Creating Snapshots/images/03-01.png
README.md
test.txt
```

Even after deleting `text.txt` from the **Working Directory** it still exist in the **Staging Area**.

Use `git add test.txt` to add that file to the staging area, to be committed.

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	deleted:    test.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   02 Creating Snapshots/08- Removing Files.md
```

And now `git commit -m "Delete unnecessary file"`.

```zsh
❯ git commit -m "Delete unnecessary file"
[main 632354b] Delete unnecessary file
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 test.txt
```

To remove a file we have to remove it both form the **Working Directory** and the **Staging Area**.

We can perform this operation with a single command `git rm test.txt`