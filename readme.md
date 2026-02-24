![](Git%20Session_media/image1.png)
![](Git%20Session_media/image3.png)

# Git & Github Session Reference

<img src="Git%20Session_media/image2.png" width="100%"/>

## Setup git on your development machine

- Install git
- `git --version` # Display git version

## Create a signature for your commits

- `git config --global user.name "Your Name"` # Set username.
- `git config --global user.email "your_email@example.com"` # Set email.
- `git config --global --list` # View your current signature.

## Working with git on your local machine

- `git init` # Initialize a new repository in the current directory.
- `git add .` # Add all files to the staging area to be included in the next commit. It becomes tracked.
- `git commit -m "commit message"` # Create a new commit with the changes in the staging area.
- `git status` # Check to see which files have changed and their tracking status.
- `git log` # View the commit history of the repository.
- `git diff <commit1> <commit2>` # Show the differences between two commits.

## Time travel and manipulation with Git

- `git branch <branch_name>` # Create a new branch in the timeline.
- `git branch` # List all branches in the repository.
- `git checkout <branch_name>` # Switch to a different branch.
- `git checkout <commit_hash>` # Move to a specific commit in the commit history. (Readonly)
- `git merge <branch_name>` # Merge changes from another branch into the current branch.

## Conflict Resolution

- When there is a conflict merging changes, Git will mark conflicting sections inside each file with markers `<<<<<<<`, `=======`, and `>>>>>>>`.
- Use `git status` to see the list of conflicted files.
- Remove the conflict markers and decide which changes to keep and modify the file accordingly.
- Stage and commit changes.

## Working with an existing git remote repo

- Clone remote repo on your local machine: `git clone <repo_uri>`
- `git pull <remote_name> <branch_name>` # Fetch and merge changes into the current branch.
- `git push <remote_name> <branch_name>` # Push your local commits to the remote repo.
- `git remote -v` # Show the URLs of the remote repositories.
- `git remote add <remote_name> <repository_url>` # Add a new remote repository.

## Setup a new remote repo on a network shared folder

- Create a folder on the network.
- Ensure collaborators have sufficient access privileges on the folder.
- `cd` to the folder and run: `git init --bare` # Initialize a repo that is setup for collaboration, but no working directory (project files will not be directly accessible).
- Clone repo on your local machine: `git clone <repo_uri>` # e.g. `git clone file:////server/share/repo`

## Setup a new remote repo on a web-based hosting service

- Signup on GitHub or any similar service.
- Create a private or public repository on the service.
- Clone repo on your local machine: `git clone <repo_url>` # Authenticate if prompted.

## Collaboration workflow on a web-based hosting service

- **Direct Model:** `Clone → Branch → Commit → Push → PR → Maintainers Review/Merge → Delete branch` (used when you have write access).
- **Fork Model:** `Fork → Clone fork → Branch → Commit → Push → PR to upstream → Maintainers Review/Merge → Delete branch` (used when you don’t have write access).
- As a best practice, in Settings → Branch protection rules, require Pull Request reviews and disable direct pushes to main so everyone (including owner) follows the PR workflow.

<br/>

<img src="Git%20Session_media/image4.png" width="100%"/>
