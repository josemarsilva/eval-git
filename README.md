# README - eval-git

## 1. Introduction

Este repositório contém uma demonstração de avaliação das diversas funcionalidades da ferramenta **Git**:

---
## 2. Documentation

### 2.1. O que é o Git

* Git é uma ferramenta __OpenSource__ de controle __distribuído__ de de códigos fontes.

### 2.2. O que este projeto vai explorar

O objetivo deste projeto é explorar os principais conceitos, comandos e cenários possíveis.

* [Instalação](#31-instalação)
* [Documentação e Guias](#32-documentação-e-guias)
* [Inicializando repositório](#33-inicializando-repositório)
* [Criando primeiro arquivo no repositorio](#34-criando-primeiro-arquivo-no-repositorio)


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
* [Laboratório Github(https://youtu.be/9S0p8YMQzsM)
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
* Adicionando-o ao controle do repositório [`git add`](https://help.github.com/en/articles/adding-a-file-to-a-repository) e [`git commit`](https://git-scm.com/docs/git)
* Sincronizando com o repositório centralizado do GitHub [`git remote add`](https://help.github.com/en/articles/adding-a-remote)

```bat
C:\..\eval-git> echo "# eval-github" >> README.md
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
C:\..\eval-git> git remote add origin https://github.com/josemarsilva/eval-github.git
C:\..\eval-git> git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.03 KiB | 1.03 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/josemarsilva/eval-github.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

### 3.4. Criando primeiro arquivo no repositorio


## I - References

* [Git Help](https://git-scm.com/)
