#git
#github

[Git comment writing best practices](https://www.conventionalcommits.org/en/v1.0.0/#summary)
#git-commit-message


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

- **git branch -a**       (to list all the local and remote branches)
- **git branch -d “branch_name”** (delete a local branch)
- **git push origin -d “branch_name”** ( delete a remote branch) 


Good video to understand git merge rebase and squash
- https://www.youtube.com/watch?v=0chZFIZLR_0
- https://www.youtube.com/watch?v=MxncLUOLdAQ
	- git Merge
	- git rebase
	- squash commit
![[Screenshot 2023-09-11 at 11.41.07 AM.png]]


- ##### Keeping a feature branch up to the date with Main is crucial , we can do that with git merge or git rebase

	- Git Merge pulls in the latest changes from main into the feature branch , creating a new merge commit in the process, its like tying two branches with a knot.
	- ![[Screenshot 2023-09-11 at 11.44.31 AM.png]]
	- Git rebase changes the base of a feature branch to the latest commit on main and then we place our changes from there it gives us a clean straightforward commit history.
	- 1. initially ![[Screenshot 2023-09-11 at 11.45.28 AM.png]]
	- 2. After rebase![[Screenshot 2023-09-11 at 11.46.44 AM.png]]


- ##### Once we've finished developing the feature we'll want to get the feature branch back to the main we can achieve that with git merge or git rebase and forward merge or by squash commits ![[Screenshot 2023-09-11 at 11.49.06 AM.png]]
	- git merge will create a new merged commit that ties together the histories of both(it can make history a bit messy) ![[Screenshot 2023-09-11 at 11.50.59 AM.png]]
	- we can use git rebase to move our feature branches changes onto the tip of Main and then perform a fast forward merge ![[Screenshot 2023-09-11 at 11.54.47 AM.png]]
	- last option is squash commit with squashing all the feature branch commits into a single commit when merged into main , this keeps the mains history linear like rebasing while still creating a single merge commit but remember we loose fine details of individual feature commits in the main branch commits history.![[Screenshot 2023-09-11 at 11.56.56 AM.png]] ![[Screenshot 2023-09-11 at 11.58.02 AM.png]]


 ![[Screenshot 2023-09-11 at 11.59.44 AM.png]]