1. Instalar docker-compose
    ```console
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    ```

1. Agregar permisos de ejecución
    ```console
    sudo chmod +x /usr/local/bin/docker-compose
    ```

1. Agregar acceso directo
    ```console
    sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
    ```
1. Verificar versión
    ```console
    docker-compose --version
    ```

1. Agregar acceso directo
    ```console
    sudo docker run -p 8080:80 nginx
    ```
    
1. Agregar acceso directo
    ```console
    sudo groupadd docker
    sudo usermod -a -G docker $USER
    sudo chmod 666 /var/run/docker.sock
    sudo service docker restart
    systemctl is-active docker
    docker run hello-world
    docker run -p 8080:80 nginx
    ```

