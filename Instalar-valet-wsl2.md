### Update apt
    $ sudo apt update
### Install php
    $ sudo apt install php-fpm php-curl php-mbstring php-mysql php-xml php-cli unzip network-manager libnss3-tools jq xsel
### Install mysql sever
    $ sudo apt install mysql-server
### Install composer
    $
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('sha384', 'composer-setup.php') === 'c31c1e292ad7be5f49291169c0ac8f683499edddcfd4e42232982d0fd193004208a58ff6f353fde0012d35fdd72bc394') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"
    $ sudo mv /home/arnoldfederis/composer.phar /usr/bin/composer
### Install valet
    $ composer global require cpriego/valet-linux
    $ echo 'export PATH="$PATH:$HOME/.config/composer/vendor/bin"' >> ~/.profile
    $ source ~/.profile
    $ valet install
### Create new laravel app
    $ cd ~/.valet/Sites
    $ valet park
    $ composer create-project --prefer-dist laravel/laravel appname
### Fix problem in installing laravel
    $ sudo apt install resolvconf
    $ sudo nano /etc/resolvconf/resolv.conf.d/head
    nameserver 8.8.4.4
    nameserver 8.8.8.8
    $ sudo service resolvconf restart
### Full path of ubuntu
    $ C:\Users\<username>\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState
### Full path of valet sites
    $ C:\Users\<username>\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState\rootfs\home\<username>\.valet\Sites
