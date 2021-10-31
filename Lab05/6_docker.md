# Docker como agente

1. Verificar plugins:
    "pipeline"
    "Docker Pipeline"
    
1. Crear job07-as-code docker
    * Crear proyecto del estilo Pipeline.
        * Nombre: job07-as-code
        * Description: Pipeline as code
        * Pipeline script

        ```Groovy         
        pipeline {
            // imagen node
            agent {
                docker { image 'node:latest' }
            }

            stages {
                stage('Build') {
                    steps {
                        echo 'Building..'
                        sh 'npm version'
                    }
                }
            }
        }
        ```