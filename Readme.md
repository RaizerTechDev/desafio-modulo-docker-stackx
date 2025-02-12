# Desafio-Modulo-Docker-Stackx

<br>

<div align="left">


## Índice
- [Objetivo](#-objetivo)
- [Atividade 1](#atividade-1-empacotando-uma-aplicação-simples-de-frontend-com-docker)
  - [ Requisitos](#requisitos)
  - [ Como Executar](#como-executar)
  - [ Detalhes da  Imagem](#detalhes-da-imagem)


<br>

## Objetivo
 

<br>

## Atividade 1: Empacotando uma aplicação simples de frontend com Docker

Este repositório contém a solução para a Atividade 1 do módulo Docker, onde empacotamos uma aplicação simples de frontend usando a imagem oficial do Nginx.

***

<div align="center">
  
<img src= "https://media.giphy.com/media/3zSF3Gnr7cxMbi6WoP/giphy.gif" align="center" height="55" width="55"> [Demonstração-Aplicação Docker] <img src= "https://media.giphy.com/media/E5DzZsofmgxc9wjbhX/giphy.gif" align="center" height="35" width="35">

![Captura de Tela da Aplicação](images/aplicacao-docker.png)

<br>

---
<div align="left">

<br>

### 1.1 Requisitos

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

