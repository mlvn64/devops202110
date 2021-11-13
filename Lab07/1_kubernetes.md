1. GKE - Service account
    1. Seleccionar el proyecto "galaxy-devops"
    1. Selecionar IAM, seleccionar "Service Account"
    1. Clic en "+ Create service account"
    1. En la seccion service account, ingresar el valor: jenkins-devops
    1. Clic en "Create and continue"
    1. En la sección de Role, seleccionar "Kubernetes Engine" y "Kubernetes Engine Admin" y clic en "Done"

1. GKE - Generar Keys
    1. Seleccionar el usuario: jenkins-devops
    1. Clic en "Add Key", en formato "json".
    