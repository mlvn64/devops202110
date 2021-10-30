
1. Generar java maven jar
    ```bash
    cd ~/devops202110/Lab04
    docker-compose -f docker-compose-runtimes.yaml up -d
    docker exec -it maven /bin/bash

    mvn --version
    git --version

    git clone https://github.com/mzegarras/labmaven.git
    cd labmaven/
    mvn package
    ls -lta target/
    java -jar ./target/labmaven-0.0.1-SNAPSHOT.jar
    ```


1. Generar koltin gradle jar
    ```bash
    cd ~/devops202110/Lab04
    docker-compose -f docker-compose-runtimes.yaml up -d
    docker exec -it gradle /bin/bash

    gradle --version
    git --version

    git clone https://github.com/mzegarras/labgradle.git
    cd labgradle/
    gradle build
    ls -lta ./build/libs/
    java -jar ./build/libs/labgradle-0.0.1-SNAPSHOT.jar
    ```
