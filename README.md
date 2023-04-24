# Jenkins-QuickStart-Docker
A quick start Jenkins deployment using Docker and Docker Compose

## Prepare persistant storage for Jenkins Home directory

### 1. Create Jenkins Home directory

```javascript
mkdir -p jenkins-data/jenkins-home
```
### 2. Create Docker-compose file using docker-compose-template.yml

```javascript
version: '3'
services:
  jenkins:
    container_name: jenkins
    image: jenkins/jenkins
    ports:
      - "8080:8080"
    volumes:
      - $PWD/jenkins_home:/var/jenkins_home
    networks:
      - net
networks:
  net:
```

```javascript
nano jenkins-data/docker-compose.yml
```

### 3. Deploy Jenkins

```javascript
cd jenkins-data
docker compose up -d
```

### 3. Access Jenkins Admin UI
```javascript
http://localhost:8080
```