# Jenkins AWS

1. El docente facilitará el pem y la máquina ec2
    ```
    ssh -i "galaxy-training-devops-alumnos.pem" ec2-user@ec2-34-220-210-182.us-west-2.compute.amazonaws.com
    ```

1. Crear credentiales aws

    * Manage Jenkins
    * Manage credentials
    * Stores scope: "Jenkins"
    * Clic "Global credentials"
    * Clic en "Add credentials"
    * "Kind": "SSH UserName with PrivateKey"
    * "Id": aws-dev
    * Username: ec2-user
    * Private Key: copiar contenido de PEM

1. Configurar remote host en aws

    * Manage Jenkins
    * Configure System
    * Ir a la sección "SSH remote hosts"
    * Clic en add
    * Hostname: "ec2-34-220-210-182.us-west-2.compute.amazonaws.com"
    * Port: 22
    * Credentials: ec2-user

1. Configurar job

    * Nombre: job5-aws
    * Description: job en aws
        * Build --> Execute shell script on remote host using shh -->
        ```bash
        NOMBRE_APELLIDO="manuel_zegarra"
        mkdir -p /tmp/data/${NOMBRE_APELLIDO}
        curl https://www.python.org/static/apple-touch-icon-144x144-precomposed.png -o precomposed.png
        mv precomposed.png /tmp/data/${NOMBRE_APELLIDO}/precomposed.png

        curl https://assets.datacamp.com/production/repositories/4180/datasets/eb1d6a36fa3039e4e00064797e1a1600d267b135/201812SpotifyData.zip -o data.zip

        mv precomposed.png /tmp/data/${NOMBRE_APELLIDO}/data.zip
        ```

1. Limpieza
 ```bash
 docker-compose down
 ```
