
1. Actualizar centos (opcional)
    ```bash
    sudo dnf update -y
    ```

1. Agregar git
```console
     sudo dnf install -y git
    git clone https://github.com/mzegarras/devops202110.git
```
1. Agregar Docker-CE repositorio
    ```console
    sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
    ```

1. Instalar última versión docker
    ```console
    sudo dnf install -y docker-ce --nobest
    ```
1. Iniciar docker cuando iniciar el SO
    ```console
    sudo systemctl start docker
    sudo systemctl enable docker
    ```
1. Verificar versión
    ```console
    docker --version
    ```