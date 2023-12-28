## Working with sonar token
- Go to sonar -> Login -> Click on profile -> my account -> Security -> Generate token
- Copy the token and configure that in pom.xml file like below:
- <sonar.host.url>sonar-server-url</sonar.host.url>
- <sonar.login>token-id</sonar.login>
- Then build the project using "mvn sonar:sonar" goal
