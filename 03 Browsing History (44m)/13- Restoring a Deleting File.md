# 13- Restoring a Deleting File

If we want to recover a deleted file we can do it by checkout the previous commit, of the one that deleted the file.

For example I have run `git rm "03 Browsing History (44m)/10- Finding Bugs Using Bisect.md"` and delete this file. Wih `git log --oneline`, we can see that the file was deleted in the last commit.

```zsh
dacc1ec (HEAD -> main) delete file
33bceb5 start new lesson
1ce178a lesson complete
b5f716e lesson complete
54b967c add details to lesson
```

Now to recover that file we checkout the previous commit (or teh parent commit), in this case `33bceb5`, passing the nane file.

```zsh
git checkout 33bceb5 -- "03 Browsing History (44m)/10- Finding Bugs Using Bisect.md"
```

After running this command we can see that we have in the **Staging Area** one new file with `git status`.

```zsh
❯ git status
On branch main

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   03 Browsing History (44m)/10- Finding Bugs Using Bisect.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	03 Browsing History (44m)/13- Restoring a Deleting File.md
```
