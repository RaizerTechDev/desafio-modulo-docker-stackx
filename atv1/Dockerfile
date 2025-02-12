#  Utilizando a imagem oficial do nginx com a tag alpine (Menor tamanho)

FROM nginx:alpine

# Definindo o diretório de trabalho
WORKDIR /app

#Copiando o arquivo index.html para o diretório de trabalho

COPY index.html /usr/share/nginx/html/index.html

# Instalando os pacotes curl, htop e wget

RUN apk add --no-cache curl htop wget

# Definindo a variável de amiente APP_VERSION

ENV APP_VERSION=1.0.0

# Expondo a porta 80
EXPOSE 80

# Comando para iniciar o nginx quando o container for iniciado
CMD ["nginx", "-g", "daemon off;"]