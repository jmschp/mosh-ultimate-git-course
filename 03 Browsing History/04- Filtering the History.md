# 04- Filtering the History

In a project with a long history we can have hundreds or even thousands of commits. We use we can filter commits, so we do not have to view the al history.

## Filter by last n commits `-number`

We can pass a number to the `git log` command. For example with `git log -3` we can view the last 3 commits. The following output is from the command `git log --oneline -3`.

```zsh
4acfee7 (HEAD -> main, origin/main) lesson complete
dd6b4b2 fix: typo
b9e25df start new lesson
```

## Filter by author `--author=`

With the option `--author=` we can filter commits by author, `git log --author="Miguel"`.

## Filter by date `--before` and or `--after`

Wit he option `--before` and or `--after` we can filter the commit history by date, we do not have to pass both options. For example `git log --oneline --after="2021-03-06"`. It is also possible to specify relative dates, like `git log --oneline --after="yesterday"`, `git log --oneline --after="one week ago"`, `git log --oneline --after="two day ago"`.

## Filter by message `--grep`

We can filter commits by keywords in their message with the `--grep` option. For example `git log --online --grep="typo"`. This will return all the commits tha have the word `typo` in their message. This command is case sensitive.

## Filter by content `-S`

We can filter commits by content of the file with the `-S` option. For instance if we need to find a commit that added or remove a certain function declaration,for example the function `hello()` we use `git log -S"hello()"`. Notice that we do not pass an `=` sign to the `-S` option. Here with the command `git log --oneline -S"VS Code"`, we can see all the commits that have the `VS Code` in the file content.

```zsh
4acfee7 (HEAD -> main, origin/main) lesson complete
bf77b4e lesson completed
15478b9 Lesson completed
f289d8a First commit
```

We could add the `--patch` option to see the actual changes made, `git log --oneline -S"VS Code" --patch`.

## Filter by commit range

It is also possible to filter a range of commits, using the commit hash `git log 15478b9..b02e494`.

## Filter by file

We can filter commits that applied changes to a particular file or several files, just by passing the name of the file, with the relative path at the end of the command, like so `git log -- "02 Creating Snapshots/16- Unstaging Files.md"`. The `--` double hyphens separating the command from the file is optional, but if we do not pass it, depending on the file name Git can throw an error of ambiguity. The file name should be the last option given to the command.