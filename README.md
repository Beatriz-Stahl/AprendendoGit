#  Configuração Inicial do Git e GitHub
* Instalação do Git No Windows

1. Acesse  <http://git-scm.com/download/win> e baixe o instalador do Git para Windows.
2. Execute o instalador e siga as instruções. Durante a instalação, você pode escolher as configurações padrão.

## 1 - Configuração Inicial do Git 
Depois de instalar o Git, você precisa configurá-lo com seu nome de usuário e email. Isso é importante porque cada commit que você fizer usará essas informações.

* Abra o Terminal (ou Git Bash no Windows).
1. Configure seu nome de usuário:

```
git config --global user.name "Seu Nome"
```

2. Configure seu email:

```
 git config --global user.email "seuemail@exemplo.com"
``` 

3. verifique se foi aplicada corretamente as configurações:

```
 git config --global --list 
``` 

### Feito essas configurações existem duas formas de começar a criar um projeto
* Iniciar um repositório local e enviar para o remoto.
* Iniciar um repositório  remoto e trazer para o local.

## 2 - Inicialização de um novo repositório local:
1. Crie um novo diretório e navegue até ele:
``` 
mkdir meu_projeto
cd meu_projeto
``` 
2. Inicialize o repositório 
```
git init
``` 
3. Adicione arquivos ao repositório 

```
echo "# Meu Projeto" >> README.md
git add README.md
  
```
Se ja tiver arquivos criados use ` git add . ` para adicionar ao stage todos arquivos da pasta

4. Faça o primeiro commit local 
``` 
git commit -m "Primeiro commit"
git branch -M main
``` 

5. crie o repositório remoto no gitHub sem criar o README e conecta o local com o remoto 
``` 
git remote add origin https://github.com/usuario/meu-projeto.git
``` 

6.  Enviar o repositório local para o remoto
Envie os commits locais para o repositório remoto:
```
git push -u origin main
``` 

## 3 - Inicialização de um novo repositório remoto:
1. Crie um novo repositório no GitHub e Copie a URL do repositório.

2. Crie um novo diretório e navegue até ele:
``` 
mkdir meu_projeto
cd meu_projeto
``` 

3. Clone o repositório 
```
git clone https://github.com/usuario/repo.git
``` 

4. pode utilizar o `git remote -v ` para visualizar os repositorios remotos
* A vantagem de fazer o processo de inicialização remota é que ja vem feita essa configuração pronta  

5. utilizar ` git add . ` para colocar no stage 

6. Para realizar o commit 
```
git commit -m "Primeiro commit"
git branch -M main
``` 
7. Para enviar ao remoto de volta utilize 
```
git push -u origin main
``` 

#### Diferença entre repositórios locais e remotos:
-Repositório Local: Onde você trabalha diretamente no seu computador.

-Repositório Remoto: Onde o código é armazenado em um servidor, permitindo colaboração (ex.: GitHub, GitLab)

## 4 - Trabalhando com Múltiplos Branches
* Criando um Novo Branch

1. Para criar um novo branch, use o comando:
```
git branch nome-do-branch
``` 
2. Troque para o novo branch:
```
git checkout nome_do_branch
``` 
obs: Criar um Novo Ramo e Mudar para ele use :` git checkout -b novo-ramo `, você pode criar um novo ramo e imediatamente mudar para esse ramo.

3. Restaurar Arquivos: Para restaurar um arquivo para o estado de um determinado commit.
```
git checkout commit -- arquivo
``` 
Isso é útil se você quiser desfazer mudanças em um arquivo específico e voltar a uma versão anterior do mesmo.

4. Restaurar Todo o Diretório de Trabalho: Para restaurar todo o diretório de trabalho para o estado de um determinado ramo ou commit.
``` 
git checkout commit
``` 

5. Envie a branch para o repositório remoto e defina o upstream
```
git push -u origin nome-da-branch
```

* Uso prático de branches para diferentes ambientes (desenvolvimento, produção):

Use branches como development e production para separar o código em diferentes estágios.
Mescle (merge) as mudanças de development para production quando estiver pronto para o lançamento.

## 5 - Integração com IDEs




### Alguns comandos interessantes 
-git branch : visualiza qual branch está 
-git checkout -b main : criar e mudar para a branch main 
-git checkout main : confirme q esta no branch main
-git branch -m master main : renomeia master para main 
-git config --global init.defaultBranch main : define main como branch padrao 
-git log --oneline : mostra linha a linha os commits 
