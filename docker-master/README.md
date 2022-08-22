# JavaTechnoLessons Docker tutorial

## Part 1 - myapp on NGINX

### Build image

```sh
docker build -f DockerfileMyappOnNginx -t myapp:1.0 .
```

### Run container
```sh
docker run --name myapp -d -p 80:80 myapp:1.0
```

## Part 2 - alpine:jre15 and alpine:jre17

### Download JRE's binaries:
* JRE15: https://cdn.azul.com/zulu/bin/zulu15.38.17-ca-jre15.0.6-linux_musl_x64.tar.gz

* JRE17: https://cdn.azul.com/zulu/bin/zulu17.32.13-ca-jre17.0.2-linux_musl_x64.tar.gz

### Build alpine:jre15 image

```sh
docker build -f DockerfileAlpineJRE --build-arg JAVA_VERSION=zulu15.38.17-ca-jre15.0.6-linux_musl_x64 -t alpine:jre15 .
```

### Run container of type alpine:jre15
```sh
docker run --name jre15 -it --rm alpine:jre15 sh
```
### Build alpine:jre17 image

```sh
docker build -f DockerfileAlpineJRE --build-arg JAVA_VERSION=zulu17.32.13-ca-jre17.0.2-linux_musl_x64 -t alpine:jre15 .
```

### Run container of type alpine:jre17
```sh
docker run --name jre15 -it --rm alpine:jre17 sh
```

## Part 3 - tomcat:10-jre17

### Download Tomcat binary
* Tomcat 10 : https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.16/bin/apache-tomcat-10.0.16.tar.gz

### Build tomcat:10-jre17 image

```sh
docker build -f DockerfileTomcatJRE --build-arg TOMCAT_VERSION=apache-tomcat-10.0.16 -t tomcat:10-jre17 .
```
### Run container of type tomcat:10-jre17
```sh
docker run -d --name tomcat -p 8080:8080 tomcat:10-jre17 
```