# Environment variables

1. Crear job05-as-code usando variables
    * Crear proyecto del estilo Pipeline.
        * Nombre: job05-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        // comentario
        pipeline {
            agent any 
            stages {
                stage('Stage 1') {
                    steps {
                        echo "BUILD_ID: ${env.BUILD_ID} - BUILD_NUMBER:${env.BUILD_NUMBER}"
                        echo "BUILD_TAG: ${env.BUILD_TAG} - BUILD_URL:${env.BUILD_URL}"
                        echo "JOB_NAME: ${env.JOB_NAME}"
                        echo "NODE_NAME: ${env.NODE_NAME} - WORKSPACE:${env.WORKSPACE}"
                    }
                }
            }
        }
        ```
1. Crear job06-as-code usando variables
    * Crear proyecto del estilo Pipeline.
        * Nombre: job06-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        // comentario
        pipeline {
            agent any 
            environment { 
                CC = 'clang'
                VERSION = '1.0.1'
                NAME_ARTIFACT='MSCUSTOMERS'
            }
            stages {
                stage('Stage 1') {
                    steps {
                        sh 'printenv'
                    }
                }

                stage('Stage 2') {
                    steps {
                        echo "CC: ${CC} - VERSION:${VERSION} - NAME_ARTIFACT:${NAME_ARTIFACT}"
                    }
                }
                stage('Stage 3') {
                    environment { 
                        DEBUG_FLAGS = '-g'
                    }
                    steps {
                        echo "DEBUG_FLAGS: ${DEBUG_FLAGS}"
                    }
                }
            }
        }
        ```