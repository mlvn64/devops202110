1. Limpiar
    ```bash
    cd ~/devops202110/Lab05
    docker rm $(docker ps -aq) -f
    ```
1. Generar imagen jenkins soporte con docker (opcional)
    ```bash
    cd ~/devops202110/Lab05
    docker-compose build jenkins
    ```

1. Inicia jenkins
    ```bash
    cd ~/devops202110/Lab05
    mkdir jenkins_home
    docker-compose up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```