# RabbitMQ

É um serviço open source de messageria, para integração entre serviços.

### Como instalar pelo Docker

Procurar a imagem no [Docker hub](https://hub.docker.com/) chamada *rabbitmq*.

#### Configurar arquivo docker-compose.yml

O arquivo *docker-compose.yml* contém as configurações do container a ser criado e executado pelo docker.

A seguir um exemplo de um arquivo *docker-compose* que configura um servidor com RabbitMQ

```
services:
    rabbitmq: 
        image: rabbitmq:<versão rabbitmq>
        container_name: rabbitmq
        restart: always
        ports:
            - 5672:5672
            - 15672:15672
        volumes:
            - ./dados:/var/lib/rabbitmq
        environment:
            - RABBITMQ_DEFAULT_USER=admin
            - RABBITMQ_DEFAULT_PASS=123456
``` 

Para subir o container com as configurações no arquivo *docker-compose*, execute o seguinte comando no diretório onde se encontra o arquivo.

>docker-compose up -d