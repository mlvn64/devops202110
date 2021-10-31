# JOBS AS CODE

1. Crear job01-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job01-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        // comentario
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

1. Crear job02-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job02-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        // comentario
        pipeline {
            // Cualquier agente
            agent none

            stages {
                stage('Build') {
                    steps {
                        echo 'Building..'
                    }
                }

                stage('Testing') {
                    steps {
                        echo 'Testing..'
                    }
                }

                stage('Deploy') {
                    steps {
                        echo 'Testing..'
                    }
                }
            }
        }
        ```

1. Crear job03-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job03-as-code
        * Description: Pipeline as code
        * Pipeline: Pipeline script from SCM
        * SCM: Git
        * Repository Url: 
        * Script Paht: Lab05/jenkinsfiles/Jenkinsfile_01

1. RETO *Crear job04-as-code*
    * Usando el jenkinsfile jenkinsfiles/Jenkinsfile_02
