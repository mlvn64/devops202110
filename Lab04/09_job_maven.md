1. Seleccionar job
    1. Remove Post Step: SonarQube Analysis with Maven
    1. En la sección Build Environment.
    1. Seleccionar: Execute SonarQubeScanner
    1. En la sección de "Analysis properties"
    ```bash

    # Project
    sonar.projectKey=labmaven01
    sonar.projectName=labmaven01

    # Source information
    sonar.sources=src/main
    sonar.sourceEncoding=UTF-8
    sonar.language=java

    # Tests
    sonar.tests=src/test
    sonar.junit.reportsPath=target/surefire-reports
    sonar.surefire.reportsPath=target/surefire-reports
    sonar.jacoco.reportPath=target/jacoco.exec
    sonar.java.binaries=target/classes
    sonar.java.coveragePlugin=jacoco
    sonar.coverage.jacoco.xmlReportPaths=target/jacoco.xml

    sonar.exclusions=**/*IT.java,**/*TEST.java,**/*Test.java,**/src/it**,**/src/test**,**/gradle/wrapper**
    sonar.java.libraries=target/*.jar
    ```    

