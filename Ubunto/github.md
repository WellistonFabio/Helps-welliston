# Instalar e configura o GIT e GitHub

    sudo apt-get update

    sudo apt-get install git

Configurar o usuario.
        
    git config --global user.name "usuario"

Configurar o email do usuario.
 
    git config --global user.email "email"

Verificar se esta tudo certo

    cat .gitconfig

## Comandos Git

        git status  // para ver os estado dos arquivo.  

        git add arquivo // para prepara o arquivo.

        git commit -m "comentário"

        git push // para mandar os arquivos para github

        git clone "endereço HTTP do repositorio"