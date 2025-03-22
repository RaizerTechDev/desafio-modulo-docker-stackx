# Desafio-Modulo-Docker-Stackx

<br>

<div align="left">


## Índice
- [Objetivo](#-objetivo)
- [Atividade 1](#atividade-1-empacotando-uma-aplicação-simples-de-frontend-com-docker)
  - [ Requisitos](#requisitos)
  - [ Como Executar](#como-executar)
  - [ Detalhes da  Imagem](#detalhes-da-imagem)
- [Atividade 2](#atividade-2-implementação-do-wikijs-com-postgresql)
  - [ Requisitos](#requisitos-1)
  - [ Como Executar](#como-executar-1)
  - [ Detalhes da Stackx ](#detalhes-da-stack)
  - [ Persistência de Dados](#persistência-de-dados)



<br>

## Objetivo
 

<br>

## <i>Atividade 1: Empacotando uma aplicação simples de frontend com Docker</i>

Este repositório contém a solução para a Atividade 1 do módulo Docker, onde empacotamos uma aplicação simples de frontend usando a imagem oficial do Nginx.

***

<div align="center">
  
<img src= "https://media.giphy.com/media/3zSF3Gnr7cxMbi6WoP/giphy.gif" align="center" height="55" width="55"> [Demonstração-Aplicação -atv1] <img src= "https://media.giphy.com/media/E5DzZsofmgxc9wjbhX/giphy.gif" align="center" height="35" width="35">

![Captura de Tela da Aplicação](/assets/images/aplicacao-docker.png)

<br>

---
<div align="left">

<br>

### Requisitos

- Docker instalado e configurado.

***
<br>

### Como executar

<br>

1. Clone este repositório:

   ```bash
   git clone https://github.com/seu-usuario/desafio-modulo-docker-stackx.git

<br>   

2. Navegue até o diretório da atividade 1:
   ``` bash
   cd desafio-modulo-docker-stackx/atv1

<br>

3. Construa a imagem Docker:
    ```bash
    sudo docker build -t desafio-modulo-docker-stackx-atv1 .

<br>

4. Execute o container:
    ```bash
    docker run -d -p 8080:80 --name desafio-atv1 desafio-modulo-docker-stackx-atv1

<br>

5. Acesse a aplicação no navegador:

   Abra o navegador e vá para http://localhost:8080.

<br>

6. Verificar se o container está em execução
   ```bash
   sudo docker ps

<br>

***  

7. Remover o container
   ```bash
   sudo docker rm atv1

<br>

***  

### Detalhes da Imagem:

- Imagem base: nginx:alpine

- Diretório de trabalho: /app

- Variável de ambiente: APP_VERSION=1.0.0

- Porta exposta: 80

- Pacotes instalados: curl, htop, wget

<br>

***

# <i>Atividade 2: Implementação do Wiki.js com PostgreSQL</i>

Este repositório contém a solução para a Atividade 2 do módulo Docker, onde implementamos uma plataforma de documentação chamada **Wiki.js** com um banco de dados **PostgreSQL** usando Docker.

***

<div align="center">
  
<img src= "https://media.giphy.com/media/3zSF3Gnr7cxMbi6WoP/giphy.gif" align="center" height="55" width="55"> [Demonstração-Aplicação Docker-atv2] <img src= "https://media.giphy.com/media/E5DzZsofmgxc9wjbhX/giphy.gif" align="center" height="35" width="35">

![Captura de Tela da Aplicação](/assets/images/wiki.png)

<br>

---
<div align="left">

<br>

## Requisitos

- Docker instalado e configurado.
- Docker Compose instalado.

## Como executar

1. Clone este repositório:

   ```bash
   git clone https://github.com/RaizerTechDev/desafio-modulo-docker-stackx.git


<br>

2. Navegue até o diretório da atividade 2:
    
   ```bash
   cd desafio-modulo-docker-stackx/atv2

<br> 

3. Inicie a stack com Docker Compose:

    ```bash
    sudo docker-compose up -d

 <br>

    
4. Acesse a aplicação Wiki.js no navegador:

    Abra o navegador e vá para http://localhost:3000.

    - Siga as instruções na tela para concluir a configuração inicial do Wiki.js.

 <br> 

## <i>Detalhes da Stack</i>

    Wiki.js: Imagem oficial ghcr.io/requarks/wiki:2.

    PostgreSQL: Imagem oficial postgres:13.

    Portas:

        Wiki.js: 3000

        PostgreSQL: 5432 (interno, não exposto).

    Variáveis de ambiente:

        Banco de dados: wiki

        Usuário: wikijs

        Senha: wikijsrocks

    Persistência de dados:

        Volume wiki_db_data para o PostgreSQL. 

 <br>

## <i>Persistência de Dados</i>

Os dados do PostgreSQL são armazenados em um volume Docker chamado wiki_db_data. Isso garante que os dados sejam mantidos mesmo se o container for reiniciado ou removido. 

  - Como acessar o PostgreSQL e verificar as tabelas.
   
   - Conecte-se ao container do PostgreSQL:

     ```bash
     docker exec -it wiki_db psql -U wikijs -d wiki

 <br>

   - No prompt do psql, você pode executar comandos SQL para interagir com o banco de dados. Aqui estão alguns exemplos:
    
        - Listar todas as tabelas: 

        ```sql
        \dt

 <br>

   - Verificar os dados da tabela users (usuários do Wiki.js):
    
        ```sql
        SELECT * FROM users;

 <br>

   - Verificar os dados da tabela pages (páginas criadas no Wiki.js):
    
        ```sql
        SELECT * FROM pages;

 <br>

   - Sair do psql:     

        ```sql
        \q

 <br>

 7. <i>Como parar a stack</i>

       Execute o seguinte comando no diretório atv2: 

       ```bash
       docker-compose down