# 10- Finding Bugs Using Bisect

Git provides a great tool to find bugs quickly **Bisect**.

Image that we have a bug in an application, but we do not know where the bug was introduced. Using the **Bisect** to we can narrow our search.

First we have to tell it that the current state, being the last commit, is a bad commit. And them we have to give it a good commit, as teh good state.

Running `git log --oneline`, let say that the good state or good commit is `9f61863`. at that point in time the application was ok.

```zsh
ebbd4b1 (HEAD -> main) add details to lesson
66cf5ab (origin/main) add details to lesson
2ee3bb6 add details to lesson
18869aa lesson complete
f2150f7 lesson complete
4acfee7 lesson complete
dd6b4b2 fix: typo
b9e25df start new lesson
9f61863 style: change tab to spaces
bf77b4e lesson completed
[...]
```

So first we run `git bisect start`, this will initialize the the **`bisect`** operation.

Then we tell it the bad commit, witch is the current one, run `git bisect bad`.

Then we give it a good commit run `git bisect good 9f61863`. This will give the following output:

```zsh
❯ git bisect good 9f61863
Bisecting: 4 revisions left to test after this (roughly 2 steps)
[18869aaa853d0e3b2383a9104184f05eadd61722] lesson complete
```

If we run the `git log --oneline --all`. We can see that the `HEAD` is detached. So Git as made a checkout to the middle of the history, between the bad and good commit we gave `bisect`. So our **Working Directory** will be restored to that point in time.

```zsh
54b967c (main, refs/bisect/bad) add details to lesson
9325623 add details to lesson
ebbd4b1 add details to lesson
66cf5ab add details to lesson
2ee3bb6 add details to lesson
18869aa (HEAD) lesson complete
f2150f7 lesson complete
4acfee7 lesson complete
dd6b4b2 fix: typo
b9e25df start new lesson
9f61863 (refs/bisect/good-9f618634b2592513a9da3da313f554abec2e18cc) style: change tab to spaces
bf77b4e lesson completed
0aa8fd5 restore deleted file
40d94ee deleted file
2d077eb lessons complete
```

At this point we can run our application and automated tests to see if the problem is still there. If the bug persists it means that it is somewhere between commit `18869aa` and commit `b9e25df`. If the bug is gone it means it was introduced in the other half.

Suppose this was a good commit, so we run `git bisect good`. Meaning the bug is in the upper half. Between commit `2ee3bb6` and the latest commit. This will have the following output:

```zsh
❯ git bisect good
Bisecting: 2 revisions left to test after this (roughly 1 step)
[66cf5ab9240156e59aca2923bc0d73a6583af68d] add details to lesson
```

So now running `git log --oneline --all`, Git as moved the `HEAD` to the middle of the half that should have the problem.

```zsh
54b967c (origin/main, main, refs/bisect/bad) add details to lesson
9325623 add details to lesson
ebbd4b1 add details to lesson
66cf5ab (HEAD) add details to lesson
2ee3bb6 add details to lesson
18869aa (refs/bisect/good-18869aaa853d0e3b2383a9104184f05eadd61722) lesson complete
f2150f7 lesson complete
4acfee7 lesson complete
dd6b4b2 fix: typo
b9e25df start new lesson
9f61863 (refs/bisect/good-9f618634b2592513a9da3da313f554abec2e18cc) style: change tab to spaces
bf77b4e lesson completed
0aa8fd5 restore deleted file
40d94ee deleted file
2d077eb lessons complete
```

Now `HEAD` in the `66cf5ab` commit, lets image we run our test and the bug is still there, so this is a bad commit, we run `git bisect bad`. The out put is:

```zsh
❯ git bisect bad
Bisecting: 0 revisions left to test after this (roughly 0 steps)
[2ee3bb6004b4f8e681693b35f81df16ae425fa10] add details to lesson
```

With `git log --oneline --all`, we see now that we have one commit marked as **`(refs/bisect/bad)`**, and Git as moved `HEAD` to the `2ee3bb6` commit. So the bug must be in commit `66cf5ab` or `2ee3bb6`.

```zsh
54b967c (origin/main, main) add details to lesson
9325623 add details to lesson
ebbd4b1 add details to lesson
66cf5ab (refs/bisect/bad) add details to lesson
2ee3bb6 (HEAD) add details to lesson
18869aa (refs/bisect/good-18869aaa853d0e3b2383a9104184f05eadd61722) lesson complete
f2150f7 lesson complete
4acfee7 lesson complete
dd6b4b2 fix: typo
b9e25df start new lesson
9f61863 (refs/bisect/good-9f618634b2592513a9da3da313f554abec2e18cc) style: change tab to spaces
bf77b4e lesson completed
0aa8fd5 restore deleted file
40d94ee deleted file
2d077eb lessons complete
```

Let's suppose the bug is still there, meaning the bug was introduced in commit `2ee3bb6`. So we run `git bisect bad`. Git will output the info about that commit like the following example:

```zsh
❯ git bisect bad
2ee3bb6004b4f8e681693b35f81df16ae425fa10 is the first bad commit
commit 2ee3bb6004b4f8e681693b35f81df16ae425fa10
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Sun Mar 7 15:37:14 2021 -0300

    add details to lesson

 03 Browsing History (44m)/09- Checking Out a Commit.md | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```

After we are done we have to attach the `HEAD` pointer to the branch with the command `git bisect reset`.

With `git bisect` we can split our history in half, to see various commit, and find the commit that introduced a problem.
