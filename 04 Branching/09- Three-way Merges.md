# 09- Three-way Merges

The 3-way-merge is implicit when the branches to merge diverge. This happens when changes are made to the original branches after the creation of the new branch.

In this example I have created a new branch from ***`main`*** (the original branch), called ***`3-way-merge`***, in the moment of creation both branches are pointing to the same commit.

```zsh
❯ git log --oneline --graph
* 2827b4c (HEAD -> 3-way-merge, main) add details to lesson
* 80a0972 add details to lesson
*   afba0c3 Merge branch 'no-fast-forward-merge'
|\
| * 00a98bb add details to lesson
| * 9aff663 add details to lesson
| * 2694107 add details to lesson
|/
* d8fbb20 add details to lesson
[...]
```

When we commit to ***`3-way-merge`***, this branch will move forward, but will have a linear path to ***`main`***. This linear path is broken when changes are applied to ***`main`*** before the merge.

Here I have switched to ***`main`*** and made 2 commits. So now the ***`main`*** branch has diverged from ***`3-way-merge`***.

```zsh
❯ git log --oneline --graph
* e81cc69 (main) add lesson title
* b9063c7 add file for lesson
| * 08e6d5e (HEAD -> 3-way-merge) add details to lesson
|/
* 2827b4c add details to lesson
* 80a0972 add details to lesson
*   afba0c3 Merge branch 'no-fast-forward-merge'
|\
| * 00a98bb add details to lesson
| * 9aff663 add details to lesson
| * 2694107 add details to lesson
|/
* d8fbb20 add details to lesson
[...]
```

Now when we run a merge Git will run a 3-way-merge. It will open the default editor with a commit message, when add more details if needed to the commit message.

```zsh
❯ git log --oneline --graph
*   e26d5a7 (HEAD -> main) Merge branch '3-way-merge'
|\
| * 2f37a10 (3-way-merge) add lesson title
| * c99eb28 add file for lesson
| * 08e6d5e add details to lesson
* | e81cc69 add lesson title
* | b9063c7 add file for lesson
|/
* 2827b4c add details to lesson
* 80a0972 add details to lesson
*   afba0c3 Merge branch 'no-fast-forward-merge'
|\
| * 00a98bb add details to lesson
| * 9aff663 add details to lesson
| * 2694107 add details to lesson
|/
* d8fbb20 add details to lesson
```

In the log we can see the merge commit. After a merge we can deleted the merged branch ***`3-way-merge`***, in this case.
