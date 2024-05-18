# Configuração Inicial do Git e GitHub
* Instalação do Git No Windows

1. Acesse <git-scm.com> e baixe o instalador do Git para Windows.
2. Execute o instalador e siga as instruções. Durante a instalação, você pode escolher as configurações padrão.

## Configuração Inicial do Git 
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

# Feito essas configurações existem duas formas de começar a criar um projeto
* Iniciar um repositório local e enviar para o remoto.
* Iniciar um repositório  remoto e trazer para o local.

### Inicialização de um novo repositório local:
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
git add README.md  
```
ou utilize 
``` 
git add . 
``` 
para adicionar ao stage todos arquivos da pasta

4. Faça o primeiro commit local 
``` 
git commit -m "Primeiro commit"
``` 
5. crie o repositório remoto no gitHub sem criar o README e conecta o local com o remoto 
pode utilizar o 
``` 
git remote -v 
``` 
para visualizar os repositorios remotos 
``` 
git remote add origin https://github.com/usuario/meu-projeto.git
``` 
6 .  Enviar o repositório local para o remoto
Envie os commits locais para o repositório remoto:
```
git push -u origin main
``` 

### Inicialização de um novo repositório remoto:
1. Crie um novo repositório no GitHub e Copie a URL do repositório.

2. Clone o repositório 
```
git clone https://github.com/usuario/repo.git
``` 
* A vantagen de fazer o processo de inicialização remota é que ja vem feita essa configuração pronta 



