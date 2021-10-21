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

