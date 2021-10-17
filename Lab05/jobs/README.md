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

1. Crear job8-as-code-fromgit
     * Crear proyecto del Pipeline
        * Nombre: job8-as-code-fromgit
        * Description: Pipeline as code from git
        * Pipeline script from SCM
        * Branch: Main
        * Script Path: ./lab05-docker/job8-as-code-fromgit.jenkinsfile        