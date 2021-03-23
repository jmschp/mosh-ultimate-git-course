# 14- Splitting a Commit

To split a commit we use the interactive `rebase` operation. We pass to the rebase operation the parent of the commit we need to split. In the script we select the `edit` option for the commit we need to split.

Then in the `rebase` operation we unstage the changes of the commit with `git reset --mixed HEAD^`. Now the changes applied in this commit ar in our **Working Directory**.

With the unstaged changes we slipt the commit to our needs with normal `git add <file>` and `git commit -m <message>`. This will create new commits. Then continue the `rebase` operation to finish `git rebase --continue`.
