# 08- Fast-forward Merges

## Git log for branches `--graph`

To have a better visualizations of branches with `git log`, it is better to include the `--graph` option. It will produce an output where we are abe to better view the branch path.

```zsh
❯ git log oneline --graph
[...]
* 6572ee7 add details to lesson
*   3f0416c (origin/main, main) Merge branch 'main' into bugfix-signup-form
|\
| * 11f8264 start new lesson
* | 27324f4 add details to lesson
* | db8b63d lesson complete
|\|
| * 7718a7f lesson complete
* | 987c5be add details to lesson
* | 54bb974 start new lesson
|/
* 6d5df20 lesson complete
* b89cef8 lesson complete
[...]
```
