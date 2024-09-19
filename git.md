---
"up::": "[[HARD SKILLS]]"
---

###### ver o upstream: 
- git remote -v



---------------



## Sync changes:
```
git add . 
git commit -m "mensagem do commit"
git push
```

---

## ## Creating a GitHub repository (SSH):

- **Create a repository on GitHub**
- Navigate locally to the directory of the local repository you want to sync with the GitHub repository:

```
- git init 
```


**Connect to the remote repository (using SSH):**
```
git remote add origin https://github.com/seu-usuario/seu-repositorio.git
```


**Add the files to the local repository:**
```
git add .
```


**Create the first commit:**
```
git commit -m "Initial commit with Obsidian notes"
```

**Push to GitHub:**
```
git push -u origin master
```

---

## Pulling updates from GitHub (SSH):

```
git pull origin main
```
- Fetch the changes from the `main` branch in the remote repository.
- Merge these changes with your local `main` branch.

```
git fetch origin
```
- This will fetch changes from the remote repository without merging them, allowing you to review the changes before merging manually if needed.

---
## Branch:

Check the current branch:
```
 git branch
```
- If no return, either there is no branch or the branch is still empty, needing the **first commit**.

##### **Rename the local `master` branch to `main`:**
```
git branch -m master main
```

**Set the remote branch to `main`:**
```
git push origin main
```

**Check the remote branches:**
```
git branch -a
```

---
### REBASE:

- Pull the `main` branch with rebase:
```
git pull origin main --rebase
```

-> Resolve conflicts (if any):

- If there are conflicts between your local changes and the changes in the remote repository, Git will stop the rebase process and ask you to resolve the conflicts. To resolve them:

- Open the conflicting files, edit them, and resolve the differences.

- After resolving, add the resolved files:
```
git add <arquivo_com_conflito>
```

- Finish the rebase:
```
git rebase --continue
```

---

## Remove GH repo:

``` git
git remote remove origin
```

- If you want to completely remove the Git repository from your local directory, you can remove the `.git` directory:

`rm -rf .git`

- This will remove all Git-relatrd data from the folder, undoing any version control association.

---

## Generate GitHub SSH key:

- Check if you already have an SSH key

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
