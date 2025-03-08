# How to Push Files to a Newly Created Git Repository

This guide will help you initialize a Git repository, add files, and push them to a remote repository like GitHub.

---

## Steps to Push Files to a Git Repository

1. **Initialize Git (if not already initialized)**  
   Before pushing your files, ensure your project is a Git repository. Navigate to your project folder and run:
   
   ```sh
   git init
   ```
   This initializes a new Git repository in your project directory.

2. **Add the Remote Repository**  
   If you haven't already created a repository on GitHub, GitLab, or another platform, do that first. Then, link your local repository to the remote one using the following command:
   
   ```sh
   git remote add origin <repository-URL>
   ```
   Example:
   
   ```sh
   git remote add origin https://github.com/your-username/your-repo.git
   ```
   This command tells Git where to push your code.

3. **Add Files and Commit**  
   Now, add your project files to Git and commit them:
   
   ```sh
   git add .
   ```
   The `git add .` command stages all changes (new files, modifications, and deletions).
   
   Next, commit your changes with a message:
   
   ```sh
   git commit -m "Initial commit"
   ```
   A commit acts like a checkpoint, saving your changes locally.

4. **Push to the Remote Repository**  
   If this is your first push, you may need to set the branch name to match the remote repository (e.g., `main` or `master`).
   
   Rename the branch to `main` if necessary:
   
   ```sh
   git branch -M main
   ```
   
   Finally, push the changes to the remote repository:
   
   ```sh
   git push -u origin main
   ```
   The `-u` flag sets `origin main` as the default remote branch for future pushes.

---

## Resolving "Rejected Push" Error

If you encounter an error like:

```sh
! [rejected]        main -> main (fetch first)
error: failed to push some refs
```

It means the remote repository already contains commits that your local repository doesn't have. To fix this:

1. **Fetch and Merge Remote Changes**  
   First, pull the latest changes from the remote repository and merge them:
   
   ```sh
   git pull origin main --rebase
   ```
   If there are conflicts, resolve them manually, then add and commit the resolved files.

2. **Push Your Changes**  
   After pulling successfully, push your local changes:
   
   ```sh
   git push origin main
   ```
   
   If you want to overwrite the remote repository (⚠ **this will delete remote changes**), use:
   
   ```sh
   git push --force origin main
   ```

Your files should now be successfully uploaded to the remote repository! 🚀
