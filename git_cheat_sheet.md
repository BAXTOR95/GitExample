
# Git cheat sheet

## Different Use Cases

### INITIAL SETUP

- **git config --global user.name “[firstname lastname]”**
  - Sets a name identifiable for credit in version history. **Best practice**: Use your real name and make it consistent across your projects.
- **git config --global user.email “[valid-email]”**
  - Sets an email address associated with each commit. **Best practice**: Use the same email as your GitHub account for easy linking.

### SETUP & INIT

- **git init**
  - Initializes an existing directory as a Git repository. **Best practice**: Only do this in the root of your project to avoid nested repositories unless intended.
- **git clone [url]**
  - Creates a copy of an existing repository from a URL. **Best practice**: Use this to work on projects without starting from scratch.

### STAGE & SNAPSHOT

- **git status**
  - Shows modified files ready to be committed. **Best practice**: Check status before committing to avoid unnecessary files in the commit.
- **git add [file]**
  - Stages a file for the next commit. **Best practice**: Use `git add .` sparingly; review changes to avoid committing unrelated changes.
- **git reset [file]**
  - Unstages a file while retaining changes. **Best practice**: Use this to remove files accidentally staged.
- **git commit -m “[descriptive message]”**
  - Commits your staged content. **Best practice**: Write clear, descriptive commit messages.

### BRANCH & MERGE

- **git branch**
  - Lists all branches. **Best practice**: Regularly clean up old branches.
- **git branch [branch-name]**
  - Creates a new branch. **Best practice**: Use meaningful branch names related to the feature or fix.
- **git checkout [branch-name]**
  - Switches to another branch. **Best practice**: Keep your working directory clean to avoid conflicts when switching branches.
- **git merge [branch]**
  - Merges specified branch into the current one. **Best practice**: Resolve conflicts carefully, ensuring the code runs as expected.

### INSPECT & COMPARE

- **git log**
  - Shows the commit history. **Best practice**: Use this to understand the evolution of the project.
- **git diff**
  - Shows the difference between commits, commit and working tree, etc. **Best practice**: Review diffs before committing to catch mistakes.

### SHARE & UPDATE

- **git push [alias] [branch]**
  - Updates the remote branch with local commits. **Best practice**: Push regularly to keep the team updated.
- **git pull**
  - Updates the local branch with remote changes. **Best practice**: Pull before starting work to stay updated.

### REWRITE HISTORY

- **git rebase [branch]**
  - Applies commits of the current branch ahead of the specified one. **Best practice**: Use with caution, preferably on private branches.

### TEMPORARY COMMITS

- **git stash push -m "[message]"**
  - Stashes your changes with a custom message, making it easier to remember the purpose of the stash. **Best practice**: Use descriptive messages for your stashes to ease navigation through them.
- **git stash pop**
  - Applies the stashed changes back to your working directory and removes them from the stash list. **Best practice**: Ensure your working directory is clean to avoid conflicts when applying a stash.

### IGNORING PATTERNS

- **.gitignore**
  - The `.gitignore` file specifies intentionally untracked files that Git should ignore. **Best practice**: Include all temporary files, local configuration files, and files containing sensitive information (such as passwords or API keys) in `.gitignore`.
- **git config --global core.excludesfile [file]**
  - Sets up a global `.gitignore` file applicable to all your repositories. **Best practice**: Use this for files that should always be ignored, like system files or editor backup files.

Always aim for clear, descriptive actions (e.g., commit messages, branch names) to make collaboration and maintenance easier for everyone involved.

Building upon the foundational Git commands, let's delve into some more advanced commands and best practices to enhance your workflow and collaboration within your development team.

### TRACKING PATH CHANGES

- **git rm [file]**
  - Removes a file from the project and stages the removal for commit. **Best practice**: Use this command to ensure that file deletions are properly recorded in version history.
- **git rm --cached -r .**
  - Removes all files and directories from the Git index (staging area) without deleting them from the working directory. This is useful when you want to unstage all changes and start fresh, while keeping the files in your local directory. **Best practice**: Be cautious when using this command, as it permanently removes files from the index.
- **git mv [existing-path] [new-path]**
  - Moves or renames a file, directory, or symlink and stages the change. **Best practice**: Use `git mv` instead of moving files manually to keep the history intact.

### REWRITING HISTORY

- **git rebase [branch]**
  - Reapplies commits on top of another base tip. **Best practice**: Use rebase to keep your project history linear and easier to follow. Avoid rebasing public branches to prevent conflicts for other developers.
- **git reset --hard [commit]**
  - Resets the index and working tree to a specific commit, discarding all changes. **Best practice**: Be very cautious with this command, as it can lead to loss of work. Ensure you really want to discard changes before using it.

### COLLABORATIVE DEVELOPMENT

- **git fetch [alias]**
  - Downloads objects and refs from another repository. **Best practice**: Regularly fetch to stay updated with what's happening in the remote repository without merging the changes into your own branch.
- **git pull --rebase [remote]**
  - Fetches the remote's copy of the current branch and rebases it into the local copy. **Best practice**: Use this before pushing to minimize merge conflicts.

### ADVANCED MERGING

- **git merge --no-ff [branch]**
  - Creates a merge commit even if the merge resolves as a fast forward. **Best practice**: Use this to ensure that merges from feature branches create a commit, preserving the context of the feature work.

### USING TAGS

- **git tag [tagname]**
  - Marks specific points in history as important. Typically used for release points. **Best practice**: Use semantic versioning for your tags to keep track of different versions of your software.

### BEST PRACTICES SUMMARY

- **Commit Often, Push Regularly**: Small, frequent commits make it easier to understand changes and roll back if needed.
- **Use Branches Wisely**: Keep your master/main branch clean. Work on feature or bugfix branches.
- **Descriptive Commit Messages**: Write messages that clearly describe what the commit accomplishes.
- **Stay Synced**: Regularly pull changes from the remote, especially before starting new work or pushing your changes.
- **Review Before You Merge**: Use pull requests for code review, ensuring quality and consistency.
