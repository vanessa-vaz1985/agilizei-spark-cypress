# Sobre o projeto
Este projeto foi desenvolvido através do Treinamento Gratuito de Cypress, "Agilizei Spark", ministrado pelo Samuel Lucas.
A playlist pode ser acessada em https://www.youtube.com/watch?v=oqR2qySVVS8&list=PLnUo-Rbc3jjztMO4K8b-px4NE-630VNKY&index=4.
Durante este projeto, utilizei uma máquina com Windows 11, e todas as instalações/execuções foram feitas com o WSL 2, permitindo utilizar o Ubuntu 22.04 no próprio Windows.

## Pré-requisitos
1. Instalar um editor de texto. Neste projeto, utilizei o Visual Studio Code.
2. Instalar NVM (para gerenciar versões do Node.js), Node.js e NPM:
    https://learn.microsoft.com/pt-br/windows/dev-environment/javascript/nodejs-on-wsl

    - Para instalar o NVM, execute o comando:
        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash

    - Para verificar a instalação, execute o comando (possivelmente será necessário fechar e abrir o terminal para verificar a instalação):
        command -v nvm

    - Para verificar a versão do NVM instalada, execute o comando:
        nvm --version

    - Para verificar quais versões do Node estão instaladas, execute o comando:
        nvm ls

    - Para instalar as versões LTS atuais e estáveis do Node.js:
        nvm install --lts

    - Para instalar a versão atual do Node.js:
        nvm install node

    - Para verificar se o Node.js está instalado e a versão padrão atual: 
        node --version

    - Para verificar se o NPM está instalado: 
        npm --version

    - Para ver o caminho usado para as versões padrão:
        which npm

    - Para alterar a versão do Node.js que você deseja usar para um projeto:
        - Crie um diretório de projeto: 
            mkdir NodeTest
    
        - Insira o diretório:
            cd NodeTest. 
        
        - Em seguida, digite o comando para alternar para a versão atual: 
            nvm use node
        
        - Ou o comando, para alternar para a versão LTS:
            nvm use --lts
            
        - Para usar o número específico para qualquer versão adicional instalada, use o comando:
            nvm use v8.2.1

        - Para listar todas as versões disponíveis do Node.js, use o comando: 
            nvm ls-remote

3. Iniciar um projeto node com configuração padrão (ao final da execução, verifique que o arquivo package.json foi criado):
    npm init -y

4. Instalar Cypress:
    https://docs.cypress.io/guides/getting-started/installing-cypress

    - No diretório do projeto, executar o comando (ao final da execução, verifique que o cypress foi incluído no arquivo package.json como dependência). O comando abaixo instala uma versão específica do Cypress, a qual foi utilizada durante o curso:
        npm install cypress@6.7.0 --save-dev

## Implementando o teste
1. Iniciar o Cypress (ao final da execução, verifique que foi criada a pasta cypress, com a estrutura inicial do projeto):
    npx cypress open

2. Aplicação que utilizaremos nos testes deste curso:
    https://devfinance-agilizei.netlify.app/

3. Comando para executar o teste, redimensionando a tela (para validar responsividade):
    npx cypress open --config viewportWidth=411,viewportHeight=823

4. Comando para executar em modo headless:
    npx cypress run --config viewportWidth=411,viewportHeight=823

5. É possível configurar os comandos no arquivo package.json. E para executá-los no terminal, informamos desta forma:
    npm run cypress:run:mobile