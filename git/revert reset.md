
> **revert:** create a commit with the reverse patch to cancel it out. This way you don't rewrite any history.


To  move back to previous commit:
```shell
# move to previous commit and get rid of all changes since then
git reset --hard <commit id>

# save the current work; move back; load the stashed work
git stash
git reset --hard <commit id>
git stash pop
```

Temporarily switch to different commit:
```shell
git checkout <commit id>
```

Create a branch from the different commit:
```shell
git checkout -b <new_branch_name> <commit_id>
```

