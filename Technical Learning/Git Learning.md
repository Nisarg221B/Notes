#git
#github


**Git stages :** 

-   Untracked 
-   Staged 
-   Commit  

-   **git status** 
-   **git add  .                ( stage all the untracked files in the current directory to the staging area)**
-   **git add filename  ( stage the untracked file )**
-   **git restore  - - staged  .       ( bring all the files in staging area to untrack )**
-   **git commit -m “ message “**     
-   **git log          ( to show the history of versions )** 
-   **git reset hash**
-   **git branch “name”** 
-   **git checkout “name”    ( to move the head pointer to “name” branch)**
-   **fork and branch** 
-   **generally origin is the name assigned to the personal-site link associated with your original project . or of your own account.**
-   **else upstream is the name assigned if the project is someone else’s and you have forked it.**

- **git remote -v**
```git
git remote set-url origin https://Nisarg221B<Token>@github.com/Nisarg221B/FaceSwap.git
```

**how to keep your origin and fork up to the date**

-   **git checkout main**
-   **git fetch —all —prune**
-   **git reset —hard upstream/main**
-   **git push origin main**
**or** 
-   **git pull upstream main**

**Stashing**

- **git stash**
- **git stash apply**
- **git stash apply stash@{2} 
- **git stash drop stash@{0} ****(to remove from stash list -- in this case stash 0)
- **git stash pop stash@{1} **(to apply selected stash and drop it from stash list)( git stash apply && git stash drop ) 

- **git stash list**
- **git stash clear** 


Good video to understand git merge rebase and squash
https://www.youtube.com/watch?v=0chZFIZLR_0
https://www.youtube.com/watch?v=MxncLUOLdAQ


- **git branch -a**       (to list all the local and remote branches)
- **git branch -d “branch_name”** (delete a local branch)
- **git push origin -d “branch_name”** ( delete a remote branch) 
