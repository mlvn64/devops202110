## Jobs

1. Crear job: Multibranch Pipeline
    * Nombre: msclientes
    * Description: Microservice clientes

1. En la sección, Source Code Management
    * Url: https://github.com/mzegarras/labmaven.git
    * Credentials: githubuser

1. En la sección, Behaviours:
    * Eliminar todo
    * Seleccionar "Filter by name (with wildcards)"
    * En la sección "Include", 
    * main|master|develop|release.*|features.*|bugfix.*

1. En la sección, Build Configuration:
    * Mode: "by Jenkinsfiles"
    * Script Paht: devops/Jenkinsfile