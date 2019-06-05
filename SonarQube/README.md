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
### -D : 對 SonarQube 的 property 進行設定
* sonar.projectKey：SonarQube 對專案的 key，內部將以此 key 作為識別，必須唯一
* sonar.sources：SonarQube 要檢查的目錄，因為已經在專案目錄下，. 即為 目前目錄
* sonar.projectName：在 SonarQube 網頁上顯示的名稱
* sonar.projectVersion：在 SonarQube 網頁上顯示的版本編號
* sonar.exclusions：不受 SonarQube 檢查的目錄，如 PHP packgage 放在 vendor 目錄下，實務上我們不會讓 SonarQube 去檢查 package，會加以排除
