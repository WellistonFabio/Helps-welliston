# Configuração do Ambiente de trabalho no Ubuntu

### Instalação do Php.

    sudo apt install php

### Instalação do composer  "site do composer = [http://getcomposer.org](https://getcomposer.org/download/)"
    
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('sha384', 'composer-setup.php') === '55ce33d7678c5a611085589f1f3ddf8b3c52d662cd01d4ba75c0ee0459970c2200a51f492d557530c71c15d8dba01eae') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"

    sudo mv composer.phar /usr/local/bin/composer

### Instalação do Curl
    
    sudo apt install curl
    
### Instalação do NVM
    
    curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
    
    source ~/.bashrc 
    
### Instalação do Node

    nvm install node

### Instação do valet no linux -- https://cpriego.github.io/valet-linux/

    sudo apt-get install network-manager libnss3-tools jq xsel
    
    sudo apt install php-fpm php-curl php-mbstring php-mysql php-xml php-cli unzip network-manager libnss3-tools jq xsel
    
    composer global require cpriego/valet-linux
    
  #### - Editando o arquico bashrc
    
    nano .bashrc
    
    ---- na ultima linha vc vai incluir:
    
    export PATH=$PATH:$HOME/.config/composer/vendor/bin/
    
  #### - Fazendo o load do arquivo bashrc
  
    source ~/.bashrc
    
  #### - Instalar o Valet.
    
    valet install
    
### Para e desabilitar o Apache 2

    sudo systemctl disable apache2
    
    sudo apt-get remove apache2
    
    sudo apt-get autoremove apache2

  #### Registrando Ditetório no valet.
    
  - crie um diretório onde ficarão os projetos web.
    Exemplo:
        
        mkdir code
  
  - Entre no diretório escolido: todos os projetos no diretório vão ser acessado "http://diretorio.test"
  
        valet park
        
  - Comando para ver as paths;
        
        valet paths
        
### Instalar o laravel CLI

    composer global requere laravel/installer

## Instalar o Docker

  - Encontre tudo em : https://docs.docker.com/engine/install/ubuntu/
  
  - Permissão de usuários no sistema:

    1. crie o grupo docker:

            sudo groupadd docker
    
    2. Adicione seu usuário ao grupo docker.

            sudo usermod -aG docker $USER
        
      <p>No Linux, você também pode executar o seguinte comando para ativar as alterações nos grupos:</p>
        
            newgrp docker
       
    3. Faça o logout e login novamente, assim as configurações executadas nos comandos executados anteriormente possam ser carregadas.
   
            sudo reboot
       
    4. Verifique que você pode executar o  docker sem o comando sudo.

            docker run hello-world

## Permissao de execução.

    chmod +x aquivo 

    Para executar um arquivo de script

    sh arquivo
    
## Comando para executar dentro do container 
    docker-compose exec laravel.test bash  

## Takeout: https://github.com/tighten/takeout

    composer global require tightenco/takeout
   
   
   
   
##   Instale o PHP 8.2 no Ubuntu 22.04
### 1. Execute as atualizações do sistema
#### A primeira coisa a fazer em um novo sistema é atualizar nossos repositórios para torná-los atualizados. Execute o comando de atualização também.

        sudo apt update && apt upgrade -y

2. Adicione o repositório Ondrej sury PPA
Para executar o PHP 8.2 no Ubuntu 22.04, precisamos adicionar Ondrej sury PPA em nosso sistema. Este é o mantenedor do repositório PHP no momento. Este PPA não está verificado no momento, portanto, a instalação a partir dele não garantirá resultados de 100%.

Para adicionar este PPA, use o seguinte comando em nosso terminal.

sudo add-apt-repository ppa:ondrej/php
Após a conclusão da instalação, precisamos atualizar os repositórios novamente para que as alterações entrem em vigor.

sudo apt update
Leia também:  Como instalar várias versões do PHP no Ubuntu 22.04

3. Instale o PHP 8.2 no Ubuntu 22.04
Agora devemos poder instalar o PHP 8.2 na máquina Linux Ubuntu 22.04. Os comandos a serem executados são os compartilhados abaixo:

sudo apt install php8.2 -y
Verifique a versão atualmente ativa do PHP com o seguinte comando:

php --version
