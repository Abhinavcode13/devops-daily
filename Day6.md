## Repository Tools
### Working with Github
- Login into your github account with your credentials
- Create Repository in Github
- Note: Repository is used to store project source code. Every project will have one repository.
- When we create a repository, unique URL is generated with Repository name.
- All the employees will connect to repository using this URL.
- We can have 2 types repository in Github
  1. Public repository
  2. Private repository
- Public repository means everybody can access but we can choose who can modify the repository.
- Private repository means we will choose who can access and who can modify the repo.

### Working with Git bash (Git client software)
- Git bash is used as a Git Client software.
- `git help` - It is used to show all the details of the most commonly used git commands.
- `git help clone` - Opens the documentation page of git bash commands.
- `git config --global user.email "user-email"` - To configure the email of user.
- `git config --global user.name "user-name"` - To configure the name of user.
- `git clone` - To clone/download git repository from Github.
  1. Syntax: $ git clone git-url
- `git init` - To initalize our folder as a git working tree.
- `git status` - It will display staged , un-staged and un-tracked files.
  1. Syntax: $ git status
  2. Staged files: The files which are added for commit.
  3. Un-Staged files: The files which are modifies but not added for commit.
  4. Un-tracked files: Newly created files.
  5. Note: To commit a file(s), we should add the files to staging area first.
- `git add` - It is used to add files to staging area
  1. Syntax: $ git add .
  2. $ git add file-name
- `git commit` - It is used to commit staged files to git local repository
  1. Syntax: $ git commit -m 'reason for commit'
  ### Steps to push code to central repository
  1. Create a public repo in GitHub : $ git clone 'repo-url'
  2. Navigate to repository folder
  3. Create one file in repository folder : $ touch test.java
  4. Check status of file : $ git status
  5. Add file to staging area : $ git add .
  6. Commit file to git local epository : $ git commit -m 'commit-message'
  7. Push file from git local repo to git central repo : $ git push
  8. Note: If you are doing git push for first time it will ask for Github credentials.
- `git remote` -
- `git push` -
- `git pull` -
- `git restore` -
- `git fetch` -
- `git branch` -
- `git merge` -
- `git rebase` -
- `git rm` -
- `git log` -
- `git fork` -
