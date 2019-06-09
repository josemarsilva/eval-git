# README - eval-git

## 1. Introdução

Este repositório contém uma demonstração de avaliação das diversas funcionalidades da ferramenta **Git**:

---
## 2. Documentação

### 2.1. O que é o Git

* Git é uma ferramenta __OpenSource__ de controle __distribuído__ de de códigos fontes.

### 2.2. O que este projeto vai explorar

O objetivo deste projeto é explorar os principais conceitos, comandos e cenários possíveis.

* [Instalação](#31-instalação)
* [Documentação e Guias](#32-documentação-e-guias)
* [Inicializando repositório](#33-inicializando-repositório)
* [Criando primeiro arquivo no repositorio](#34-criando-primeiro-arquivo-no-repositorio)
* [Alterando conteúdo de arquivo](#35-alterando-conteúdo-de-arquivo)
* [Desistindo de alterações e revertendo alterações](#37-desistindo-de-alteracoes-e-revertendo-alteracoes)
  * [Cenário 1: Desistindo da criação de um arquivo local](#371-cenário-1-desistindo-da-criação-de-um-arquivo-local)
  * [Cenário 2: Desistindo de adicionar um arquivo ao repositório local](#372-cenário-2-desistindo-de-adicionar-um-arquivo-ao-repositório-local)
  * [Cenário 3: Removendo um arquivo do repositorio local](#373-cenario-3-removendo-um-arquivo-do-repositorio-local)
  * [Cenário 4: Removendo um arquivo do repositorio centralizado](#374-cenário-4-removendo-um-arquivo-do-repositorio-centralizado)


---
## 3. Projeto Demonstração

### 3.1. Instalação

* Em [https://git-scm.com/](https://git-scm.com/) você encontra link para download e instalação da última versão do Git (gratuita)
* Em [https://github.com](https://github.com) você encontra um serviço de repositório centralizado do Git (gratuito)


### 3.2. Documentação e Guias

* [Handbook](https://guides.github.com/introduction/git-handbook/)
* [Guia de comandos muitos básicos](https://github.github.com/training-kit/downloads/pt_BR/github-git-cheat-sheet/)
* [Guia de uso de branches com Git](https://learngitbranching.js.org/)
* [Laboratório de aprendizado do Git](https://lab.github.com/)
* [Laboratório Github](https://youtu.be/9S0p8YMQzsM)
* [Guia dos principais comandos](https://help.github.com/en#dotcom)


### 3.3. Inicializando repositório

* Incializando um repositório [`git init`](https://help.github.com/en/articles/adding-an-existing-project-to-github-using-the-command-line)

```bat
C:\> REM Step-01: Criando pasta base do repositorio e a pasta do projeto
C:\> md c:\githome
C:\> cd c:\githome
C:\> md eval-git
C:\..\eval-git> git init
Initialized empty Git repository in C:/GitHome/eval-git/.git/
C:\> 
```

### 3.4. Criando primeiro arquivo no repositorio

* Criando primeiro arquivo para o controle de arquivos
* Identificando os arquivos que fazem e que não fazem parte do controle do repositorio [`git status`](https://help.github.com/en/articles/about-status-checks)
* Criar um repositorio público no GitHub
* Adicionando-o ao controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository) e [`git commit`](https://git-scm.com/docs/git)
* Sincronizando com o repositório centralizado do GitHub [`git remote add`](https://help.github.com/en/articles/adding-a-remote)

```bat
C:\..\eval-git> echo "# eval-git" >> README.md
C:\..\eval-git> git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        README.md
        doc/

nothing added to commit but untracked files present (use "git add" to track)
C:\..\eval-git> git add .
C:\..\eval-git> git commit -a -m "primeiro commit"
[master (root-commit) 4100414] first commit
 1 file changed, 61 insertions(+)
 create mode 100644 README.md
 
C:\..\eval-git> git status
```

![github-create-repository-01.png](./doc/github-create-repository-01.png) 

![github-create-repository-01.png](./doc/github-create-repository-02.png) 


```bat
C:\..\eval-git> git remote add origin https://github.com/josemarsilva/eval-git.git
C:\..\eval-git> git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.03 KiB | 1.03 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/josemarsilva/eval-git.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

### 3.5. Alterando conteúdo de arquivo

* Alterando o conteúdo do arquivo
* Identificando que o conteúdo de um dos arquivos foi alterado e não está sincronizado com o repositorio [`git status`](https://git-scm.com/docs/git-status)
* Garantir que as alterações sejam sincronizadas com o repositorio, inclusive o repositório externo à sua máquina no GitHub [`git commit`](https://git-scm.com/docs/git-commit) [`git push`](https://git-scm.com/docs/git-push)

```bat
C:\..\eval-git> echo passei por aqui >> README.md
C:\..\eval-git> git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")


C:\..\eval-git> git commit -a -m "."
[master 7cbddaa] .
 1 file changed, 20 insertions(+), 1 deletion(-)
C:\..\eval-git> git push
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 732 bytes | 732.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/josemarsilva/eval-git.git
   1f973ad..7cbddaa  master -> master
```


### 3.6. Clonando um repositorio de um Git público em sua máquina local

* Obtenha a url do projeto no seu repositório público de [Github](https://github.com/josemarsilva/eval-git). 
* Em seguida execute o comando [`git clone`](https://git-scm.com/docs/git-clone)
* Lembre-se: O clone não pode ser feito sobre um sub diretório que já existe

![github-clone-repository-01.png](./doc/github-clone-repository-01.png) 

```bat
C:\..\eval-git> git clone https://github.com/josemarsilva/eval-git.git
Cloning into 'eval-git'...
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
```


### 3.7. Desistindo de alterações e revertendo alterações

Nesta tópico vamos aprender as [inúmeras possibilidades de desfazer alterações](https://docs.gitlab.com/ee/topics/git/numerous_undo_possibilities_in_git/)

* Criando e commitando no repositorio remoto 3 arquivos para exercícios com um único conteúdo "Initialized". 

```bat
C:\..\eval-git> echo Initialized > file1.txt
C:\..\eval-git> echo Initialized > file2.txt
C:\..\eval-git> echo Initialized > file3.txt
C:\..\eval-git> git add .
C:\..\eval-git> git commit -a -m "."
C:\..\eval-git> git push
C:\..\eval-git> git pull
```

#### 3.7.1. Cenário 1: Desistindo da criação de um arquivo local

* crie um arquivo `file4.txt`
* identifique que o arquivo não faz parte do controle do repositorio [`git status`](https://help.github.com/en/articles/about-status-checks)
* remova `del file4.txt` o arquivo e verifique novamente o controle do repositorio

```bat
C:\..\eval-git> echo Initialized > file4.txt
C:\..\eval-git> git status
   : 
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        file4.txt
   : 
C:\..\eval-git> del file4.txt
C:\..\eval-git> git status
   : 
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
   : 
```

#### 3.7.2. Cenário 2: Desistindo de adicionar um arquivo ao repositório local

* crie um arquivo `file5.txt`
* identifique que o arquivo não faz parte do controle do repositorio [`git status`](https://help.github.com/en/articles/about-status-checks)
* adicione o arquivo no controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository)
* identifique que o arquivo `file5.txt` é um novo arquivo do controle do repositorio mas ainda não foi armazenado no repositorio [`git status`](https://help.github.com/en/articles/about-status-checks)
* desista das alterações locais, podendo recupera-la mais tarde  [`git stash`](https://git-scm.com/docs/git-stash)
* verifique o status das alteraçoes locais no controle do repositório [`git status`](https://help.github.com/en/articles/about-status-checks)
* procure o arquivo `file5.txt` no diretorio. Observe que depois do `git stash` o arquivo não está mais no diretório
* descarte as alterações locais (permanentemente) de um arquivo [`git checkout -- <file>`](https://git-scm.com/docs/git-checkout)
* descarte todas as alterações locais de todos os aquivos permanentemente [`git reset --hard`](https://git-scm.com/docs/git-reset)

```bat
C:\..\eval-git> echo Initialized > file5.txt
C:\..\eval-git> git status
  :
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        file5.txt
  :
C:\..\eval-git> git add .
C:\..\eval-git> git status
  :
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   file5.txt
  :
C:\..\eval-git> git stash
Saved working directory and index state WIP on master: 239353a >
C:\..\eval-git> git status
  :
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
  :
```


#### 3.7.3. Cenário 3: Removendo um arquivo do repositorio local

* crie um arquivo `file6.txt`
* identifique que o arquivo não faz parte do controle do repositorio [`git status`](https://help.github.com/en/articles/about-status-checks)
* adicione o arquivo no controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository)
* faça o commit do arquivo no repositório local[`git commit`](https://git-scm.com/docs/git-commit)
* remova o arquivo `file6.txt` do repositório [`git rm <file>`](https://git-scm.com/docs/git-rm)
* procure pelo arquivo `file6.txt` no diretorio local, observe que ele não está mais lá
* crie um arquivo `file7.txt`
* adicione o arquivo no controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository) e faça o commit no repositório local[`git commit`](https://git-scm.com/docs/git-commit)
* remova o arquivo `file7.txt` do repositório mas mantenha a cópia local em seu diretório de trabalho [`git rm <file> --cached`](https://git-scm.com/docs/git-rm)
* procure pelo arquivo `file7.txt` no diretorio local, observe que ele ainda está lá
* identifique que o arquivo `file7.txt` não faz parte do controle do repositorio mas ainda está disponível no diretório local [`git status`](https://help.github.com/en/articles/about-status-checks)



```bat
C:\..\eval-git> echo Initialized > file6.txt
C:\..\eval-git> git status
  :
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        file5.txt
  :
C:\..\eval-git> git add file6.txt
C:\..\eval-git> git commit -a -m "."
C:\..\eval-git> git status
C:\..\eval-git> git rm file6.txt
C:\..\eval-git> dir file6.txt
Arquivo nao encontrado
C:\..\eval-git> echo Initialized > file7.txt
C:\..\eval-git> git add file7.txt
C:\..\eval-git> git commit -a -m "."
C:\..\eval-git> git rm file7.txt --cached
C:\..\eval-git> git status
  :
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        deleted:    file7.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        file7.txt
  :
C:\..\eval-git> git commit -a -m "."
C:\..\eval-git> dir file7.txt
  :
09/06/2019  17:25                14 file7.txt
  :
```

#### 3.7.4. Cenário 4: Removendo um arquivo do repositorio centralizado

* crie um arquivo `file8.txt`
* adicione o arquivo no controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository) e faça o commit do arquivo no repositório local[`git commit`](https://git-scm.com/docs/git-commit)
* empurre o arquivo para o repositorio centralizado [`git push`](https://git-scm.com/docs/git-push)
* remova o arquivo `file8.txt` do repositório local [`git rm <file>`](https://git-scm.com/docs/git-rm)
* faça o commit do arquivo no repositório local[`git commit`](https://git-scm.com/docs/git-commit)
* empurre o arquivo para o repositorio centralizado [`git push`](https://git-scm.com/docs/git-push)
* procure pelo arquivo `file8.txt` no diretorio local, observe que ele não está mais lá
* procure pelo arquivo `file8.txt` no diretorio remoto

```bat
C:\..\eval-git> echo Initialized > file8.txt
C:\..\eval-git> git add file8.txt
C:\..\eval-git> git commit -a -m "." 
C:\..\eval-git> git push
   :
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 367 bytes | 367.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote: This repository moved. Please use the new location:
remote:   https://github.com/josemarsilva/eval-git.git
To https://github.com/josemarsilva/eval-github.git
   51873a1..44cbcb4  master -> master
   :
C:\..\eval-git> git rm file8.txt
C:\..\eval-git> git commit -a -m "." 
C:\..\eval-git> git push
C:\..\eval-git> dir file8.txt
Arquivo não encontrado
```




### 3.8. Estratégia de gerenciamento de branches

![BranchStrategyWorkflow-Context.png](./doc/BranchStrategyWorkflow-Context.png) 

#### a. master
  * pronto para produção
  * vive "para sempre"

#### b. develop
  * último desenvolvimento pronto para produção
  * criado a partir da __master__

#### c. feature
  * suporte a funcionalidade
  * mais comum e familiar às pessoas porque elas normalmente trabalham nesta branch
  * criado a partir da __develop__
  * deve finalizar com merge em __develop__;

#### d. release
  * suporte a preparação do trabalhao que irá para próxima versão
  * criado a partir da __develop__
  * deve finalizar com merge em __develop__ e __master__
  * convenção de nomes: __release-*__

#### e. hotfix
  * mudanças críticas em produção
  * criado a partir da __master__
  * deve finalizar com merge em __master__ e __develop__
  * convenção de nomes: __hotfix-*__






## I - References

* [Git Help](https://git-scm.com/)
* [Git Branch Model](https://nvie.com/posts/a-successful-git-branching-model/)
