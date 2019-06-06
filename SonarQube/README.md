### Quick sonar scanner docker image
https://github.com/newtmitch/docker-sonar-scanner

### 如何使用 SonarQube 檢查 PHP 專案？
https://oomusou.io/sonarqube/php/
* SonarQube
* SonarQube Scanner
* Jenkins

### Run Sonar Qube Server
```
docker run -d --name sonarqube -p 9000:9000 -p 9092:9092 sonarqube
```

### Run Sonar Scanner
```
docker run -ti -v $(pwd):/usr/src --link sonarqube newtmitch/sonar-scanner
docker run -ti -v $(pwd):/usr/src --link sonarqube newtmitch/sonar-scanner:alpine
```

### Fully-loaded command line
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
* sonar.exclusions：不受 SonarQube 檢查的目錄
```
// PHP CodeIgniter exclusion Path
-Dsonar.exclusions=system/**,application/config/**,application/third_party/**,application/logs/**
```

### Scanner SUCCESS CASE
```
docker run -ti -v $(pwd):/root/src --link sonarqube newtmitch/sonar-scanner:alpine sonar-scanner \
  -Dsonar.projectKey=MyProjectKey \
  -Dsonar.projectName="My Project Name" \
  -Dsonar.projectVersion=1
 ```
 
