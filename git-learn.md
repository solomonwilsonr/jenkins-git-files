# How to Push Files to a Newly Created Git Repository

This guide will help you initialize a Git repository, add files, and push them to a remote repository like GitHub.

---

## 1. Initialize Git (if not already initialized)

Before pushing your files, ensure your project is a Git repository.  
Navigate to your project folder and run:

```sh
git init


2. Add the Remote Repository
If you haven't already created a repository on GitHub, GitLab, or another platform, do that first.
Then, link your local repository to the remote one using the following command:

sh
Copy
Edit
git remote add origin <repository-URL>
For example:

sh
Copy
Edit
git remote add origin https://github.com/your-username/your-repo.git
This command tells Git where to push your code.

3. Add Files and Commit
Now, add your project files to Git and commit them:

sh
Copy
Edit
git add .
The git add . command stages all changes (new files, modifications, and deletions).

Next, commit your changes with a message:

sh
Copy
Edit
git commit -m "Initial commit"
A commit acts like a checkpoint, saving your changes locally.

4. Push to the Remote Repository
If this is your first push, you may need to set the branch name to match the remote repository (e.g., main or master).

Rename the branch to main if necessary:

sh
Copy
Edit
git branch -M main
Finally, push the changes to the remote repository:

sh
Copy
Edit
git push -u origin main
The -u flag sets origin main as the default remote branch for future pushes.

The error occurs because the remote repository already contains commits that your local repository doesn't have. To resolve this, follow these steps:

1. Fetch and Merge Remote Changes
First, pull the latest changes from the remote repository and merge them:

sh
Copy
Edit
git pull origin main --rebase
If there are conflicts, resolve them manually, then add and commit the resolved files.

2. Push Your Changes
After pulling successfully, push your local changes:

sh
Copy
Edit
git push origin main