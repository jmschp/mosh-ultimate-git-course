# 14- Finding the Author of Line Using Blame

Git Blame is a command to find the author of a crappy line of code. Run `git blame <file>`

```zsh
git blame "03 Browsing History (44m)/13- Restoring a Deleting File.md"
```

This command will give an output like the following:

````zsh
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  1) # 13- Restoring a Deleting File
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  2)
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  3) If we want to recover a deleted file we can do it by checkout the previous commit, of the one that deleted the file.
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  4)
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  5) For example I have run `git rm "03 Browsing History (44m)/10- Finding Bugs Using Bisect.md"` and delete this file. Wih `git log --oneline`, we can see that the file was deleted in the last commit.
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  6)
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  7) ```zsh
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  8) dacc1ec (HEAD -> main) delete file
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300  9) 33bceb5 start new lesson
````

For each line of code in the file we can see

1. The commit ---> b89cef85
2. The author ---> Miguel Pimenta
3. Date & Time ---> 2021-03-08 23:30:10 -0300
4. Line number ---> 1
5. And the code it self.

## Git blame with email `-e`

We can use other option with `git blame`, for example `-e` will also return the email of the author.

```zsh
git blame -e "03 Browsing History (44m)/13- Restoring a Deleting File.md"
```

```zsh
b89cef85 (<jmiguelpimenta@gmail.com> 2021-03-08 23:30:10 -0300  1) # 13- Restoring a Deleting File
b89cef85 (<jmiguelpimenta@gmail.com> 2021-03-08 23:30:10 -0300  2)
b89cef85 (<jmiguelpimenta@gmail.com> 2021-03-08 23:30:10 -0300  3) If we want to recover a deleted file we can do it by checkout the previous commit, of the one that deleted the file.
b89cef85 (<jmiguelpimenta@gmail.com> 2021-03-08 23:30:10 -0300  4)
b89cef85 (<jmiguelpimenta@gmail.com> 2021-03-08 23:30:10 -0300  5) For example I have run `git rm "03 Browsing History (44m)/10- Finding Bugs Using Bisect.md"` and delete this file. Wih `git log --oneline`, we can see that the file was deleted in the last commit.
```

## Git blame filter by lines `-L`

We can filter the lines we want using the `-L` flag and we have to pass to it the start line and end line separated by a comma.

```zsh
git blame -L 1,3 "03 Browsing History (44m)/13- Restoring a Deleting File.md"
```

The above example will return the first three lines of code.

```zsh
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300 1) # 13- Restoring a Deleting File
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300 2)
b89cef85 (Miguel Pimenta 2021-03-08 23:30:10 -0300 3) If we want to recover a deleted file we can do it by checkout the previous commit, of the one that deleted the file.
```
