## Maven Terminology

- archetype
- groupId
- artifactId
- packaging

- Archtype represents what type of project we want to create
  1. Maven-archetype-quickstart : It represents java standalone projects
  2. Maven-archetype-webapp : It rrepresents java web applications
- Note : Maven providing `1500+` archetypes

- groupId represents compnay name or project name.
- ArtifactId represents project name or project module name.
- packaging represents how we want to package our java applications (jar/war).

### Creating standalone applications using maven

- mvn archetype:generate -DgroupId=com.yourapp.app -DartifactId=swingapp `-DarchetypeArtifactId=maven-archetype-quickstart` -Dversion=1.0-SNAPSHOT

### Creating web applications using maven

- mvn archetype:generate -DgroupId=com.yourapp.app -DartifactId=swingapp `-DarchetypeArtifactId=maven-archetype-webapp` -Dversion=1.0-SNAPSHOT

![Flowchart](https://github.com/Abhinavcode13/DevOpsDrift-Daily/assets/126642111/a427081c-206a-45dc-8730-292a86d88aef)

- We can add dependencies in the `pom.xml` file

### How maven will download dependencies using repository

- Maven will download dependencies using repository
- There are three types of repository
  1. Central Repository
  2. Remote Repository
  3. Local Repository
- Central repository is maintained by apache organization.
- Every company will maintain their own remote repository.
- Local repository will be created in our system.
