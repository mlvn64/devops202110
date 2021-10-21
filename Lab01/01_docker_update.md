


1. Actualizar centos (opcional)
    ```bash
    sudo dnf update -y
    ```

1. Agregar Docker-CE repositorio
    ```console
    sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
    ```


1. Agregar Docker-CE repositorio
    ```console
    docker --version
    sudo dnf install  -y docker-ce docker-ce-cli containerd.io
    docker --version
    ```

1. Verificar permisos
    ```console
    sudo docker run -p 8080:80 nginx
    CTRL + C
    ```
    
1. Fix permisos
    ```console
    sudo groupadd docker
    sudo usermod -a -G docker $USER
    sudo chmod 666 /var/run/docker.sock
    sudo service docker restart
    systemctl is-active docker
    docker run hello-world
    ```