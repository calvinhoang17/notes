### GIT 

Setup 
```
git config --global user.name "NAME"
git config --global user.email "EMAIL" 
```
Initialize Git on working directory
```
git init
```
Shows repo status 
```
git status
```
Show commit log
```
git log
```
## Staging Environment
Add file to staging environment
```
git add [FILE]
git add --all [FILE]
```
Stage ➝ Commit
```
git commit -m "MESSAGE"
```
To skip staging
```
git commit -a -m "MESSAGE"
```

## Branches
```
git branch [NAME]
```
Move to another branch 
```
git checkout [BRANCHNAME]
```
Merge Branches
```
git merge [BRANCHNAME]
```
Delete a branch
```
git branch -d [BRANCHNAME]
```

## Pull from GitHub
Gets all change history 
```
git fetch origin
```
Show differences between local main and orgin/main
```
git diff origin/master
```
Merge branches
```
git merge origin/main
```
Pull (fetch + merge)
```
git pull origin
```

##Github Cloning repo
```
git clone [LINK]
```
