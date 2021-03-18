# 06- Aliases

We can set aliases from frequently used commands so we do not have to type them in the long form. That is done the config property `alias`, like so.

```zsh
git config --global alias.l "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

We we are setting the `l` as an alias of `log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit`.

So ater setting that property we can use `git l`.
