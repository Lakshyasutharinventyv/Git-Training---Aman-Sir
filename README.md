# Git Workflow Visualization

This repository demonstrates a simple Git workflow involving branching, merging, and tagging. The steps below outline the commands and actions performed to create the state of the repository as shown in the visualization.
![image](https://github.com/user-attachments/assets/89ac7ada-7d50-43eb-b1b8-cb76d5522b38)

### Branches
- **prod**: A branch for production code, created from `master`.
- **hotfix**: A branch for hotfixes, created from `prod`.
- **feature1**: A branch for feature development, created from `release1`.
- **release1**: A release branch, created from `prod`.

### Key Actions
# Rename master branch to prod
git branch -m master prod

# Commit changes (empty commit message placeholder)
git commit -m ""

# Create and switch to a new branch 'feature1'
git checkout -b feature1

# Commit changes (empty commit message placeholders)
git commit -m ""
git commit -m ""

# Switch back to 'prod' branch
git checkout prod

# Create and switch to a new branch 'hotfix'
git checkout -b hotfix

# Commit changes (empty commit message placeholders)
git commit -m ""
git commit -m ""

# Attempt to merge 'prod' into 'hotfix' (Already up-to-date)
git merge prod

# List branches
git branch
# Output:
#   prod
#   master
#   feature1
# * hotfix

# Switch to 'prod' branch
git checkout prod

# Merge 'hotfix' into 'prod' (Fast-forward merge)
git merge hotfix

# Undo last commit twice using hard reset
git reset --hard HEAD~1
git reset --hard HEAD~1

# Create a new branch 'releasef1'
git checkout -b releasef1

# Merge 'feature1' into 'releasef1' (Fast-forward merge)
git merge feature1

# Switch back to 'prod' branch
git checkout prod

# Merge 'releasef1' into 'prod' (Fast-forward merge)
git merge releasef1

# List branches
git branch
# Output:
#   master
#   feature1
#   releasef1
# * prod
#   hotfix

# Merge 'hotfix' into 'prod' (Potential typo: 'format readme' is not a valid branch name)
git merge hotfix

## Final State
- The `prod` branch includes all changes from `hotfix` and `release1`, with a tagged commit (`PM`).
- The `release1` branch includes merged changes from `feature1`.
- `feature1` and `hotfix` are independent feature branches.

### Visualization
The graph illustrates the relationships between commits, branches, and tags, with `prod` as the current HEAD.


# Pull Request Practice
![image](https://github.com/user-attachments/assets/7e71c1f7-0719-406b-ace1-13d32b8685eb)






