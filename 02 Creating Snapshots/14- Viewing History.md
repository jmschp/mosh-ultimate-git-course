# 14- Viewing History

## Log

We can use the `git log` command to view the commit history. This command produces and output like the following. It is order by the newest to oldest commit.

```zsh
commit 3e3c6c3fced4e94579e7c506e742b480bd2c682c (HEAD -> main, origin/main)
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Sun Feb 28 17:39:31 2021 -0300

    Start lesson

commit 529f5c183f9084caa3f5eafd2435f67094888a94
Author: Miguel Pimenta <jmiguelpimenta@gmail.com>
Date:   Sun Feb 28 17:13:15 2021 -0300

    Added new lessons
```

Each commit ad a unique identifier, and hexadecial, 40 character that git generates automatically.

```zsh
commit 3e3c6c3fced4e94579e7c506e742b480bd2c682c
```

Next to the first commit we have **`(HEAD -> main)`**:

- `HEAD` is a reference to the current branch.
- `main` beeing the current branch.

## Log one line

With the `git log --oneline` we can see a shorter version of the `log`command.

```zsh
3e3c6c3 (HEAD -> main, origin/main) Start lesson
529f5c1 Added new lessons
da5f08b Lessons start
12156df Add details to lesson
0ed2ae3 Lesson completed
ebdd235 Add gitignore
4dec09d Add more details to lesson
```

## Reverse history

The `--reverse` flag reverts the log display history. It can be applied both to the log command and to the log one line command.

- `git log --reverse`
- `git log --oneline --reverse`
