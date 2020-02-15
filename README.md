# Infraestutura para Sistemas Web
#Instação do Apache e hospedagem de Site

- 1 Passo - Instalação do Apache na maquina
insira o comando 

sudo apt istall apache2

Verifique o funcionamento
service apache status
# OK, Se aparecer uma mensagem verde escrita active (runnig), está funcionado
- Você também pode testar o apache no seu navegador - Digitando : localhost
- Se aparecer uma mensagem e imagem do apache está tudo ok

![imagem](foto.jpg)
- Lista
- lista


# Para hospedar um arquivo salve seu arquivo HTML em /var/www/html
![imagem](cp.png)

# HOSTS VIRTUAIS - AULA 2

- Iremos aprender a configurar o Apache2, um servidor WEB capaz de entregar conteúdo WEB para quem requisita

1 - Passo

Crie uma pasta para despositar seu host virtual 
Digite o comando a seguir dando nome para pasta
Nesse caso a pasta se chama "thiagoalves"

• $ sudo mkdir /var/www/thiagoalves

2 - Passo - Concendendo permissões
execute os comandos a seguir para dar permissão a este diretório
$ sudo chown –R $USER:$USER /var/www/thia
• $ sudo chmod –R 755 /var/www/thiagoalves

3-Passo

Crie um HTML de teste  e deposite dentro da pasta thiagoalves

4- Passo
VAMOS CRIAR O ARQUIVO.CONF (ATENÇÃO ESTA PARTE É IMPORTANTE)

Crie um arquivo em

/etc/apache2/sites-
available.

Nocaso eu criei thiagoalves.conf

Nesse arquivo insira as informações a seguir
<VirtualHost *80:>
  ServerAdmin thiag.alves.avs@gmail.com 
  ServerName thiago.alves.avs.com
  ServerAlias www.thiago.alves.avs.com  
  DocumentRoot /var/www/thiagoalves
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/acess.log combined
<VirtualHost>
  
- Passo 5

ATIVE SEU HOST VIRTUAl COM O COMANDO
sudo a2ensite thiagoalves.conf

- Passo 6 Configure o arquivo de host local

Como não configuramos um servidor DNS para resolver a requisição feita ao
navegador vamos criar uma entrada no arquivo /etc/hosts. Acesse esse
arquivo e insira a seguinte informação:
• localhost thiago.alves.avs.com
• localhost www.thiago.alves.avs.com

- Passo 7
Reinicie o apache

sudo service apache2 restart

- Passo 8 testando

Abra o navegador e digite
www.thiago.alves.avs.com
