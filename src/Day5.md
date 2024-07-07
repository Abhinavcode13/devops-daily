## Continued

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/83a3fc28-022d-47db-a11e-267662c17567)

- When we add dependency in pom.xml maven will search for that dependency automatically in the local repository. If it is available it will add to project build path.
- If dependency not available in local repository then maven will connect to Central repository or remote repository based on our configuratiion.
- Note: By default maven will connect to central repository. If we want to use remote repository then we need to configure remote repository details.
- Every software company will maintain their own remote repository ( For example: JFrog )

![image](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/d6e9c26a-f429-4a26-be5f-39e68c2657e5)

## Maven Goals

- `Clean`: It is used to delete target folder in maven
- `Test`: It is used to execute unit test code of application.
- `Package`: It is used to generate jar or war file for our application based on packaging type available in pom.xml
- `Install`: It is used to install project as dependency in maven repository.
- `Compile`: It is used to compile project source code. Compiled source code will be stored in target folder.
- Note: Every maven goal is associated with `maven plugin`. when we execute maven goal then respective maven plugin will execute to perform the operation.
- Target folder is created when we compile the java application which is done using the compile goal.
- This target folder can be deleted using the `maven clean` command.
- We can execute multiple maven goals like `maven compile clean`.
- Syntax: `mvn goal-name`
