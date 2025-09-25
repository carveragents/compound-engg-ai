---
allowed-tools: Read, Write, Edit, Grep, Bash(git merge:*), Bash(git push:*), Bash(git branch -d:*)
description: Merge the current working branch into main, push to origin, and cleanup
---

<!-- Some parts of this command are specific to Claude Code,
especially folder locations, front matter, and argument passing.
Modify as needed if using with other coding agents. -->


## What This Command Does

0. If there are uncommitted changes on the branch, STOP and inform the user. Don't do anything else.

Otherwise:
1. Merge the current working branch into main (or master)
2. Push main (or master) to origin
3. Delete the working feature branch
