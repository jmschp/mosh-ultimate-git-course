# 06- Configuring Git

## Setting

The fist time we use git we have to specify a few configuration setting.

- Settings:
- Name
- Email
- Default editor
- Line ending

## Settings Level

We can specify these configurations setting at 3 different levels

1. System ---> Apply to all users of the current computer.
2. Global ---> Apply to all repositories of the current user.
3. Local ---> Apply to the current repository.

## Command to apply settings

The command to apply setting is `git config --global <setting> <value>`. The flag `--global` specifies we are applying setting the the Global level.

- In the terminal type:
  - `git config --global user.name "Miguel Pimenta"`
  - `git config --global user.email my-email@code.com`
  - `git config --global core.editor "code --wait"` code for **VS Code** the `--wait` tells the terminal to wait until the window is closed.
  - `git config --global --edit` command to open the config file in the editor.

### End of lines

To manage end of line correctly we have to configure a property called `core.autocrlf`. These is a very import setting, so git can properly handle end of lines.

#### Windows

On Windows end of lines are marked with two special characters:

- Carriage Return: `\r`
- Line Feed: `\n`

`git config --global core.autocrlf true`

#### macOS / Linux

On macOS and Linux end of lines are marked with one special character:

- Line Feed: `\n`

`git config --global core.autocrlf input`

![End of Line Characters](./images/06-01.png "End of Line Characters")
