1. Agregar git
    ```console
    sudo dnf install -y git
    git clone https://github.com/mzegarras/devops202110.git
    ```

1. Preparación:
    ```bash
    cd ~/devops202110/Lab01
    mkdir jenkins_home
    ```

1. Iniciar docker-compose
    ```bash
    docker-compose  -f docker-compose-v1.yaml up -d
    docker ps
    docker logs jenkins
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    docker exec -it jenkins bash
    ```

1. Detener jenkins
    ```bash
    docker-compose -f docker-compose-v1.yaml ps
    docker-compose  -f docker-compose-v1.yaml down
    docker-compose  -f docker-compose-v1.yaml rm
    rm -fr jenkins_home
    ```    