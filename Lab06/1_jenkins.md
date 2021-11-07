1. Limpiar
    ```bash
    cd ~/devops202110/Lab06
    docker rm $(docker ps -aq) -f
    ```

1. Inicia jenkins
    ```bash
    cd ~/devops202110/Lab06
    mkdir jenkins_home
    docker-compose up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```