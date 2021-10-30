
1. Limpiar
    ```bash
    cd ~/devops202110/Lab04
    docker-compose -f docker-compose-runtimes.yaml rm -f
    ```
    
1. Inicia jenkins
    ```bash
    cd ~/devops202110/Lab04
    docker rm $(docker ps -aq) -f
    mkdir jenkins_home
    docker-compose up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```