# Guia Git e GitHub

## Git

*  Verificando a versão do git:
```
git --version
```

*  Listando as configurações:
```
git config --list
```

*  Configurando user name global:
```
git config --global user.name "nome..."
```

*  Configurando user email global:
```
git config --global user.email "email..."
```

*  Gerando chave ssh:
```
ssh-keygen
```

*  Iniciando o controle:
```
git init
```

*  Verificando o status:
```
git status
```

*  Passando objetos de "Working Directory" para "Staging Area":
```
git add .
```

*  Passando objetos de "Staging Area" para "Repository Local":
```
git commit -m "descrição-da-alteração"
```

*  Passando objetos de "Working Directory" para "Repository Local":
```
git commit -a -m "descrição-da-alteração"
```

* Voltando um objeto de "Staging Area" para "Working Directory":
```
git reset HEAD nome-arquivo-objeto
```

* Voltando a versão de um objeto:
```
git checkout --nome-arquivo-objeto
```

* Excluindo definitivamente um objeto:
```
git rm nome-arquivo-objeto
```

* Exibindo o log:
```
git log
```

* Listando as branchs (ramificações):
```
git branch
```

* Criando uma branch (ramificação):
```
git branch nome_da_branch_b
```

* Mudando da branch_a para a branch_b:
```
git checkout nome_da_branch_b
```

* Criando e mudando para uma nova branch_b:
```
git checkout -b nome_da_branch_b
```

* Unificando branchs:
```
git merge nome_da_branch_b
```
> Este comando unifica a branch_b com a branch_a. 
Para que a unificação ocorra você deve sair da branch_b e mudar para a branch_a antes de executar merge.

* Apagando uma branch já unificada:
```
git branch -d nome_da_branch_b
```

* Enviando para o GitHub:
```
git remote add origin git@github.com:nome-de-usuario/repository.git
git push -u origin master
```

* Obtendo alterações/atualizações do GitHub:
```
git pull origin master
```

* Ferramenta gráfica para verificar alterações:
```
gitk
```

* Arquivo ".gitignore":
```
Uma informação por linha. Aceita nomes de arquivos, nomes de diretórios e outros.
```

* Preparando um cenário para controle em equipe utilizando-se de um servidor local/central:
> Antes de mais nada é necessário compartilhar a pasta no servidor central.

Comando | Descrição
------- | ---------
git init --base | Comando que deve ser executado no servidor
git clone file:////server/pastaProjetos/pastaProjeto1 [apelidoLocalParaProjeto1] | Comando que deve ser executado em um computador cliente1
git add . | Executar no computador cliente1
git commit -m "descrição..." | Executar no computador cliente1
git push origin master | Executar no computador cliente1
git clone file:////server/pastaProjetos/pastaProjeto1 | Executar num computador cliente2
git pull origen master | Executar em qualquer computador cliente para pegar as alterações do servidor central

## GitHub

* Colaborando com projetos:
```
fork
```

* Enviando sugestões:
```
pull request
```

### Interessante

* Gitflow Workflow Atlassian: [https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow]
* git-flow: [https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html]