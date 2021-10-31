# Credentials

1. Crear credentiales git-credentials

    * Manage Jenkins
    * Manage credentials
    * Stores scope: "Jenkins"
    * Clic "Global credentials"
    * Clic en "Add credentials"
        * "Kind": "Secret Text"
        * Secret: secret-key-123@
        * "Id": jenkins-aws-secret-key-id
        * Description: aws secret id
    * Clic en "Add credentials"
        * "Kind": "Secret Text"
        * Secret: secret-access-123@
        * "Id": jenkins-aws-secret-access-key
    * Clic en "Add credentials"
        * "Kind": "User name with password"
        * Username: Us3r
        * Password: P@ssw0rd
        * Id: git-user

1. Crear job07-as-code credentials
    * Crear proyecto del estilo Pipeline.
        * Nombre: job07-as-code
        * Description: Pipeline as code
        * Pipeline script
        ```dsl
        // comentario
        pipeline {
            agent any 
             environment {
                AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
                AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
            }
            stages {
                stage('AWS') {
                    steps {
                        
                        /* WRONG! */
                        //'hello; ls /'
                        //echo "AWS_ACCESS_KEY_ID: $AWS_ACCESS_KEY_ID"
                        

                        /* CORRECT! */
                        
                        echo 'AWS_SECRET_ACCESS_KEY: $AWS_SECRET_ACCESS_KEY ls /'
                        sh('echo AWS_ACCESS_KEY_ID: ${AWS_ACCESS_KEY_ID} ls /')
                        sh('echo AWS_SECRET_ACCESS_KEY: ${AWS_SECRET_ACCESS_KEY}')

                    }
                }

                stage('GIT') {
                     environment {
                        GIT_CREDS = credentials('git-user')
                        
                    }

                    steps {
                        sh('echo CRED: ${GIT_CREDS}')  
                        sh('echo USER: ${GIT_CREDS_USR}')  
                        sh('echo PWD: ${GIT_CREDS_PSW}')  
                    }
                }
            }
        }
        ```
1. [Documentación](https://www.jenkins.io/doc/book/pipeline/jenkinsfile/   ) - Documentación oficial
     