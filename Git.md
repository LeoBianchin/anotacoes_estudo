Git Cheatsheet

configurar o git
	-git config --global user.email "leonardo_bianchin@hotmail.com" 
	-git config --global user.name "Leonardo Bianchin da Silveira" 

git init //Inicia o repositório na pasta atual

git add <arquivo> //Adiciona um arquivo específico para commit
git add . //Adiciona todos os arquivos alterados/não rastreados

git commit -m "<mensagem>" //Faz o commit das alterações dos arquivos selecionados

git commit -a //Faz o commit de todos os arquivos alterados/que não foram adicionados ao controle de versão 


--LOG
git log //Lista os commits realizados
git log -p //Detalha o log de alterações e quais alterações realizadas
git log -p -n // n: número. Detalha a quantidade de logs

git log --pretty=oneline // Resumo das alterações
git log --pretty=format: "%h - %an, %ar - % s" // Resumo das alterações formatado

git log --since=N.days //Busca o log desde "N" dias ou weeks etc

--ignorar arquivos

criar arquivo de texto ".gitignore" e adicione os arquivos ou diretórios por linha

-- Voltar versões do GIT

git log // para listar os commits em ordem descrescente
git checkout <Hash commit>

git reset HEAD~N // Volta uma quantidade de commits sendo 'N' a quantidade.

git reset HEAD~N --soft // remove o commit mas deixa os arquivos com alterações
git reset HEAD~N --hard // remove o commit e remove os arquivos com alterações !ATENÇÃO!

-- BRANCHES
git branch // Exibe o branch atual e lista os branches existentes
git branch -a // Exibe os branches locais E remotos

git checkout -b <nome do branch> // Cria e seleciona o novo branch 

git checkout <branch> // Muda para o branch informado

-- MERGE

git merge <nome do branch> // puxa as alterações do branch informado criando um commit

git rebase <nome do branch> // puxa as alterações pro branch atual sem criar o commit

-- Gerar chave pública pro Github

ssh-keygen

-- Adicionar repositório Git remoto

git remote add origin <url repositório>

-- Push para repositório remoto

git push origin <branch> // Faz o upload do branch para o github

-- Clonar repositório

git clone <url ou ssh do repositório> // faz o 'clone' do repositório remoto dentro da pasta selecioada

git checkout -b <nome do branch> origin/<nome do branch remoto> // cria um novo branch baseado no remoto

git pull // Sincroniza o repositório local com o remoto

git pull origin <branch> // Atualiza os arquivos locais com os do repositório

-- Tags : Marcadores, servem como release do projeto. A cada nova versão pode gerar uma nova tag.

git tag -l // Lista todas as tags

git tag <conteúdo> // cria a tag localmente

git push origin master --tags // Subir as tags para o repositório remoto, para gerar a release/versão

-- Git Bare

git init --bare // Repositório para hospedar os arquivos do repositório. 

-- Git hook : deploy automatizado





