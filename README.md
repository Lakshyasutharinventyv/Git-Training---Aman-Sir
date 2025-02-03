# Git Workflow Visualization

This repository demonstrates a simple Git workflow involving **branching, merging, and tagging**. The steps below outline the commands and actions performed to create the state of the repository as shown in the visualization.

---

## 🖼️ Git Workflow Diagram
![Git Workflow](https://github.com/user-attachments/assets/89ac7ada-7d50-43eb-b1b8-cb76d5522b38)

---

## 📌 Branch Structure
- **`prod`** → Production branch, created from `master`.
- **`hotfix`** → Hotfix branch, created from `prod`.
- **`feature1`** → Feature development branch, created from `release1`.
- **`release1`** → Release branch, created from `prod`.

---

## ⚡ Key Git Actions

### 🔹 Rename `master` to `prod`
```sh
git branch -m master prod
```

### 🔹 Commit changes
```sh
git commit -m "<commit message>"
```

### 🔹 Create & switch to `feature1`
```sh
git checkout -b feature1
```

### 🔹 Commit changes to `feature1`
```sh
git commit -m "Feature 1 commit 1"
git commit -m "Feature 1 commit 2"
```

### 🔹 Switch to `prod` & create `hotfix`
```sh
git checkout prod
git checkout -b hotfix
```

### 🔹 Commit changes to `hotfix`
```sh
git commit -m "Hotfix commit 1"
git commit -m "Hotfix commit 2"
```

### 🔹 Merge `prod` into `hotfix` (No changes)
```sh
git merge prod
```

### 🔹 List branches
```sh
git branch
```
**Output:**
```
  prod
  master
  feature1
* hotfix
```

### 🔹 Merge `hotfix` into `prod` (Fast-forward merge)
```sh
git checkout prod
git merge hotfix
```

### 🔹 Undo last two commits (if needed)
```sh
git reset --hard HEAD~1
git reset --hard HEAD~1
```

### 🔹 Create `releasef1` & merge `feature1`
```sh
git checkout -b releasef1
git merge feature1
```

### 🔹 Merge `releasef1` into `prod`
```sh
git checkout prod
git merge releasef1
```

### 🔹 Final Branch List
```sh
git branch
```
**Output:**
```
  master
  feature1
  releasef1
* prod
  hotfix
```

### 🔹 Merge `hotfix` into `prod`
```sh
git merge hotfix
```

> **Note:** If you intended to format a commit message, use:
> ```sh
> git commit -m "Format README"
> ```

---

## 🚀 Final State
- `prod` contains all changes from `hotfix` and `release1`, with a tagged commit (`PM`).
- `release1` includes merged changes from `feature1`.
- `feature1` and `hotfix` remain independent feature branches.

### 📌 Git Visualization
![Pull Request Practice](https://github.com/user-attachments/assets/7e71c1f7-0719-406b-ace1-13d32b8685eb)

### 🔧 Branch Pull Request Settings
![image](https://github.com/user-attachments/assets/9dd82709-5804-4c2d-8b88-cbc2e7e99964)

---

### ✅ Best Practices
- **Use meaningful commit messages** 📝
- **Keep feature branches isolated until complete** 🔀
- **Tag releases and significant merges** 🏷️
- **Regularly update `prod` from `release` and `hotfix`** 🔄

Enjoy version control with Git! 🚀
