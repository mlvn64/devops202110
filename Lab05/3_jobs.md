# JOBS AS CODE

1. Crear job01-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job01-as-code
        * Description: Pipeline as code
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

1. Crear job02-as-code
    * Crear proyecto del estilo Pipeline.
        * Nombre: job02-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        # script 
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

