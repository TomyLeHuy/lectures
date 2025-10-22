# Lecture Project & Git Workflow

This document outlines the current project status and the mandatory Git workflow for all contributors.

## Current Status
* The `development` branch is now clean and stable, serving as the base for all new work.

---

## Git Workflow: Merge-Down, Merge-Up

To keep our codebase clean, minimize merge conflicts, and maintain a stable `development` branch. I appeal to all group members to adhere to this standard "merge-down, merge-up" practice. 

### 1. Create Your Feature Branch

Always make sure your local `development` branch is up-to-date *before* creating a new feature branch.

**Naming Convention:** Please adhere to the `feature/your-feature-name` format.

```bash
# 1. Switch to the development branch
git checkout development

# 2. Pull the latest changes
git pull origin development

# 3. Create your new feature branch
git checkout -b feature/your-feature-name

# 4. After you are done with your feature, push your branch to origin
git add .
git commit -m "Your commit message"
git push origin feature/your-feature-name
```

### 2. Update Your Branch Before Merging (Merge-Down)
Before you create a pull request (PR) to merge your feature back into `development`, you must first pull the latest changes from `development` into your feature branch.

This crucial step ensures you resolve any and all conflicts locally on your branch first.

```bash
# 1. Switch back to development and pull the latest changes
git checkout development
git pull origin development

# 2. Switch back to your feature branch
git checkout feature/your-feature-name

# 3. Merge the updated development branch into your feature branch
git merge development

# 4. --- IMPORTANT ---
# Resolve any merge conflicts locally now!
# Once resolved, commit the merge.
```

### 3. Merge Your Feature into development (Merge-Up)
Once your feature is complete, tested, and you have successfully merged the latest `development` branch into it (Step 2), you can proceed to create a pull request to merge your feature branch into `development.

### Rationale
Following this workflow is essential for maintaining a structured development process and a consistently working code base while adding new features. This practice is in the best interest of all team members and the project's progress.