## Git Branches (Continued)
- One project will have one GitHub repository.
- Branches are used to maintain multiple code bases.
- Using branches team members can do their work parallelly.
## Branch merging
- The process of merging changes from one branch to another branch is called Branch merging.
- We use Pull Request for branch merging.
  ### Steps to do branch merging
  - Create feature branch from main branch
  - Clone feature branch
  - Create new file in feature branch then commit and push to central repo
  - Go to repository then create pull request to merge feature branch changes to main branch
  - Note: Once feature branch changes are merged to main branch then we can delete feature branch if required
- What is  `.gitignore`?
- This .gitignore is used to configure the files or folder which we want to ignore from our commits.
- The files and folder which are not required to commit to central repository those feelings we can configure in .gitignore file.
- In maven project 'target' folder will be available which is not required to commit to central repository.
## Git Merge vs Git rebase
- Both command does the same work to merge changes from one branch to another branch.
- Git merge : It will preserve all the commit history of the developer.
- Git rebase : It doesn't give commit history what changes are done by developers.
- When we are working on particular sprint and we want to merge changes from one branch to another branch then we will use 'git merge' command.
- Once sprint-1 is delivered then we want to take latest code of sprint-1 to start sprint-2 development.In this scenario we don't need commit history so we used 'git rebase' command.
  
![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/3f597af9-f058-4880-9439-eaae1e43454b)

- Master branch created
- Created m1.txt in master and commit it
- From master create a feature branch
- Switch to feature branch
- Create f1.txt in feature and commit it
- Note: Master contain m1.txt & Feature contain m1.txt and f1.txt
- Switch to master branch
- Create m2.txt in master and commit it
- Note: Master contain m1.txt and m2.txt & Feature contain m1.txt and f1.txt
- Now Merge master branch to feature branch.
