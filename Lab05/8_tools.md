# Tools
## Settings
1. Instalar maven
    1. Manage Jenkins
    1. Global Tool Configuration
    1. Ir a la sección: "Maven"
    1. Clic en "Add Maven"
        * Name: maven-default
        * Install automatically: Check

## Coverage
1. JaCoCo
    1. Manage Jenkins
    1. Manage Plugins
    1. Clic Avialable
    1. Buscar Plugin: "JaCoCo"

1. Crear job10-as-code docker
    * Crear proyecto del estilo Pipeline.
        * Nombre: job10-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```Groovy         
        pipeline {
            agent any

             tools {
                maven 'maven-default'
            }


            stages {
                stage('Checkout code') {
                    steps {

                        git branch: 'master',
                            url: 'https://github.com/mzegarras/labmaven.git'


                    }
                }

                stage('Build') {
                    steps {
                        echo 'Building..'
                        sh 'mvn verify'
                    }
                    post {
                        always {
                            junit(testResults: '**/surefire-reports/*.xml', allowEmptyResults: true)
                            junit(testResults: '**/failsafe-reports/*.xml', allowEmptyResults: true)
                            archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
                            jacoco runAlways: true
                        }
                    }
                }
            }
        }
        ```

