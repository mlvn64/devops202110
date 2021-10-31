# Docker como agente

1. Verificar plugins:
    * "pipeline"
    * "Docker Pipeline"
    
1. Crear job08-as-code docker
    * Crear proyecto del estilo Pipeline.
        * Nombre: job08-as-code
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
1. Update job08-as-code docker
    * Pipeline script
        ```Groovy 
        pipeline {
            agent any

            stages {
                stage('Build') {
                    agent {
                        docker {
                            image 'gradle:6.7-jdk11'
                            // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
                            reuseNode true
                        }
                    }
                    steps {
                        sh 'gradle --version'
                    }
                }
            }
        }
        ```          
1. Update job08-as-code docker
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
                        sh 'mvn --version'
                    }
                }
            }
        }
        ```
1. Update job08-as-code docker
    * Pipeline script
        ```Groovy
        pipeline {
            agent none
            stages {
                stage('Back-end') {
                    agent {
                        docker { image 'maven:3.8.1-adoptopenjdk-11' }
                    }
                    steps {
                        sh 'mvn --version'
                    }
                }
                stage('Front-end') {
                    agent {
                        docker { image 'node:14-alpine' }
                    }
                    steps {
                        sh 'node --version'
                    }
                }
            }
        }
        ```