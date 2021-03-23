# 13- Squashing Commits

## Squash rebase

To squash commits together we use the interactive `rebase` operation. In the rebase script we select the `squash` option only for the child commits, the parent commit keeps the `pick` option. All commits that need to be squash have to be in sequence, so if needed we can reorder them first.

```zsh
pick 098a4bc Render restaurants the map.
squash 0bf60fe Fix a typo.
squash dd8f07e Change the color of restaurant icons.
pick ba55176 Update terms of service and Google Map SDK version.
pick f820221 WIP
pick 65dbb96 .
```

In the above example commits `098a4bc`, `0bf60fe` and `dd8f07e`, will be combined together. After combined the commits, the rebase operation will open the default editor to edit the commit message.

## Fixup rebase

The `fixup` rebase option works like `squash` option, but instead of allowing us to edit the commit message, it will use the message form the parent squashed commit, in this case the message from commit `098a4bc`.

```zsh
pick 098a4bc Render restaurants the map.
pick fixup Fix a typo.
pick fixup Change the color of restaurant icons.
pick ba55176 Update terms of service and Google Map SDK version.
pick f820221 WIP
pick 65dbb96 .
```
