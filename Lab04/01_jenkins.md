1. Generar imagen
    ```bash
    cd ~/devops202110/Lab04
    docker-compose build
    ```

1. Iniciar docker-compose con remote machine
    ```bash
    mkdir jenkins_home
    docker-compose up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```