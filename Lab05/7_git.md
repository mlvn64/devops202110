# Git

1. Crear job09-as-code docker
    * Crear proyecto del estilo Pipeline.
        * Nombre: job09-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```Groovy         
        pipeline {
             agent {
                docker {
                    image 'maven:3.8.1-adoptopenjdk-11'
                    args '-v /tmp/.m2:/root/.m2'
                }
            }

            stages {
                stage('Build') {
                    steps {
                        echo 'Building..'
                        sh 'mvn --version'

                        git branch: 'master',
                            url: 'https://github.com/mzegarras/labmaven.git'
                    }
                }
            }
        }
        ```

