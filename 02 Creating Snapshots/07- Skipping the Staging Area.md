# 07- Skipping the Staging Area

We don't always have to stage our changes before committing. But do this only if we are sure our changes do not need to be reviewed.

To do this we run the command `git commit -a -m "My message"`, we supply the flag `-a`, that means all modified files. Or we can use `git commit -am "My message"`, combining `-a -m`.