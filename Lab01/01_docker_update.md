


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