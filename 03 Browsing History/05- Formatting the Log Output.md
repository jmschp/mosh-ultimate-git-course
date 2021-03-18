# 05- Formatting the Log Output

## Option `--pretty=format:`

We can personalize the output of the log command with the option `git log --pretty:format:`. We must pass it a format string that where we can use plain text combined with placeholder that will be replaced by Git with information. In [Git PRETTY FORMATS](https://git-scm.com/docs/pretty-formats) we can see a list of all the place holders. We can also pass colors to the output

The following command (courtesy of [Le Wagon](https://www.lewagon.com/) bootcamp setup).

```zsh
git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

Will give teh following output:

```zsh
* 4acfee7 - (HEAD -> main, origin/main) lesson complete (57 minutes ago) <Miguel Pimenta>
* dd6b4b2 - fix: typo (57 minutes ago) <Miguel Pimenta>
* b9e25df - start new lesson (3 days ago) <Miguel Pimenta>
* 9f61863 - style: change tab to spaces (3 days ago) <Miguel Pimenta>
* bf77b4e - lesson completed (3 days ago) <Miguel Pimenta>
* 0aa8fd5 - restore deleted file (3 days ago) <Miguel Pimenta>
* 40d94ee - deleted file (3 days ago) <Miguel Pimenta>
* 2d077eb - lessons complete (3 days ago) <Miguel Pimenta>
* b02e494 - delete file (3 days ago) <Miguel Pimenta>
* cb02fd6 - Lesson complete (5 days ago) <Miguel Pimenta>
* 9b67da8 - Lesson start (5 days ago) <Miguel Pimenta>
```
