# 05- Committing Changes

Now that we have files in the **Staging Area**, we can commit them to the repository, with the command `git commit -m "My commit message"`

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   02 Creating Snapshots/05- Committing Changes.md
```

With the command `git commit -m "New lesson started"` a snapshot will be saved to the repository.

```zsh
❯ git commit -m 'New lesson started'
[main cb4a472] New lesson started
 1 file changed, 4 insertions(+)
 create mode 100644 02 Creating Snapshots/05- Committing Changes.md
```

If we commit to more than one file, we will se the following message:

```zsh
❯ git commit -m 'Lesson completed'
[main bc32e03] Lesson completed
 2 files changed, 25 insertions(+)
 create mode 100644 02 Creating Snapshots/06- Committing Best Practices.md
 create mode 100644 02 Creating Snapshots/07- Skipping the Staging Area.md
```

When a short, one line, message is not sufficient, because we need to explain in detail the changes that where made we can use the command `git commit`, without the `-m "My message"` part. These will open the default editor with a file named `COMMIT_EDITMSG`.

In the first line we add a short description, ideal less than 80 characters, then we addd a line break and the more detail message. After we save and close the file the changes are committed. And we will hae in the terminal and ouput like the following:

```zsh
❯ git commit
[main e0a1a79] Continuing lesson 5 Committing Changes
 1 file changed, 18 insertions(+)
```

Example detailed commit:

```zsh
Continuing lesson 5 Committing Changes

Adding more details to the lesson number 5 Committing Changes of section 2 Creating Snapshots of the course The Ultimate Git Course.
Lectured by Mosh Hamedani.
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch main
# Your branch is ahead of 'origin/main' by 2 commits.
#   (use "git push" to publish your local commits)
#
# Changes to be committed:
#	modified:   02 Creating Snapshots/05- Committing Changes.md
#
# ------------------------ >8 ------------------------
# Do not modify or remove the line above.
# Everything below it will be ignored.
diff --git a/02 Creating Snapshots/05- Committing Changes.md b/02 Creating Snapshots/05- Committing Changes.md
index 10da8dc..21c6f07 100644
--- a/02 Creating Snapshots/05- Committing Changes.md
+++ b/02 Creating Snapshots/05- Committing Changes.md
@@ -2,3 +2,21 @@

 Now that we have files in the **Staging Area**, we can commit them to the repository, with the command `git commit -m "My commit message"`

+```zsh
+On branch main
+
+Changes to be committed:
+  (use "git restore --staged <file>..." to unstage)
+	new file:   02 Creating Snapshots/05- Committing Changes.md
+```
+
+With the command `git commit -m "New lesson started"` a snapshot will be saved to the repository.
+
+```zsh
+git commit -m 'New lesson started'
+[main cb4a472] New lesson started
+ 1 file changed, 4 insertions(+)
+ create mode 100644 02 Creating Snapshots/05- Committing Changes.md
+```
+
+When a short, one line, message is not sufficient, because we need to explain in detail the changes that where made we can use the command `git commit`, without the `-m "My message"` part. These will open the default editor.
\ No newline at end of file
```
