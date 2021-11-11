# Creando imagenes

1. Limpiar
    ```bash
    cd ~/devops202110/Lab06
    docker rm $(docker ps -aq) -f
    ```

* Java 1
    ```bash
    cd 03_java/1.1
    docker build -t java01 .
    docker images
    docker images|grep java01
    docker run -p 8080:8080 java01

    ```

    ```bash
    curl http://localhost:8080/customers
    ```

* Java 2
    ```bash
    cd 03_java/1.2
    docker build -t java02 .
    docker run -p 8080:8080 java02

    ```

    ```bash
    curl http://localhost:8080/customers
    ```

* Publish Java 1 y 2
    ```bash
    docker tag java02 mzegarra/java01
    docker login
    docker push mzegarra/java01

    docker tag java02 mzegarra/java02
    docker login
    docker push mzegarra/java02
    ```