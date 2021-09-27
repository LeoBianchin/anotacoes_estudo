# DOCKER

Fonte: [Tutorial: Colocar um aplicativo .NET Core em contêineres](https://docs.microsoft.com/pt-br/dotnet/core/docker/build-container?tabs=windows)

Para colocar um aplicativo .NET, é necessário publicar ele primeiramente. De acordo com o autor do artigo, é melhor fazer com que o container execute a versão publicada do aplicativo.

Para publicar um aplicativo .NET, execute o seguinte comando enquanto estiver dentro da pasta do projeto no terminal.

>dotnet publish -c Release

## Em construção