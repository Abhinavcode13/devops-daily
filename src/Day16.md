## Working with sonar token
- Go to sonar -> Login -> Click on profile -> my account -> Security -> Generate token
- Copy the token and configure that in pom.xml file like below:
- <sonar.host.url>sonar-server-url</sonar.host.url>
- <sonar.login>token-id</sonar.login>
- Then build the project using "mvn sonar:sonar" goal
- For each language sonar qube provided one quality profile
- Quality profile means set of rules to perform code review
- We can create our own quality profile based on requirement
- Create one quality profile
  1. Name : Chef_project
  2. Language : Java
  3. Parent : None 
