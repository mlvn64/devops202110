1. Limpiar
    ```bash
    cd ~/devops202110/Lab07
    docker rm $(docker ps -aq) -f
    ```
    
1. Generar imagen jenkins soporte con docker (opcional)
    ```bash
    cd ~/devops202110/Lab07
    docker-compose build jenkins
    ```

1. Inicia jenkins
    ```bash
    cd ~/devops202110/Lab07
    mkdir jenkins_home
    docker-compose up -d
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```

1. Instalar plugins docker pipeline
    1. Login
    1. Manage Jenkins
    1. Manage Plugins
    1. Clic Avialable
    1. Buscar Plugins: 
        * "Pipeline"
        * "Git"
        * "Docker Pipeline"

1. Crear secret
   * Manage Jenkins
    * Manage credentials
    * Stores scope: "Jenkins"
    * Clic "Global credentials"
    * Clic en "Add credentials"
        * "Kind": "Secret File"
        * Secret: Seleccionar Archivo
        * "Id": gke-sa
        * Description: gke-sa

1. Crear job ms01-genesis
    ```grovy    
    pipeline {
                
        agent any

        environment {
            PROJECT_ID = 'galaxy-devops-331819'
            CLUSTER_NAME = 'cluster-1'
            LOCATION = 'us-central1-c'
            CREDENTIALS_ID = 'gke-sa'
        }

        stages {
            
            stage('Deploy to GKE') {
                agent {
                    docker { 
                        image 'google/cloud-sdk:latest' 
                    }
                    
                }
                environment {
                    CLOUDSDK_CONFIG="/tmp"
                    KUBECONFIG="~/.kube"
                }

                steps {
                    withCredentials([[$class: 'FileBinding', credentialsId: env.CREDENTIALS_ID, variable: 'GOOGLE_APPLICATION_CREDENTIALS']]) {
                        sh 'echo "${GOOGLE_APPLICATION_CREDENTIALS}"' // returns ****
                        sh 'gcloud auth activate-service-account --key-file $GOOGLE_APPLICATION_CREDENTIALS'
                        sh 'gcloud container clusters get-credentials $CLUSTER_NAME --zone $LOCATION --project $PROJECT_ID'
                        sh 'kubectl apply -f ./Lab07/k8s/clientes.yaml'
                    }
                }

            }
        }
    }
    ```

1. Crear job ms01-apocalipsis
    ```grovy    
    pipeline {
                
        agent any

        environment {
            PROJECT_ID = 'galaxy-devops-331819'
            CLUSTER_NAME = 'cluster-1'
            LOCATION = 'us-central1-c'
            CREDENTIALS_ID = 'gke-sa'
        }

        stages {
            
            stage('Deploy to GKE') {
                agent {
                    docker { 
                        image 'google/cloud-sdk:latest' 
                    }
                    
                }
                environment {
                    CLOUDSDK_CONFIG="/tmp"
                    KUBECONFIG="~/.kube"
                }

                steps {
                    withCredentials([[$class: 'FileBinding', credentialsId: env.CREDENTIALS_ID, variable: 'GOOGLE_APPLICATION_CREDENTIALS']]) {
                        sh 'echo "${GOOGLE_APPLICATION_CREDENTIALS}"' // returns ****
                        sh 'gcloud auth activate-service-account --key-file $GOOGLE_APPLICATION_CREDENTIALS'
                        sh 'gcloud container clusters get-credentials $CLUSTER_NAME --zone $LOCATION --project $PROJECT_ID'
                        sh 'kubectl apply -f ./Lab07/k8s/clientes.yaml'
                    }
                }

            }
        }
    }
    ```
