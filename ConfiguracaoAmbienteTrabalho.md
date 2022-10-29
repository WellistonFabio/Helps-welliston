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

    
