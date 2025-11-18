# Git Workshop

## What is Git?

Git is a version control system that tracks changes to your code over time. It allows you to:
- Save different versions of your project
- Collaborate with other developers
- Revert to previous versions if needed
- Work on different features simultaneously

## Create a New Repository
```
git init                   # Initialize a new git repository
git clone <url>            # Clone an existing repository
```

## Check Status & History
```
git status                 # See which files have changed
git log                    # View commit history
git diff                   # See differences between working directory and staging area
```

### Stage and Commit
```
git add <file>             # Stage specific file
git add .                  # Stage all changes
git commit -m "message"    # Save changes with a description
```

### Handle branches
```
git branch                 # List all branches
git branch <branch-name>   # Create new branch
git checkout <branch-name> # Switch to branch
git checkout -b <branch>   # Create and switch to new branch
git merge <branch-name>    # Merge branch into current branch
git branch -d <branch>     # Delete branch
```

### Remote Repositories
```
git remote add origin <url>     # Connect to remote repository
git push origin <branch>        # Upload changes to remote
git pull origin <branch>        # Download changes from remote
git fetch                       # Get updates without merging
```

### Undo Changes
```
git restore <file>             # Discard changes in working directory
git restore --staged <file>    # Unstage file
git revert <commit>            # Create new commit that undoes changes
git reset HEAD~1               # Undo last commit (keep changes)
```

### Stash Changes
```
git stash                           # Save current changes
git stash pop                       # Restore most recent stash
git stash list                      # View all stashes
git stash drop                      # Delete a stash
```

### Common Workflow
1. Create or clone a repository 
2. Make changes to files 
3. Stage changes: `git add .`
4. Commit changes: `git commit -m "description"`
5. Push to remote: `git push origin main`

### Commit Messages Best Practices
- Use present tense: "Add feature" instead of "Added feature"
- Be specific about what changed: "Fix login button alignment" not "Fix bug"
- Keep it concise but informative 
- Example: `git commit -m "Add user authentication to login page"`

## Pull Requests

### What is a Pull Request?

A pull request (PR) is a way to propose changes to a project. It allows you to:
- Review code before merging
- Discuss changes with team members
- Run automated tests
- Keep the main branch stable

### Pull Request Workflow

In order to create a pull request on GitHub:
1. Go to your repository 
2. Click "New Pull Request"
3. Select your branch and main branch 
4. Add title and description 
5. Request reviewers 
6. Wait for approval 
7. Merge when ready

### Common PR Commands
```
git fetch origin                      # Get latest updates
git rebase origin/main                # Update your branch with main
git push origin feature/my-feature    # Push updates to PR
```

### After Merge Commands
```
git checkout main                     # Switch to main branch
git pull origin main                  # Get merged changes
git branch -d feature/my-feature      # Delete local branch
git push origin --delete feature/my-feature  # Delete remote branch
```


## Other Tips

### Merge Conflicts
Merge conflicts occur when Git can't automatically merge changes. Here's how to handle them:
```
git fetch origin                    # Get latest updates
git merge origin/main               # Attempt to merge
# Git will mark conflicting files
# Edit the conflicted files manually
# Look for markers: <<<<<<<, =======, >>>>>>>
git add <resolved-file>             # Stage resolved files
git commit -m "Resolve merge conflict"
```

### .gitignore
Create a .gitignore file in your repository root to exclude files from being tracked:
```
node_modules/
.env
.DS_Store
*.log
*.tmp
__pycache__/
.vscode/
```