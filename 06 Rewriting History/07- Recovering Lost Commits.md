# 07- Recovering Lost Commits

With the `reflog` command we can see a log of how a reference (or pointer) as moved in our history. If we do not supply any options we will see how the `HEAD` pointer moved in history.  `git reflog <reference>`

```zsh
❯ git reflog
088455d (HEAD -> master) HEAD@{0}: reset: moving to HEAD~1
b7ed3ee HEAD@{1}: commit: Revert last 4 commits
088455d (HEAD -> master) HEAD@{2}: reset: moving to HEAD~4
645357e HEAD@{3}: revert: Revert "WIP"
685ec4e HEAD@{4}: revert: Revert "Update terms of service and Google Map SDK version."
6a65dda HEAD@{5}: revert: Revert "WIP"
a0262f0 HEAD@{6}: revert: Revert "."
088455d (HEAD -> master) HEAD@{7}: reset: moving to
[...]
088455d (HEAD -> master) HEAD@{27}: commit: .
f666091 HEAD@{28}: commit: WIP
111bd75 HEAD@{29}: commit: Update terms of service and Google Map SDK version.
72856ea HEAD@{30}: commit: WIP
8441b05 HEAD@{31}: commit: Add a reference to Google Map SDK.
8527033 HEAD@{32}: commit: Change the color of restaurant icons.
af26a96 HEAD@{33}: commit: Fix a typo.
6fb2ba7 HEAD@{34}: commit: Render restaurants the map.
70ef834 HEAD@{35}: commit (initial): Initial commit
```

Every entry of the `reflog` command starts with the commit `HEAD` is point to after the operation, then a unique identifier. In this example we have `HEAD@{0}` for the first entry, `HEAD@{1}` for the second entry, and so on. In front of the identifier we see what happened.

| Commit ID | Identifier | Message                 |
| :-------: | :--------: | :---------------------- |
|  645357e  |  HEAD@{1}  | reset: moving to HEAD~4 |

So we can revert any of theses operations to recover lost commits. In this example the operation `HEAD@{0}` is resetting `HEAD~1`. We can recover the lost commit with the `reset` command. We can use the identifier or the the commit ID

History before:

```zsh
❯ git log --all --oneline --graph
* 088455d (HEAD -> master) .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
```

```zsh
❯ git reset --hard HEAD@{1}
HEAD is now at b7ed3ee Revert last 4 commits
```

History after:

```zsh
❯ git log --all  --oneline --graph
* b7ed3ee (HEAD -> master) Revert last 4 commits
* 088455d .
* f666091 WIP
* 111bd75 Update terms of service and Google Map SDK version.
* 72856ea WIP
* 8441b05 Add a reference to Google Map SDK.
* 8527033 Change the color of restaurant icons.
* af26a96 Fix a typo.
* 6fb2ba7 Render restaurants the map.
* 70ef834 Initial commit
````
