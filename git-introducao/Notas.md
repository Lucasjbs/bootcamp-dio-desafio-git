# Anotações de Introdução ao Git e ao GitHub

***

## Entendendo o que é Git e sua importância:

É importante usar o Git e o GitHub para organizar e compartilhar as versões dos projetos, evitando situações onde as novas versões do mesmo projeto são criadas como: projeto1, projeto2, projeto2-final, projeto2-final-de-vdd, etc.

Git e GitHub não são a mesma coisa, apesar de serem complementares.

***

## Comandos básicos para um bom desempenho no terminal:

GUI x CLI (Interface Gráfica x Linha de comando)

Comandos úteis do Windows:
* cd    (diretório atual);
* dir   (lista de diretórios);
* mkdir (cria diretório);
* del   (deleta arquivos);
* rmdir (deletar diretório);
* cls   (clear screen);
* echo  (printa na CLI);
* símbolo '>' (redirecioma fluxo => ex: echo hello > hello.txt);

***

## Realizando a instalação do GIT:

Ir para 'git-scm.com'

Mudanças da versão 2.28 para 2.30

Problemas com as mudanças de versão

Mudanças no Git Credential Manager

***

## Tópicos fundamentais para entender o funcionamento do Git:

Criptografia SHA1: Exemplo de encriptação com o "olá mundo" usando o sha1

Cada vírgula mudada no código altera completamente o resultado da criptografia

***

## Objetos internos do Git:

Objeto Blob do Git: Contém um tipo, um tamanho, um \0 e o conteúdo.

Digitando os parâmetros do Blob e usando a encriptação manualmente com os mesmos valores, a encriptação sem o Git é igual à com o Git.

As árvores(Trees) armazenam(apontam) Blobs.

Objeto Commit: Aponta para as árvores, autor e parentes.

***

## Chave SSH e Token:

Alterações na autenticação do GitHub

Chave SSH

Passos para criar a chave SSH na máquina local:
* No Git Bash => ssh-keygen -t ed25519 -C ???@gmail.com
* Git Bash na pasta .ssh 
* cat id_ed25519.pub 
* Copiar chave ssh
* No GitHub => Settings => SSH and GPG Keys => Add new SSH => Colar chave SSH
* No Git Bash => eval $(ssh-agent -s) => ssh-add id_ed25519 

Mesmo processo no Linux e MAC

Token de acesso pessoal

***

## Iniciando o Git e criando um commit:

Listar arquivos ocultos no Git Bash: ls -a

Configuração:
* git config --global user.email "?????@gmail.com"
* git config --global user.name Nome
* git add .
* git commit -m "first commit"

=> master (root-commit) 996de7c /* Esses números são o início do SHA1 */

***

## Passo a passo no ciclo de vida:

Untracked => Unmodified => Modified => Staged (=> Commit => Unmodified)

Repositório remoto => servidor // Ambiente de Desenvolvimento => Local

Comandos:
* git status
* git add index.html receitas/

***

## Trabalhando com o GitHub:

Conta no GitHub

Comandos: 
* git config --list (repare em user.name e user.email)
* git config --global --unset user.name (Apaga o user.name das cofigurações)
(é ideal que o email e nome sejam os mesmos do GitHub)
* git remote add origin git@github.com:Nome/repositorio.git
* git remote -v
* git push origin master

Histórico de commits:

Número SHA1 no canto superior direito: 16741a1 17 minutes ago

1 parent 8908cbd commit 16741a145e9c43bb9e3aa292c3971c8897547470

Clicando no parente, o Git navega para o commit anterior e assim por diante.

Também é possivel navegar pelo histórico clicando em "3 commits"

Se o o email e nome não forem os mesmos do GitHub, os commits criados por eles serão salvos no GitHub como um usuário sem conta no GitHub.

***

## Como os conflitos acontecem no GitHub e como resolvê-los:

Alteração do código simultaneamente na mesma linha: Conflito de Merge

Git Push Rejected: Alterações que não foram integradas

Para integrar as alterações (feitas por outro editor) é utilizado o git pull:
* git pull origin master

Quando existe um conflito de merge: Alterações na mesma linha / arquivo. É necessário corrigir o conflito no arquivo manualmente para então usar o git push.

Clonar projeto:
* git clone git@github.com:Nome/repositorio.git
