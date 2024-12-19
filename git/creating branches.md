Creating branch from current:
```shell
git checkout -b <new-branch-name>
```

Creating branch from a commit hash:
```shell
# to get commit logs of current branch
git log

# to get one liner commit history and hashes
git log --oneline

git checkout -b <new-branch-name> <commit-hash>
```
This would create a new branch including git commits up-to that hash's commit.


