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
    
    sudu apt install curl
    
### Instalação do NVM
    
    curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
    
    source ~/.bashrc 
    
### Instalação do Node

    nvm install node

### Instação do valet no linux -- https://cpriego.github.io/valet-linux/

    sudo apt-get install network-manager libnss3-tools jq xsel
    
    sudo apt install php-mbstring php-cli php-curl php-xml php-mysql php-pgsql php-sqlite3
    
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

  #### Registrando Ditetório no valet.
    
  - crie um diretório onde ficarão os projetos web.
    Exemplo:
        
        mkdir code
  
  - Entre no diretório escolido: todos os projetos no diretório vão ser acessado "http://diretorio.test"
  
        valet park
        
  - Comando para ver as paths;
        
        valet paths

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

