1. Crear Job08-as-code
    * Crear proyecto del Pipeline
        * Nombre: Job08-as-code
        * Description: Pipeline as code
        * Pipeline --> Pipeline script --> 
        ```bash         
        pipeline {
             agent {
                docker { image 'alpine:latest' }
            }

            stages {
                stage('Build') {
                    steps {
                        echo 'Building..'
                        sh 'echo "Fecha $(date)"'
                        sh 'echo "Sever $(hostname)"'
                    }
                }
            }
        }
        ```