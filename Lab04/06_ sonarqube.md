
1. Limpiar
    ```bash
    cd ~/devops202110/Lab04
    docker-compose -f docker-compose-runtimes.yaml rm -f
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
    ```
1. Parámetros:
    * Conector url : http://localhost:9000
    * user: admin
    * password: admin

1. Crear token de sesión:
    * Conector url : http://localhost:9000
    * Clic Profile, "My Account"
    * Seleccionar "Security"
    * Generar token

1. Crear secret text en jenkins
    1. Login
    1. Manage Jenkins
    1. Manage Credentials
    1. Seleccionar Vault
    1. Selecconar "Secret Text"
    1. Id: SonarQubeToken

1. Instalar plugins
    1. Login
    1. Manage Jenkins
    1. Manage Plugins
    1. Clic Avialable
    1. Buscar Plugins: "SonarQube Scanner for Jenkins"
    1. URL https://www.jenkins.io/doc/pipeline/steps/sonar/

1. Configurar
    1. Ingresar a Configure System
    1. En la sección: SonarQube servers
    1. Parémtros:
        * Name: sonar-server
        * Url : http://localhost:9000/
        * Token: SonarQubeToken

1. Configurar
    1. Ingresar a Global Tool Configuration
    1. SonarQube Scanner
    1. Name: scanner-default

1. Seleccionar job
    1. En la sección Build Environment.
    1. Seleccionar: Prepare SonarQube Scanner environment
    1. Add Post Step: SonarQube Analysis with Maven
