# 09- Storing Credentials

We can store the credentials for access to the **Remote Repository**, and tell git where to find them. For this we can set `credential.helper` in the configuration.

## Cache

With the `cache` configuration Git will save the credentials for 15 minutes in memory.

```zsh
git config --global credential.helper cache
```

## MacOs

We can use macOS keychain, to permanently store our credential. First run the following commando to know if the macOS keychain helper is installed.

```zsh
❯ git credential-osxkeychain
usage: git credential-osxkeychain <get|store|erase>
```

If it is installed we can set it, with the following command, if not Git will give us instructions on how to install it.

```zsh
git config --global credential.helper osxkeychain
```
