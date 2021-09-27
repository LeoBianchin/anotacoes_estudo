# Colocar um aplicativo .NET em contêineres

Fonte: [Tutorial: Colocar um aplicativo .NET Core em contêineres](https://docs.microsoft.com/pt-br/dotnet/core/docker/build-container?tabs=windows)

Para colocar um aplicativo .NET, é necessário publicar ele primeiramente. De acordo com o autor do artigo, é melhor fazer com que o container execute a versão publicada do aplicativo.

Para publicar um aplicativo .NET, execute o seguinte comando enquanto estiver dentro da pasta do projeto no terminal.

>dotnet publish -c Release

### Criar arquivo Dockerfile

Dentro da pasta do projeto, crie um novo arquivo *Dockerfile*.

Adicione a linha seguinte no arquivo

> FROM mcr.microsoft.com/dotnet/aspnet:5.0

Nesse caso, o Docker irá puxar a imagem do repositório de conteiner. 
O segmento */dotnet/* indica o repositório, */aspnet* é a imagem e *:5.0* é a versão da imagem.

Executar o seguinte comando no terminal

> docker build -t counter-image -f Dockerfile .


## Em construção...