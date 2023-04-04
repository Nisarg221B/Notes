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
-   **Token - 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    — Nisarg00**
-   **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    — Nisarg221B**
-   **fork and branch** 
-   **generally origin is the name assigned to the personal-site link associated with your original project . or of your own account.**
-   **else upstream is the name assigned if the project is someone else’s and you have forked it.**

git remote set-url origin https://Nisarg221B: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@github.com/Nisarg221B/FaceSwap.git

**how to keep your origin and fork up to the date**

-   **git checkout main**
-   **git fetch —all —prune**
-   **git reset —hard upstream/main**
-   **git push origin main**
**or** 
-   **git pull upstream main**