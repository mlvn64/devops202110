# Git

1. Crear job09-as-code docker
    * Crear proyecto del estilo Pipeline.
        * Nombre: job09-as-code
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

                        git branch: 'master',
                            url: 'https://github.com/mzegarras/labmaven.git'
                    }
                }
            }
        }
        ```

