# 03- Viewing the History

We are going to view in more detail the `git log` command. Wit this command, as we know we can see in more detail the commit history. It gives us teh following output.

```zsh
commit b9e25dff4873a1db8cd615784a485d4ab7854e14 (HEAD -> main, origin/main)
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:45:40 2021 -0300

    start new lesson

commit 9f618634b2592513a9da3da313f554abec2e18cc
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:42:01 2021 -0300

    style: change tab to spaces

commit bf77b4e007ecaa30da382ff80e7afdc1fb1f6fc9
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:35:58 2021 -0300

    lesson completed
```

Given we can have multiple pages of commits pressing`space` will take us to the nex page, we can also use the up and down arrows to navigate, and `q` to exit.

Apart fom the `--oneline` options that show a summary of the commits history, que can use other options.

## Option --stat

With the `--stat` options we can se the list of file that have been changed in each commit. The `git log --stat` will give the following output.

```zsh
commit b9e25dff4873a1db8cd615784a485d4ab7854e14 (HEAD -> main, origin/main)
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:45:40 2021 -0300

    start new lesson

 03 Browsing History (44m)/01- Introduction.md | 1 +
 1 file changed, 1 insertion(+)

commit 9f618634b2592513a9da3da313f554abec2e18cc
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:42:01 2021 -0300

    style: change tab to spaces

 02 Creating Snapshots/15- Viewing a Commit.md | 8 ++++----
 1 file changed, 4 insertions(+), 4 deletions(-)

commit bf77b4e007ecaa30da382ff80e7afdc1fb1f6fc9
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Thu Mar 4 23:35:58 2021 -0300

    lesson completed

 02 Creating Snapshots/19- Creating Snapshots with VSCode.md    |   9 +++++++++
 02 Creating Snapshots/20- Creating Snapshots with GitKraken.md |   0
 02 Creating Snapshots/images/19-01.png                         | Bin 0 -> 375202 bytes
 3 files changed, 9 insertions(+)
```

Or combined with the `--online` option `git log --oneline --stat`.

```zsh
b9e25df (HEAD -> main, origin/main) start new lesson
 03 Browsing History (44m)/01- Introduction.md | 1 +
 1 file changed, 1 insertion(+)
9f61863 style: change tab to spaces
 02 Creating Snapshots/15- Viewing a Commit.md | 8 ++++----
 1 file changed, 4 insertions(+), 4 deletions(-)
bf77b4e lesson completed
 02 Creating Snapshots/19- Creating Snapshots with VSCode.md    |   9 +++++++++
 02 Creating Snapshots/20- Creating Snapshots with GitKraken.md |   0
 02 Creating Snapshots/images/19-01.png                         | Bin 0 -> 375202 bytes
 3 files changed, 9 insertions(+)
```

## Option --patch

With the `--path` option we can see the actual changes in each commit. The `git log --online --patch` wil give the following ouput.

```zsh
bf77b4e lesson completed
diff --git a/02 Creating Snapshots/19- Creating Snapshots with VSCode.md b/02 Creating Snapshots/19- Creating Snapshots with VSCode.md
new file mode 100644
index 0000000..bac12c2
--- /dev/null
+++ b/02 Creating Snapshots/19- Creating Snapshots with VSCode.md
@@ -0,0 +1,9 @@
+# 19- Creating Snapshots with VSCode
+
+In VS Code built-in source controle we can use several Git commands.
+
+![VS Code Source Controle](./images/19-01.png "VS Code Source Controle")
+
+The view in the left panel is similar to the `git status` output.
+
+If we hover the mouse hover a file we will see a **`+`** sign. That will add files to the **Staging Area**. If that file is already in the **Staging Area** a **`-`** sig will be displayed, to remove the file from the **Staging Area**.
diff --git a/02 Creating Snapshots/20- Creating Snapshots with GitKraken.md b/02 Creating Snapshots/20- Creating Snapshots with GitKraken.md
new file mode 100644
index 0000000..e69de29
diff --git a/02 Creating Snapshots/images/19-01.png b/02 Creating Snapshots/images/19-01.png
new file mode 100644
index 0000000..292335c
Binary files /dev/null and b/02 Creating Snapshots/images/19-01.png differ
```
