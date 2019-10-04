# Docker

## Incluindo uma imagem própria no Docker Hub

Após criar sua imagem e ela estar *buindin* no seu ambiente local é possível incluir essa imagem no docker hub para futuras utilizações, reaproveitamento e compartilhamento. 

1. Realizando login no Docker Hub

```bash
docker login
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: leonardoscorrea
Password:
Login Succeeded
```

2.  Incluindo uma **Tag** na imagem docker

Para incluir uma imagem local ao *Docker Registry* é necessário associar a imagem ao repositório. A notação que realiza essa associação é *username/repository:tag*

```bash
docker tag image username/repository:tag
```

Como exemplo usaremos o *spring-boot-websocket-chat*

```bash
docker tag spring-boot-websocket-chat leonardoscorrea/spring-boot-websocket-chat:0.0.1-SNAPSHOT
docker image ls
```

3. Realizar o **PUSH** da imagem no Docker Hub

Para realizar o push da imagem local ao Docker Hub basta executar o comando que segue.

```bash
docker push leonardoscorrea/spring-boot-websocket-chat:0.0.1-SNAPSHOT
```

4. Utilizando a imagem que está no Docker Hub

Após realizar o push da imagem é possível utilizá-la sempre que necessário.

```bash
docker run -p 5000:8080 callicoder/spring-boot-websocket-chat:0.0.1-SNAPSHOT
```
