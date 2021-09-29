# Docker

Comandos principais

Criar um container a partir de uma imagem

>docker container run :IMAGE:
>>docker container run --name :NOME_DO_CONTAINER: :IMAGE: -atribuir um nome para o container

Cria um container no modo *Daemon*
>docker container run :IMAGE: -d

Para poder executar o container e conseguir executar local é necessário utilizar o *port binding* para vincular as portas locais e as portas do container com a opção `-p`. Sempre a porta à esquerda é a porta local e a direita do container.

>docker container run -d -p 8080:80 :IMAGE:

Existem casos que serão necessários atribuir valores para variáveis de ambiente. Adicionar a opção `-e` para cada variável

>docker container run -d -e :VAR_AMBIENTE:=:VALOR_VARIAVEL: :IMAGE:

Remover um container

>docker container rm :CONTAINER_ID:

Forçar a remoção de um container

>docker container rm -f :CONTAINER_ID:

Baixar imagem do Docker Hub

>docker image pull :IMAGE:

O comando pull busca a imagem do ***Docker registry*** e salva no sistema. Nesse caso, o registro é o [Docker Hub](https://hub.docker.com)

Visualizar as imagens que estão salvas no sistema

>docker image ls

Executar um container com uma execução de um shell do Linux, permitindo executar alguns comandos como `ls -l` ou `uname -a` por exemplo.

Exibe lista de conteineres, por padrão só exibe os que estiverem em execução

>docker container ls

Lista todos os conteineres

>docker container ls -a

Executar uma instancia específica de container

>docker container start :CONTAINER_ID:

Quando executar o comando `docker container ls` novamente, vai exibir a instância que foi iniciada no comando anterior;

Mandar um comando para uma instância de container que estiver em execução

>docker container exec :CONTAINER_ID: ls

---
## Criar imagem Docker

1. Criar uma imagem a partir de um container

Ao criar um container, é possível gerar uma imagem a partir dele. 
Após fazer as configuraçoes necessárias basta executar o seguinte comando:

>docker container commit :CONTAINER_ID:

Para definir o nome da imagem é necessário alterar a tag

>docker image tag :IMAGE_ID:

2. Criar imagem usando um ***Dockerfile***

Um Dockerfile contém instruções para criar a imagem, facilitando o gerenciamento das mudanças, especialmente quando as imagens crescem e se tornam mais complexas.

Por exemplo:

```
FROM alpine
RUN apk update && apk add nodejs
COPY . /app
WORKDIR /app
CMD ["node", "index.js"]
```

1. **FROM** especifica a imagem base
2. **RUN** executa comandos, nesse caso executou 2 comandos dentro do container instalando o Node.js server.
3. **COPY** copia todos os arquivos do diretório de trabalho (".") para dentro do container.
4. **WORKDIR** especifica o diretório que o container deve usar quando inicia.
5. **CMD** especifica comandos para o container executar quando iniciar. 


Após a criação do arquivo ***Dockerfile***, monte a imagem com o seguinte comando

>docker image build -t :NOME_IMAGEM:VERSAO: .

---
# Troubleshoot

---
## Terminologia

*Docker daemon*: O serviço que executa no background no host que gerencia a construção, execução e distribuição dos conteineres.

*Docker client*: A ferramenta de linha de comando para o usuário interagir com o *daemon*

*Docker hub*: É um diretório onde são armazenadas imagens Docker disponíveis publicamente. [Docker Hub](https://hub.docker.com)

*Containers*: Execução de instâncias de imagens Docker.

---

## Referências

[Docker docs](https://docs.docker.com/reference/) 
---

## Em construção...