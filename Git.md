# Git Cheatsheet

## Configurar o git

Inicia o repositório na pasta atual
>git init 

Configurar User name e Email

>git config --global user.email {email}

>git config --global user.name {name}

## Committing

Adiciona um arquivo específico para commit
>git add <arquivo> 

Adiciona todos os arquivos alterados/não rastreados
>git add . 

Faz o commit das alterações dos arquivos selecionados 
>git commit -m "<mensagem>" 

Faz o commit de todos os arquivos alterados/que não foram adicionados ao controle de versão
>git commit -a 

## LOG

//Lista os commits realizados
>git log 

//Detalha o log de alterações e quais alterações realizadas
>git log -p 


>git log -p -n (n: número. Detalha a quantidade de logs)

Resumo das alterações
>git log --pretty=oneline 

Resumo das alterações formatado
>git log --pretty=format: "%h - %an, %ar - % s" 

Busca o log desde "N" dias ou weeks etc
>git log --since=N.days 

## ignorar arquivos

Criar arquivo de texto ".gitignore" e adicione os arquivos ou diretórios por linha

## Voltar versões do GIT

Listar os commits em ordem descrescente
>git log 

>git checkout <Hash commit>

Volta uma quantidade de commits sendo 'N' a quantidade.
>git reset HEAD~N 

Remove o commit mas deixa os arquivos com alterações
>git reset HEAD~N --soft 

Remove o commit e remove os arquivos com alterações !ATENÇÃO!
>git reset HEAD~N --hard

## BRANCHES

Exibe o branch atual e lista os branches existentes
>git branch 

Exibe os branches locais E remotos
>git branch -a 

Cria e seleciona o novo branch
>git checkout -b <nome do branch> 

Muda para o branch informado
>git checkout <branch> 

## MERGE

Puxa as alterações do branch informado criando um commit
>git merge <nome do branch> 

Puxa as alterações pro branch atual sem criar o commit
>git rebase <nome do branch> 

## Gerar chave pública pro Github

>ssh-keygen

## Adicionar repositório Git remoto

>git remote add origin <url repositório>

## Push para repositório remoto

Faz o upload do branch para o github
>git push origin <branch> 

## Clonar repositório

Colna o repositório remoto dentro da pasta selecioada
>git clone <url ou ssh do repositório> 

Cria um novo branch baseado no remoto
>git checkout -b <nome do branch> origin/<nome do branch remoto> 

Sincroniza o repositório local com o remoto
>git pull 

Atualiza os arquivos locais com os do repositório
>git pull origin <branch> 

## Tags : Marcadores, servem como release do projeto. A cada nova versão pode gerar uma nova tag.

Lista todas as tags
>git tag -l 

cria a tag localmente
>git tag <conteúdo> 

Subir as tags para o repositório remoto, para gerar a release/versão
>git push origin master --tags 

## Git Bare

Repositório para hospedar os arquivos do repositório.
>git init --bare 

## Git hook : deploy automatizado

## Em construção...