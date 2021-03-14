# 08- Fast-forward Merges

## Git log for branches `--graph`

To have a better visualizations of branches with `git log`, it is better to include the `--graph` option. It will produce an output where we are abe to better view the branch path.

```zsh
❯ git log --oneline --graph
* 23c694d (HEAD -> fast-forward-merge) add details to lesson
* 6d91b25 (origin/main, main) add details to lesson
* 932b8dd lesson complete
* 1433f35 lesson complete
* 6d7a701 style: add final empty line
* 18c119d lesson start
* 176761d lesson completed
[...]
```

In this log we can see that the branch ***`fast-forward-merge`*** is one commit ahead of ***`main`***, and that there is a linear path between them.

## Merge branch

To merge the ***`fast-forward-merge`*** branch into ***`main`***, we first should have committed all of our work in that branch and them we switch to ***`main`***. In the ***`main`*** branch we run the merge with the command:

```zsh
git merge fast-forward-merge
```
