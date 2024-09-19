---
"up::": "[[HARD SKILLS]]"
---

###### ver o upstream: 
- git remote -v



---------------

## Creating GH repo:

- **cria repo no GH**
-  navega localmente ate o diretório do repo local que quero sincronizar com o repo git
```
- git init 
```


**Conectar ao repositório remoto**
```
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
```


**Adicionar os arquivos ao repositório local:**
```
git add .
```


**Criar o primeiro commit**
```
git commit -m "Initial commit with Obsidian notes"
```

**Enviar para o GitHub**
```
git push -u origin master
```


## Sync changes:
```
git add . 
git commit -m "mensagem do commit"
git push
```


## Pulling att from GH:

```
git pull origin main
```
- Buscar as alterações da branch `main` no repositório remoto.
- Mesclar essas alterações com a sua branch `main` local.

```
git fetch origin
```
trará as alterações do repositório remoto sem mesclá-las, permitindo que você revise antes de mesclar manualmente, se desejar.

## Branch:

verificar branch atual
```
 git branch
```
- se nao retornar nada, ou nao tem branch, ou a branch ainda esta vazia, necessitando o **primeiro commit**

##### **Renomear a branch local `master` para `main`:**
```
git branch -m master main
```

**Configurar o branch remoto para `main`:**
```
git push origin main
```

**Verifique o branch remoto**
```
git branch -a
```

##### REBASE:
Fazer um Pull da branch `main`
```
git pull origin main --rebase
```

 ##### Resolver Conflitos (se houver)
 
Se houverem conflitos entre as suas mudanças locais e as mudanças no repositório remoto, o Git irá parar o processo de rebase e te pedirá para resolver esses conflitos. Para resolver:

Abra os arquivos com conflitos, edite-os e resolva as diferenças.

Após resolver, adicione os arquivos corrigidos:
```
git add <arquivo_com_conflito>
```

Finalize o rebase:
```
git rebase --continue
```



## Remove GH repo:

``` git
git remote remove origin
```

Caso haja um repositório Git e você queira desvinculá-lo, você pode remover o diretório `.git`:

`rm -rf .git`

Isso removerá todos os dados relacionados ao Git dentro da pasta, desfazendo qualquer associação com o controle de versão.

## Generate GitHub SSH key:


Check if you already have an SSH key

```
ls -al ~/.ssh
```


1- Generate a new SSH key

```
ssh-keygen -t ed25519 -C "your_email@example.com"

```


2- Add your SSH key to the SSH agent

```
eval "$(ssh-agent -s)"

```


3- add your SSH key to the agent:

```
ssh-add ~/.ssh/id_ed25519

```


4 -Add your SSH key to **GitHub**

copy the key:
```
	cat ~/.ssh/id_ed25519.pub
```


paste it on GitHub.
