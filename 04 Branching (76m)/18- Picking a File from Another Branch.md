# 18- Picking a File from Another Branch

Sometimes we may need a single file from one branch in another branch. Unlike cherry picking that merges a commit, we can bring only one file. For this operation we use the `restore` command. In the branch that needs the files we run `git restore --source=<name-of-branch> -- <file-name>`, git will update the **_Working Directory_** with the latest version of that file from the target branch

Let's suppose we need a file named `config.rb` from an unmerged branch called **feature** in **_`main`_**, so we run:

```zsh
git restore --source=feature -- config.rb
```
