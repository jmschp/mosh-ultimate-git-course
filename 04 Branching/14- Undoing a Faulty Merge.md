# 14- Undoing a Faulty Merge

In case we need to undo a merge we have two options:

1. Remove the merge commit, as if it was never there (only if we did not shared the repository with others)
2. Revert the merge commit

## 1. Remove the merge commit

After a merge we have the **_`main`_** and **_`HEAD`_** pointers, pointing to the last commit, that is the merge commit.

![Merge commit](./images/14-01.png "Merge commit")

With the reset command we will move both pointers to the last commit before the merge. And remove the merge commit.

![Parent merge commit](./images/14-02.png "Parent merge commit")

Run the command:

```zsh
git reset --hard HEAD~1
```

After we run the command the merge commit does not have any commit or pointer pointing to it. So for Git this garbage, once in a while Git looks for commits like this and removes them.

### Resting the **_`HEAD`_** options

When resting the **_`HEAD`_** pointer, we have three option:

1. soft
2. mixed
3. hard

#### Option `--soft`

When we reset the **_`HEAD`_** using the `--soft` option, Git will have the **_`HEAD`_** pointer pointing to the indicated commit, in this case `HEAD~1`, so go back one commit, in the **_Repository_**. But the **_Staging Area_** and **_Working Directory_** are not affected.

```zsh
git reset --soft HEAD~1
```

![--soft option](./images/14-03.png "--soft option")

#### Option `--mixed`

In this case Git is going to apply the new snapshot to both the **_Repository_** and **_Staging Area_**, local changes in the **_Working Directory_** will not be affected.

Using the `--mixed` option, which is the default option so we do not need to specify it.

```zsh
git reset HEAD~1
```

![--mixed option](./images/14-04.png "--mixed mixed")

#### Option `--hard`

Using the `--hard` option Git will apply the new snapshot to all environments (**_Working Directory_**, **_Staging Area_**, **_Repository_**).This was the state we where before stating the merge.

![--hard option](./images/14-05.png "--hard mixed")

## 2. Revert the merge commit

If we have shared our history instead of undoing the merge commit we have to revert the last commit.

A merge commit has two parents so have to tell git how we want to revert the changes. Because our merge commit is in the **_`main`_** branch the first parent should also be in the **_`main`_** branch. To do this we use the the following command:

```zsh
git revert -m 1 HEAD
```

In the `-m 1`, we are specifying the first parent. And `HEAD` is representing the target commit, the last commit.

Running this Git will open the default editor with a default message for the revert commit.

### Option `-m`

From `git revet --help`

> -m parent-number, --mainline parent-number
> Usually you cannot revert a merge because you do not know which side of the merge should be considered the mainline. This option specifies the parent number (starting from 1) of the mainline and allows revert to reverse the change relative to the specified parent.
