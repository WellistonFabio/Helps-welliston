## Abreviar comando sail

    alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'
    
## camando sail para limpar código

    sail art optimize:clear

## Criar model, Migration e Controller

    sail art make:model Export -mr

## O Tinker é um console interativo do Laravel, um shell do PHP com acesso às classes do nosso projeto.
    sail tinker
