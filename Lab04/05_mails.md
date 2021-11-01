1. Configurar cuenta en:
    https://mailtrap.io/inboxes/1514511/messages#
    
1. Instalar plugins docker pipeline
    1. Login
    1. Manage Jenkins
    1. Manage Plugins
    1. Clic Avialable
    1. Buscar Plugins: "Mailer"

1. Configurar mail
    1. Login
    1. Manage Jenkins
    1. Configure System
    1. E-mail Notification, clic en "Advance"
    1. Settings:
        1. "SMTP Server": smtp.mailtrap.io
        1. "Use SMTP Authentication"
        1. "User": "xxx@gmail.com"
        1. "Password": "tupassword"
        1. Use TLS: true
        1. SMTP Port: 465
        1. Reply address: noreply@gmail.com
        1. Charset: UTF-8