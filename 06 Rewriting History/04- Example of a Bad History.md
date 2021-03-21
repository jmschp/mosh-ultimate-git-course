# 04- Example of a Bad History

As an example of bad history:

```zsh
❯ git log --oneline --graph
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

Commit:

- `6fb2ba7 Render restaurants the map.` -> Wording issue should be `"...restaurants on the map."``
- `af26a96 Fix a typo.` -> We shouldn't have a typo in the first place, commits like these pollute the history. So we can combine them with other commit.
- `8527033 Change the color of restaurant icons.` -> This part of the of the same line of work in the restaurants, So all this commits should be combined.
- `8441b05 Add a reference to Google Map SDK.` -> The problem here is that if we checkout commit `6fb2ba7`, our application is not going to work, because the Google Map SD reference comes afterwards. We should either move this commit down before `6fb2ba7`, or combine both commits.
- `72856ea WIP` -> A "Work In Progress" commit it is just a noisy commit, we Should either drop it, change the message or combine it.
- `111bd75 Update terms of service and Google Map SDK version.` -> Ideally we should separate these commit in tow commits, Because updating terms of service, as nothing to do with updating google map SDK.
- `088455d (HEAD -> master) .` -> A mysterious message commit, we should either drop it or change this message.
