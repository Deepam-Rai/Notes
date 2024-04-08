# Uploading local repo to github

First create a new repo in github and get the repo url(`code`>>`https`>> clone using web url).  
Then,  
```shell
# initialize git in the main project folder
git init -b main  # setting default branch name "main"

# stage changes for commit
git stage .

# commit the changes
git commit -m "Commit message"

# add remote repository
git add origin <REMOTE-URL>

# push the commit to remote origin
git push -u -f origin main
```

----
