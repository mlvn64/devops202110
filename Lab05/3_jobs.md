# JOBS AS CODE
1. Crear job01-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job6-maven
        * Description: Maven demo
        * Pipeline
        ```dsl class:"lineNo"     
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