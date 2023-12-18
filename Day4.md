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
