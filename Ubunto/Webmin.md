# Instalar o Webmin para gerenciar o ubunto server

sudo echo "deb http://download.webmin.com/download/repository/ sarge contrib" | sudo tee -a /etc/apt/sources.list

        sudo echo "deb http://download.webmin.com/download/repository/ sarge contrib" | sudo tee -a /etc/apt/sources.list
    
        wget -q http://www.webmin.com/jcameron-key.asc -O- | sudo apt-key add -

        sudo apt-get update

        sudo apt-get install webmin apt-transport-https

<p>Para acessar o Webmin você precisa digitar no navegador o endereço: https://ip-do-servidor:10000 (lembre-se de alterar ip-do-servidor para o endereço IP do computador onde o Webmin foi instalado.</p>