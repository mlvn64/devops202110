1. Seleccionar job
    1. Remove Post Step: SonarQube Analysis with Maven
    1. En la sección Build Environment.
    1. Seleccionar: Execute SonarQubeScanner
    1. En la sección de "Analysis properties"
    ```bash
    sonar.projectKey=labmaven01
    sonar.projectName=labmaven01
    sonar.sources=src/main/java
    sonar.java.binaries=target/classes/
    sonar.tests=src/test/java
    ```    