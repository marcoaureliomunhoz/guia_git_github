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
#1) Todos os commits:
git log

#2) Último commit:
git log -1
```

* Exibindo o sumário:
```
git show --summary
```

* Listando as branchs (ramificações):
```
#1) Listando só as branchs locais
git branch

#2) Listando todas as branchs, locais e remotas
git branch -a
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

> Caso ocorra algum conflito em um arquivo será necessário remover as linhas adicionadas que indicam as diferenças, ou seja, você precisa resolver o conflito. Depois de resolver o conflito dentro do arquivo você precissa adicionar este arquivo modificado na "Staging Area" e depois realizar outro commit. Importante: tudo o que está entre **<<< HEAD (Current)** e **===** faz parte das alterações feitas na branch_a (current) e tudo o que está entre **===** e **>>> branch_b (Incoming)** faz parte das alterações feitas na branch_b (branch que está "entrando" na branch corrente).

* Apagando uma branch já unificada:
```
git branch -d nome_da_branch_b
```

> É importante salientar que você não precisa excluir uma branch secundária. É uma boa prática manter essas branchs secundárias. Basta sempre da master você criar uma secundária com nome e versão.

* Clonando um repositório de sua conta no GitHub:
```bash
#1ª opção: este comando vai clonar o repositório repository_xyz dentro da pasta corrente:
git clone git@github.com:nome-de-usuario/repository_xyz.git

#2ª opção: este comando vai clonar o repositório repository_xyz dentro da pasta corrente com outro nome:
git clone git@github.com:nome-de-usuario/repository_xyz.git outro_nome
``` 

* Enviando para o repositório origin e para a branch master do GitHub:
```bash
git remote add origin git@github.com:nome-de-usuario/repository.git
git push -u origin master  
#ou para forçar 
git push -f origin master 
```

> É possível se conectar a outro repositório remoto que foi forkado para empurrar nossas alterações para o fork. Para isso temos que fazer:
```bash
#1) conexão com o outro repositório
git remote add nome_do_outro_repositorio git@github.com:nome-de-outro-usuario/other_repository.git

#2) aqui estamos pegando as alterações da branch master do outro repositório 
git pull nome_do_outro_repositorio master

#3) aqui estamos enviando/empurrando alterações para a branch master do repositório forkado
git push
```

> Não é uma boa prática fazer o push diretamente para a branch master do repositório forkado antes de receber o aceite do proprietário do repositório principal (upstream). O ideal é fazer o seguinte:
- Realize a conexão com o repositório **upstream**
- Realize o **pull** para obter o conteúdo atualizado do repositório **upstream**
- Crie uma nova branch e realize as alterações nesta branch secundária
- Faça o **add** e o **commit** na branch secundária
- Ainda na branch secundária realize um **push** da branch secundária no repositório **origin** forkado
  ```bash
  git push origin nova_branch_secundaria
  ```

* Obtendo alterações/atualizações do repositório origin e da branch master que estão no GitHub:
```
git pull origin master
```

* Listando as conexões remotas:
```
git remote -v
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
