# Build Project Using Maven

Maven is java based build tool to generate executable 

packages(jar, ear,war) for java based projects.

```bash
mvn clean package
```

## Create Docker Image
Docker is a continerization tool.Using docker we can deploy our applications as 

containers using docker images. Containers contains application code and also the softwares,

config files whatever is required for our application to run.

Create docker image using Dockerfile


```docker
docker build -t your-repo-name/springboot-app .
```

## Create Docker Network
```docker
docker network create spring-network
```

## Pull Mongo image
```docker
docker pull mongo
```

## Deploy Application Using Docker

#### Springboot App

```Docker
docker run --name springboot-app -d -p 3000:8080 --network spring-network -d \
    -e MONGO_DB_USERNAME=root \
    -e MONGO_DB_PASSWORD=admin123 \
    -e MONGO_DB_HOSTNAME=mongodb springboot-app 
``` 

#### Mongo DB

```Docker
docker run --name mongodb -d --network spring-network -e MONGO_INITDB_ROOT_USERNAME=root -e MONGO_INITDB_ROOT_PASSWORD=admin123 mongo
```

<!-- ## Deploy Application Using Docker Compose 

```docker-compose 
docker-compose up -d 
``` -->

## List Docker Containers
```docker
docker ps -a
```

## License
[United Core Systems](http://unitedcoresystems.com)