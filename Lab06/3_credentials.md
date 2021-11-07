## Credentials

1. Github
    1. Seleccionar Profile, seleccionar settings
    1. Seleccionar "Developer settings", clic en "Personal access tokens"
    1. En Note: "jenkins-token"
    1. En scope:
        * repo:status
        * repo_deployment
    1. Clic en "Generate token"
    
1. Crear credentiales para git
    1. Manage Jenkins
    1. Manage credentials
    1. Stores scope: "Jenkins"
    1. Clic "Global credentials"
    1. Clic en "Add credentials"
        * Kind: "Username with password"
        * User: Tu_user_github
        * Password : Github_token
        * Id: gituser-credentials
        * Description: Github user

1. Crear credentiales para docker hub
    1. Manage Jenkins
    1. Manage credentials
    1. Stores scope: "Jenkins"
    1. Clic "Global credentials"
    1. Clic en "Add credentials"
        * Kind: "Username with password"
        * User: Tu_user_dockerhub
        * Password : password_dockerhub
        * Id: docker-credentials
        * Description: Github user