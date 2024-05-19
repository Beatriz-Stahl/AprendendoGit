# Índice
1. [Configuração Inicial do Git](#configura%C3%A7%C3%A3o-inicial-do-git)
2. [Inicialização de um novo repositório local](#inicializa%C3%A7%C3%A3o-de-um-novo-reposit%C3%B3rio-local)
3. [Inicialização de um novo repositório remoto](#inicializa%C3%A7%C3%A3o-de-um-novo-reposit%C3%B3rio-remoto)
4. [Trabalhando com Múltiplos Branches](#trabalhando-com-m%C3%BAltiplos-branches)
5. [Integração com IDEs](#integra%C3%A7%C3%A3o-com-ides)
6. [Estratégias de Branching](#estrat%C3%A9gias-de-branching)
7. [Commits e Gerenciamento de Versão](#commits-e-gerenciamento-de-vers%C3%A3o)
8. [Fluxo de Trabalho Avançado](#fluxo-de-trabalho-avan%C3%A7ado)


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
### VScode:
* Instalação da extensão Git:
1. Abra o VSCode.
Vá para Extensões (Ctrl+Shift+X) e procure por "GitLens" e "Git History".

2. Instale as extensões.

* Gerenciamento de branches e commits através do VSCode:
1. Abra o painel de controle de versão (Ctrl+Shift+G).

2. Use os botões e menus para criar, alternar e gerenciar branches, commits e outras operações Git.

### Eclipse:
* Configuração do plugin EGit:
1. Vá para Help > Eclipse Marketplace.

2. Procure por "EGit" e instale.

* Execução de operações Git dentro do Eclipse:
1. Navegue até Window > Show View > Other > Git.

2. Use as opções para clonar repositórios, criar branches, realizar commits, etc.

### Android Studio:
* Uso do controle de versão integrado:
1. Vá para VCS > Enable Version Control Integration.

2. Selecione Git e siga as instruções para configurar seu repositório.

3. Use as opções no menu VCS para gerenciar branches, commits, etc.

## 6 - Estratégias de Branching
É interessante criar branchs distintas quando se tem um desenvolvimento muito grande de equipes, dessa forma podemos ter um fluxo como:
- branch Prodution : que é a principal do sistema, é onde o software estará em produção
- branch development : que é uma copia da prodution onde os desenvolvedores podem clonar e fazerem as modificações.
- branch feature : é onde os desenvolvedores vão trabalhar podendo ser varias features que ao final elas se mescle com o development.

* Crie um branch para cada nova funcionalidade:
```
git checkout -b feature/nova_funcionalidade
``` 
* Mescle as mudanças de volta em development quando a funcionalidade estiver pronta:
```
git checkout development
git merge feature/nova_funcionalidade
```

## 7 - Commits e Gerenciamento de Versão 
* Faça commits frequentemente para registrar o progresso:
```
git add .
git commit -m "Descrição do que foi feito"
```
* Tagging para marcar lançamentos de versões:
```
git tag -a v1.0 -m "Versão 1.0"
```
* Envie a tag para o repositório remoto:
```
git push origin v1.0
```
* Para enviar todas as tags:
```
git push origin --tags 
``` 
* para ver todas as tags listadas:
```
git tag
```
## 8 - Fluxo de Trabalho Avançado
### BACKLOG: 
é uma lista ordenada de tudo que é conhecido que precisa ser feito no projeto.
 #### Componentes do backlog: 
- User Stories - Descrições de funcionalidades do usuário 
- Tasks - itens menores que descrevem o necessario para implementar o User Stories
- Bugs - problemas a serem corrigidos 
- Melhorias - melhorias incrementais nas funcionalidades existentes 

#### Gestão do Backlog:
- Prioridade com base em valor de negócio e urgência.
- Revisão Regular para garantir que esteja atualizado e refletindo as necessidades atuais do projeto.
- Divisão em Sprints: Em metodologias ágeis, o backlog é dividido em sprints, onde um conjunto de itens é selecionado para desenvolvimento em um período específico.

### CHANGELOG: 
Changelog é um documento que registra todas as mudanças feitas no projeto, incluindo novas funcionalidades, correções de bugs e outras alterações importantes. 

#### Estrutura do Changelog
- Versão e data : Cada entrada no changelog começa com a versão e a data de lançamento.
`Exemplo: ## [1.2.0] - 2024-05-18 `

- Categorias de Mudanças:
Adicionado (Added) /  Mudado (Changed) / Corrigido (Fixed) / Removido (Removed) 

### VERSIONAMENTO EM 3 NÍVEIS (X.Y.Z) 
O versionamento utiliza um esquema de três números para denotar versões de software, no formato X.Y.Z, onde:

1. X (Major): Incrementado para mudanças que introduzem alterações significativas.
2. Y (Minor): Incrementado para adicionar uma nova funcionalidade sem quebrar a compatibilidade.
3. Z (Patch):  Incrementado para correções de bugs e pequenas melhorias

#### Exemplo pratico:
- 1.0.0: Primeira versão estável.
- 1.1.0: Adição de uma nova funcionalidade de redefinição de senha.
- 1.1.1: Correção de bug na funcionalidade de redefinição de senha.
- 2.0.0: Introdução de uma nova API de autenticação que quebra a compatibilidade com a versão 1.x.x.

#### Integração de BACKLOG, CHANGELOG e VERSIONAMENTO 
1. Planejamento no Backlog: Organizar tarefas e funcionalidades priorizando o que deve ser desenvolvido. 

2. Desenvolvimento e Commits: Realize commits durante o desenvolvimento garantindo que cada mudança seja clara e documentada.

3. Marcação de versões: lançamentos importantes com tags no Git

4. Documentação no Changelog: Atualize o changelog para cada versão lançada, detalhando as mudanças feitas.

## 9 - Resolução de conflitos 











### Alguns comandos interessantes 
-git branch : visualiza qual branch está 
-git checkout -b main : criar e mudar para a branch main 
-git checkout main : confirme q esta no branch main
-git branch -m master main : renomeia master para main 
-git config --global init.defaultBranch main : define main como branch padrao 
-git log --oneline : mostra linha a linha os commits 
