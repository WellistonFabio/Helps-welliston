# Configurando o Tailwind CSS corretamente no Laravel 9+ com Vite
#### Após iniciar o seu projeto com Laravel Sail, instale o TailwindCSS com os seguintes comandos:

    sail npm install -D tailwindcss postcss autoprefixer

#### Em seguida, crie o arquivo de configuração do TailwindCSS com o seguinte comando:

    sail npx tailwindcss init -p

#### Agora, mantenha o seu conteúdo do tailwind.config.js parecido com esse arquivo:

    /** @type {import('tailwindcss').Config} */

    module.exports = {
        content: [
            "./resources/**/*.blade.php",
            "./resources/**/*.js",
            "./resources/**/*.vue",
        ],
        theme: {
            extend: {
            }
        },
        plugins: [
            require("@tailwindcss/forms"),
            require("@tailwindcss/typography"),
        ],
    }
Aqui existem 2 dependências que devemos instalar com os seguintes comandos:

    sail npm install @tailwindcss/forms

    sail npm install @tailwindcss/typography

Perfeito! O próximo passo agora é adicionar o "core" do TailwindCSS em nosso arquivo app.css (dentro de resources/css):

    @tailwind base;
    @tailwind components;
    @tailwind utilities;
Por fim, vamos executar um build para garantir que tudo está funcionando bem:

    sail npm run build

Se tudo executou com sucesso, vamos alterar nosso welcome.blade.php com o seguinte:

    <!doctype html>
    <html>
    <head>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      @vite(['resources/css/app.css', 'resources/js/app.js'])
    </head>
    <body>
      <h1 class="text-3xl font-bold underline text-white bg-red-500">
        Hello world!
      </h1>
    </body>
    </html>


Beleza! vamos compilar novamente e ver se tudo funciona:

    sail npm run build



Boa! Agora, vamos tentar trabalhar com o desenvolvimento assistido, onde vamos permitir o vite compilar os assets (css e js) em tempo real. Pra isso, usamos o seguinte comando:

    sail npm run dev



Em alguns casos isso vai funcionar, porém em outros não. Nos casos que não funcionar, é porque nosso browser não está conseguindo acessar o servidor de compilação do vite (encontrado no arquivo public/hot).



Para que isso funcione, devemos falar para o vite utilizar a própria URL do nosso localhost, no meu caso, laravel.test (que no meu arquivo hosts aponta para 127.0.0.1). Altere o arquivo vite.config.js da seguinte forma:

    import { defineConfig } from "vite";
    import laravel, { refreshPaths } from "laravel-vite-plugin";
    
    export default defineConfig({
        server: {
            hmr: {
                host: 'laravel.test'
            },
            host: 'laravel.test'
        },
        plugins: [
            laravel({
                input: ["resources/css/app.css", "resources/js/app.js"],
                refresh: [...refreshPaths, "app/Http/Livewire/**"],
            }),
        ],
    });
O que manda pra funcionar perfeitamente aqui é a chave server: {}, mas já vou mostrar pra vocês como fica meu arquivo final trabalhando com TALL Stack.



Agora tente rodar novamente o comando de compilação automática e confira o funcionamento:

    sail npm run dev
