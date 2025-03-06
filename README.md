📌 Backup Automático de Logs do Nginx com Notificação via AWS SNS 

📖 Introdução: 

Este projeto automatiza o backup dos arquivos de log do Nginx (access.log e error.log) utilizando serviços da AWS. Um script shell é responsável por enviar os logs periodicamente para um bucket no Amazon S3. Assim que os arquivos chegam ao S3, um evento aciona uma notificação via Amazon SNS, enviando um alerta por e-mail sobre a conclusão do backup. 

Essa solução garante a integridade e a segurança dos logs, facilitando a auditoria e o monitoramento do ambiente. 

🛠️ Serviços AWS Utilizados 

1️⃣ Amazon EC2 (Elastic Compute Cloud) 

Servidor virtual onde o Nginx está instalado e configurado para gerar os logs. 

Responsável por executar o script de backup. 

2️⃣ Amazon S3 (Simple Storage Service) 

Armazena os arquivos de log enviados pelo script. 

Possui um evento configurado para detectar novos arquivos e acionar o SNS. 

3️⃣ Amazon SNS (Simple Notification Service) 

Serviço responsável por enviar notificações por e-mail assim que os logs chegam no S3. 

⚙️ Como Funciona? 

O servidor EC2 gera os arquivos de log do Nginx (access.log e error.log). 

Um script de backup copia esses arquivos e os envia para um bucket no S3. 

O S3 detecta a chegada dos novos arquivos e dispara um evento. 

Esse evento aciona um tópico do SNS, que envia um e-mail notificando o backup. 
