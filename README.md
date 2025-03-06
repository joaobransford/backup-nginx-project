📌 Objetivo do Projeto

Este projeto automatiza o backup de logs do servidor Nginx utilizando um script que:

  1. Faz o backup dos arquivos /var/log/nginx/access.log e /var/log/nginx/error.log.
  2.Envia os arquivos de backup para um bucket no S3.
  3.Dispara uma notificação via SNS por e-mail sempre que um novo backup for enviado.

🛠 Serviços AWS Utilizados

 1.Amazon EC2 → Servidor Linux rodando Nginx, responsável por gerar os logs.
 2.Amazon S3 → Armazena os arquivos de backup dos logs.
 3.Amazon SNS → Envia notificações por e-mail quando um novo backup é salvo no S3.
 
⚙️ Como Funciona?

 1. O servidor EC2 executa periodicamente um script de backup.
 2. O script copia os logs e os envia para um bucket S3.
 3. O S3 possui uma configuração para acionar o SNS ao receber novos arquivos.
 4. O SNS envia um e-mail informando a chegada de um novo backup.
