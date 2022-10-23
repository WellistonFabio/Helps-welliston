## Docker

Permissão de usuários no sistema:

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
