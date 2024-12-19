
> **revert:** create a commit with the reverse patch to cancel it out. This way you don't rewrite any history.


Un-stage staged files (Undoing `git stage .`):
```shell
git reset
```


Restore un-staged changes(Delete all updates after last commit):
```shell
git restore <file_path>
```


Undo last local commit:
```shell
git reset HEAD~
```


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

Remove all local commits and sync with remote origin:
```shell
git reset --hard origin/master
```


----

Get/update just a file from another branch:
```shell
git checkout branch_where_want_to_update
git checkout branch_from_where_want_to_update file_name
```

## ignoring
---
Start ignoring file that has been committed in past:
```shell
echo file > .gitignore
git rm --cached file
# nowonwards the file will be ignored
git commit -m "Started ignoring file"
```

---
Start ignoring local changes made to a file:
```shell
git update-index --assume-unchanged path/to/file
```

Stop ignoring changes:
```shell
git update-index --no-assume-unchanged path/to/file
```