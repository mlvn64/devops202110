# Creando imagenes

* Publish Java 1 y 2
    ```bash
    docker tag java01 mzegarra/java01
    docker login
    docker push mzegarra/java01

    docker tag java02 mzegarra/java02
    docker login
    docker push mzegarra/java02
    ```