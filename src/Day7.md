## Continued
- `git stash` - When we are working on one task, suddenly we may encounter any other priority task which has to be done first.
- Usecase :
     - Manager assigned task-id : 101
     - Person A is working on task-id : 101 and suddenly manager call him to shift his work to another priority task which is task-id : 102
     - When manager asked to do task-id : 102 meanwhile task-id : 101 was partially completed and hence we can't push partial changes to repo because it may break current functionality.
     - Also we can't delete those implemented changes.
     - In this scenario we go for git stash option.
     - Git Stash is used to save working tree changes to temporary location and make working tree clean.
     - After priority work completed we can get stashed changes back using `$ git stash apply`.

  ![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/c0a9eb38-9f37-4ef5-b60f-c7f1b05e6dfe)

## Git Branches
- Branches are used to maintain seperate code bases for the project.
- In Git repository we can create multiple branches.
- Examples :
  - Main
  - Develop
  - QA
  - Release
  - Research
- To clone a particular branch in git repo we will used command as : `$ git clone -b branch-name repo-url`
