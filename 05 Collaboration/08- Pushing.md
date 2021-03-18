# 08- Pushing

With the `git push <remote-repository> <name-of-branch>` command we can send (upload) our changes to the **Remote Repository**.

```zsh
❯ git push origin main
Enumerating objects: 30, done.
Counting objects: 100% (30/30), done.
Delta compression using up to 8 threads
Compressing objects: 100% (24/24), done.
Writing objects: 100% (25/25), 649.54 KiB | 19.68 MiB/s, done.
Total 25 (delta 11), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (11/11), completed with 3 local objects.
To https://github.com/jmschp/mosh-ultimate-git-course.git
   0065a18..a170331  main -> main
```

It is also possible to abbreviate this command and only run `git push`, by default Git assumes the **Remote Repository** **_`origin`_**, and it will also assume teh current branch.

## Reject push

In some situations our `push` may be rejected. For example if some team member pushed before us. So the **Remote Repository** and **Local Repository** histories have diverged.

To resolve this, first we have to `pull` the **Remote Repository** and merge the changes, and them we can `push`.
