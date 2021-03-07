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

Then we give it a good commit run `git bisect good 9f61863`.
