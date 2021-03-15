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
```
When we commit to ***`3-way-merge`***, this branch will move forward, but will have a linear path to ***`main`***. This linear path is broken when changes are applied to ***`main`*** before the merge.
