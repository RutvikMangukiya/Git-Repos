
### **1. Creating Branches**
- `git branch <branch-name>` → Create a new branch.
- `git checkout -b <branch-name>` → Create and switch to a new branch.

### **2. Viewing Branches**
- `git branch` → List all local branches.
- `git branch -r` → List all remote branches.
- `git branch -a` → List both local and remote branches.

### **3. Switching Branches**
- `git checkout <branch-name>` → Switch to a branch (older method).
- `git switch <branch-name>` → Switch to a branch (newer method).
- `git switch -c <branch-name>` → Create and switch to a new branch.

### **4. Renaming Branches**
- `git branch -m <new-branch-name>` → Rename the current branch.
- `git branch -m <old-branch-name> <new-branch-name>` → Rename a specific branch.

### **5. Deleting Branches**
- `git branch -d <branch-name>` → Delete a local branch (safe delete).
- `git branch -D <branch-name>` → Force delete a local branch.
- `git push origin --delete <branch-name>` → Delete a remote branch.

### **6. Merging Branches**
- `git merge <branch-name>` → Merge another branch into the current branch.
- `git merge --no-ff <branch-name>` → Merge with a commit history.
- `git merge --abort` → Abort a merge if there are conflicts.
    git pull --rebase origin main -> to fetch the remote changes
    git rebase origin/main -> apply remote changes to local main
### **7. Rebasing Branches**
- `git rebase <branch-name>` → Rebase the current branch onto another branch.
- `git rebase --abort` → Abort an ongoing rebase.
- `git rebase --continue` → Continue after resolving conflicts.
- `git rebase --skip` -> skip the commit and move forward
### **8. Tracking Remote Branches**
- `git branch -vv` → Show tracking branches.
- `git checkout --track origin/<branch-name>` → Create a local branch tracking a remote one.
- `git push -u origin <branch-name>` → Push and track a new branch.

### **9. Stashing Work Before Switching Branches**
- `git stash` → Save uncommitted changes temporarily.
- `git stash pop` → Apply the stashed changes back.
- `git stash list` → View all stashed changes.
- `git stash drop` → Delete the last stashed changes.

### **10. Checking Branch Logs**
- `git log --oneline --graph --all --decorate` → View a graphical history of all branches.


### **11. Comparing Branches**
- `git diff <branch1>..<branch2>` → Show the difference between two branches.
- `git log <branch1>..<branch2>` → Show commits in `<branch2>` that are not in `<branch1>`.

### **12. Deleting Remote-Tracking Branches**
- `git fetch -p` → Remove deleted remote branches from local tracking.

### **13. Resetting Branches**
- `git reset --hard <commit-hash>` → Reset the current branch to a specific commit.
- `git reset --soft <commit-hash>` → Move the branch to a commit but keep changes staged.

### **14. Overwriting a Branch**
- `git branch -f <branch-name> <commit-hash>` → Force update a branch to a specific commit.

### **15. Working with Upstream Branches**
- `git branch --set-upstream-to=origin/<branch-name>` → Set an upstream (tracking) branch.

### **16. Moving Commits to Another Branch**
- `git cherry-pick <commit-hash>` → Apply a specific commit to the current branch.

### **17. Handling Merging Issues**
- `git merge --squash <branch-name>` → Merge without keeping commit history.
- `git merge --no-commit <branch-name>` → Merge but don’t create a merge commit yet.


### **18. Undoing Changes in Branches**
- `git reset --hard origin/<branch-name>` → Reset your branch to match the remote branch.
- `git reset --mixed HEAD~1`  -> Undo the Last Commit (And Unstage Changes)
- `git reset --soft HEAD~1` -> undo the last commit with keep trac
- `git checkout -b <new-branch> <commit-hash>` → Create a branch from a specific commit.
- `git reflog` → Show the history of HEAD changes (useful to recover lost branches).

### **19. Working with Detached HEAD State**
- `git checkout <commit-hash>` → Move to a specific commit (detached HEAD mode).
- `git checkout -b <new-branch>` → Create a new branch from the detached state.

### **20. Deleting Merged and Unmerged Branches**
- `git branch --merged` → List branches that have been merged into the current branch.
- `git branch --no-merged` → List branches that haven’t been merged yet.

### **21. Cleaning Up Local Branches**
- `git branch --sort=-committerdate` → List branches sorted by latest commit.
- `git branch -vv | grep ': gone]' | awk '{print $1}' | xargs git branch -D` → Delete local branches that no longer exist on the remote.

### **22. Synchronizing Branches with Remote**
- `git pull --rebase origin <branch-name>` → Pull changes but keep a clean history.
- `git push --force-with-lease` → Force push safely (prevents overwriting someone else’s changes).

---

### **23. Checking Out a Remote Branch Without Creating a Local One**
- `git fetch origin <branch-name>` → Fetch a remote branch without switching.
- `git checkout origin/<branch-name>` → View a remote branch without creating a local one.

---

### **24. Force Updating a Branch**
- `git branch -f <branch-name> <commit-hash>` → Move a branch to a specific commit **without switching to it**.

---

### **25. Squashing and Cleaning Up Commits**
- `git rebase -i HEAD~<number-of-commits>` → Interactive rebase to squash multiple commits.
- `git commit --amend` → Modify the last commit without creating a new one.

---

### **26. Viewing and Managing Branch Points**
- `git merge-base <branch1> <branch2>` → Find the common ancestor of two branches.
- `git show-branch` → Show branches and their relationships.

---

### **27. Temporarily Switching Contexts**
- `git worktree add ../new-dir <branch-name>` → Work on multiple branches simultaneously in different directories.

---

### **28. Advanced Branch Filtering**
- `git branch --contains <commit-hash>` → Show branches that contain a specific commit.
- `git branch --no-contains <commit-hash>` → Show branches that don’t contain a commit.

---

### **29. Reviving a Deleted Branch**
- `git reflog` → Find the last commit of a deleted branch.
- `git checkout -b <branch-name> <commit-hash>` → Restore the deleted branch.

---

### **30. Debugging Branch Issues**
- `git fsck --full` → Check for issues in your repository.
- `git bisect start` → Start a binary search to find a bug in your commits.

---
### **31. Find last commit on branch**
- `git rev-parse ` -> Find last commit-Hash on branch
- `git log -1 --oneline Branch-name`  -> Find last commit on branch
