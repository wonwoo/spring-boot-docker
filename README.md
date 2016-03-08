# spring-boot-docker

Spring boot docker Sample

```
$ git clone https://github.com/wonwoo/spring-boot-docker.git
$ cd spring-boot-docker
$ mvn clean package docker:build
```

mysql pull 
```
$ docker run -d --name spring-boot-mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=docker -e MYSQL_USER=dbuser -e MYSQL_PASSWORD=dbpassword -d mysql:latest
```

spring boot link mysql run
```
$ docker run --name spring-boot-docker --link spring-boot-mysql:mysql -p 8080:8080 -d wonwoo/spring-boot-docker
```

if **No route to host** exception?
```
$ iptables -t filter -A DOCKER -d 172.17.0.0/16 -i docker0 -j ACCEPT
```
