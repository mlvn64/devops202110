# JOBS AS CODE
1. Crear job01-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job6-maven
        * Description: Maven demo
        * Pipeline script
        ```dsl
        # script 
        pipeline {
            agent any 
            stages {
                stage('Stage 1') {
                    steps {
                        echo 'Hello world!' 
                    }
                }
            }
        }
        ```
1. Snippet Generator
http://localhost:8080/pipeline-syntax/