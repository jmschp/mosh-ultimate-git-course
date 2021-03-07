# 08- Viewing the Changes Across Commits

To see what has been changed across a range of commits we use the `diff` command. For example `gif diff HEAD~2 HEAD`, will return all the changes from the last two commits `HEAD~2` until the most recent commit `HEAD`.

We can add a particular file to that command to only see the changes made to that file, like `git diff HEAD~2 HEAD "03 Browsing History (44m)/06- Aliases.md"`

Like with the `log` command, we can pass `--name-only` and `--name-status` here to see the list of file that have been changed.
