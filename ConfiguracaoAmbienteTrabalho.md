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
        

4. Instale as extensões do PHP 8.2
Além do próprio PHP, você provavelmente desejará instalar alguns módulos PHP adicionais. Você pode usar este comando para instalar módulos adicionais, substituindo  PACKAGE_NAME pelo pacote que deseja instalar:

        sudo apt-get install php8.2-PACKAGE_NAME

Você também pode instalar mais de um pacote por vez. Aqui estão algumas sugestões dos módulos mais comuns que você provavelmente desejará instalar:

        sudo apt-get install -y php8.2-cli php8.2-common php8.2-fpm php8.2-mysql php8.2-zip php8.2-gd php8.2-mbstring php8.2-curl php8.2-xml php8.2-bcmath

Este comando irá instalar os seguintes módulos:

php8.2-cli - interpretador de comandos, útil para testar scripts PHP a partir de um shell ou executar tarefas gerais de scripts de shell
php8.2-common - documentação, exemplos e módulos comuns para PHP
php8.2-mysql - para trabalhar com bancos de dados MySQL
php8.2-zip - para trabalhar com arquivos compactados
php8.2-gd - para trabalhar com imagens
php8.2-mbstring - usado para gerenciar strings não-ASCII
php8.2-curl - permite fazer solicitações HTTP em PHP
php8.2-xml - para trabalhar com dados XML
php8.2-bcmath - usado ao trabalhar com flutuadores de precisão
As configurações do PHP relacionadas ao Apache são armazenadas em arquivos  /etc/php/8.2/apache2/php.ini. Você pode listar todos os módulos PHP carregados com o seguinte comando:

        php -m
