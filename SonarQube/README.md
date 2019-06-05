### Quick sonar scanner docker image
https://github.com/newtmitch/docker-sonar-scanner

### 如何使用 SonarQube 檢查 PHP 專案？
https://oomusou.io/sonarqube/php/

SonarQube
SonarQube Scanner
Jenkins



Using the official Sonar Qube Docker image:

```
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

```
docker run -ti -v $(pwd):/usr/src --link sonarqube newtmitch/sonar-scanner
docker run -ti -v $(pwd):/usr/src --link sonarqube newtmitch/sonar-scanner:alpine
```

Here's a fully-loaded command line (based on latest/3.0.3 version) that basically overrides everything from the sonar-runner.properties file on the command-line itself. The settings shown here match those in the sonar-runner.properties file.

```
docker run -ti -v $(pwd):/usr/src --link sonarqube newtmitch/sonar-scanner sonar-scanner \
  -Dsonar.host.url=http://sonarqube:9000 \
  -Dsonar.jdbc.url=jdbc:h2:tcp://sonarqube/sonar \
  -Dsonar.projectKey=MyProjectKey \
  -Dsonar.projectName="My Project Name" \
  -Dsonar.projectVersion=1 \
  -Dsonar.projectBaseDir=/usr/src \
  -Dsonar.sources=.
```
