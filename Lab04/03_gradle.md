# Gradle

## Settings
1. Instalar plugins maven
    1. Login
    1. Manage Jenkins
    1. Manage Plugins
    1. Clic Avialable
    1. Buscar Plugin: "Gradle Plugin"

1. Instalar gradle
    1. Manage Jenkins
    1. Global Tool Configuration
    1. Ir a la sección: "Gradle"
    1. Clic en "Add Gradle"
        * Name: gradle-default
        * Install automatically: Check



# JOBS
1. Crear job6-gradle
    * Crear proyecto del estilo libre.
        * Nombre: job6-gradle
        * Description: Gradle demo
        * Build --> Invoke Gradle script--> 
        ```bash         
        gradle --version
        ```

1. update job6-gradle
    * Crear proyecto del estilo libre.
        * Nombre: job6-gradle
        * Description: Gradle demo
        * Source Code Management: Git
            * Repository: https://github.com/mzegarras/labmaven.git
            * Branch: */master        
        * Build --> Invoke Gradle script--> 
        ```bash         
        gradle --version
        ```


1. Update job6-gradle
    * Crear proyecto del estilo libre.
        * Nombre: job6-maven
        * Description: Maven demo
        * Source Code Management: Git
            * Repository: https://github.com/mzegarras/labgradle.git
            * Branch: */master
        * Build --> Invoke gradle script --> 
        * Gradle version: gradle-default
        ```bash         
        build
        ```
        * Post-buil Actions
            * Add post build actions: Archive the artifacts
            * Files to archive: build/libs/labgradle-*-SNAPSHOT.jar
1. Update job6-gradle
    * Nombre: job6-gradle
    * Post-buil Actions
        * Add Publish JUnit test result report
        * Test report XMLs: **/build/test-results/test/TEST-*.xml

1. Instalar plugin: "Workspace Cleanup"
