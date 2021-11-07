
1. Limpiar
    ```bash
    cd ~/devops202110/Lab04
    docker-compose rm -f
    ```
        
1. Iniciar jenkins con sonarque
    ```bash
    cd ~/devops202110/Lab04
    docker rm $(docker ps -aq) -f

    mkdir -p sonarqube_home/data
    mkdir -p sonarqube_home/extensions
    mkdir -p sonarqube_home/logs
    mkdir -p sonarqube_home/temp

    docker-compose -f docker-compose-sonarqube.yaml up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```