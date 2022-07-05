
# Basics
---

#### Initialize staging area
```git
git init
```
<br>

#### Add to the staging area 

```git
git add "name of the file"
```
or use "." to add every file

```git
git add .
```  
<br>

#### Save copy of the file at the moment
```git
git commit -m "comment"
```
<br>

#### "add" and "commit" in the same command
```git
git commit -am "comment"
```
<br>

# Status and logs
---

#### Check status for files not in repository
```git
git status
```
<br>

#### Check status in simplified version
```git
git status -s
```
<br>

#### Check commit logs/changes in the repository
```git
git log
```
<br>

#### check commit log simplified
```git
git log --oneline
```
<br>

# Reset
---

#### Reset file to an expecif version in the log
```git
git reset --hard "code of the version"
```
<br>

# Github
---

#### Add github repository to local repository
```git
git remote add "name of remote" "link of repository"
```
<br>

#### Clone repository
```git
git clone "link of repository"
```
<br>

#### get changes from github repository
- ```git
    git pull
    ```
- ```git
    git pull "name of remote"
    ```
<br>

#### Transfer changes to github repository
- ```git
    git push
    ```
-  ```git
    git push "name of remote"
    ```
<br>

#### Transfer tags to github

```git
git push --tags
```
<br>


# Remote
---

#### Show remote names
```git
git remote
```
<br>

#### Show remote names, links, fetch and pull
```git
git remote -v
```
<br>

#### Rename the remote
```git
git remote rename "old name" "new name"
```
<br>

#### Remove remote
```git
git remote remove "name"
```
<br>

# Tags
---

#### Add a tag to the project
```git
git tag "version" -m "comment"
```
<br>


# Branches
---


#### Show current branch and all branches
```git
git branch
```
<br>

#### Create new branch
```git
git branch "branch name"
```
<br>

#### Move to different branch
```git
git checkout "branch name"
```
<br>

#### Merge branch to current branch
```git
git merge "branch name"
```
<br>

#### Delete branch
```git
git branch -d "branch name"
```
<br>
