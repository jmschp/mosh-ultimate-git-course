# 15- Viewing a Commit

## Show commit

To view what was changed in a commit we can use the `git show` command. We have to pass teh commit as an argument. There are two ways to reference a commit:

1. By the unique identifier, for example `git show 3e3c6c3`. We don't have to type all the characters, we can type fewer character as long they are unique.
2. Another way is using the `HEAD` pointer. `HEAD` is in front of the last commit, so we can type how many steps we want to go back `git show HEAD~2`, for example 2.

This will produce a similar output to `git diff`.

```zsh
commit da5f08b76c559362400177e88d3a01b6d7511531
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Sun Feb 28 16:52:55 2021 -0300

    Lessons start

diff --git a/02 Creating Snapshots/11- Short Status.md b/02 Creating Snapshots/11- Short Status.md
new file mode 100644
index 0000000..3b350e3
--- /dev/null
+++ b/02 Creating Snapshots/11- Short Status.md
@@ -0,0 +1,2 @@
+# 11- Short Status
+
```

## Show commit single file

If we want to see the exact version of a file saved in commit instead of seeing the differences we can use `git show HEAD~1:README.md`. So the `git show` command followed by `:`and the path to a file, in this example `README.md`, or another example, `git show HEAD~1:"02 CreatingSnapshots/12- Viewing Staged and Unstaged Changes.md"`.

## Show commit all files and directories

If we want to see all the files and directories in a commit we use `ls-tree`. A **tree** is a data structure for representing hierarchical information. These trees can have nodes and the nodes can have children. If we use `git ls-tree HEAD~1`, we will have an output like this:

```zsh
❯ git ls-tree HEAD~1
100644 blob 333c1e910a3e2bef1b9d0d4587392627d8388974    .gitignore
040000 tree 4c24e363fb92a146d90b33f5e6be484eda876cb1    01 Getting Started
040000 tree fedd8b67c40b90365ca1b2fc1357b15a56b8c9b6    02 Creating Snapshots
100644 blob abefdb35d01f55ffdabca93f53748b84f9d10e14    README.md
```

Files are represented using `blob` and directories are represented by `tree`. All of theses are object saved in git database. The `333c1e910a3e2bef1b9d0d4587392627d8388974` is a unique identifier of the corresponding file. We can use this identifier to vew the content of the file.

We can use `git show 333c1e` to view the content of the `.gitignore`, in that commit.

If we run this command on a `tree` like for instance `git show 4c24` we will get:

```zsh
tree 4c24

01- Introduction.md
02- How to Take This Course.md
03- What is Git.md
04- Using Git.md
05- Installing Git.md
06- Configuring Git.md
07- Getting Help.md
images/
```

## Git objects

Using `git show` we can view **Git Objects**, these objects can be:

- Commits
- Blobs (files)
- Tree (directories)
- Tags
