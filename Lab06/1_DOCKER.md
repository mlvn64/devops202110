# Docker

* Limpiar (opcional)
    ```bash
    docker system prune
    ```

1. Limpiar
    ```bash
    cd ~/devops202110/Lab06
    docker rm $(docker ps -aq) -f
    ```
1. Crear containers [nginx](https://hub.docker.com/_/nginx) 
    ```bash
    docker run -p 8008:80 nginx
    docker run -p 8080:80 nginx:latest
    docker run -p 8080:80 nginx:alpine
    ```

1. Crear containers [tomcat](https://hub.docker.com/_/tomcat) 
    ```bash
    docker run -p 8888:8080 tomcat:9-slim
    docker run -p 8888:8080 -d tomcat:9-slim
    ```

1. Web LPSA
    ```bash
    docker run -p 8080:80 mzegarra/lpsa:1.0
    docker run -p 8081:80 mzegarra/lpsa:2.0
    ```

1. Listar containers
    ```bash
    docker ps
    docker ps -a
    docker ps -aq
    docke