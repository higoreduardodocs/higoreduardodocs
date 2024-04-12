# :dart: Documentation

- :eyes: I’m interested in developing software
- :revolving_hearts: I'm looking to collaborate with easy and quick software documentation

<details>

  <summary> :scroll: Git</summary>

  > Git SSH:

  ```
  cd ~/.ssh
  ssh-keygen -t rsa -b 4096 -C "<email-address>" -f "<github-username>"
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/<github-username>
  touch config
  clip < ~/.ssh/github-username.pub
  ```

  > Git config:

  ```
  #username account
  Host github.com-username
      		HostName github.com
      		User git
      		IdentityFile ~/.ssh/github-username
  ```

  > Git remote access:

  ```
  git clone git@github.com-<github-username>:username/<reponame.git>
  git clone -b <branch-name> <repository-name> .
  git clone --single-branch <branch-name> <repository-name>
  git remote add origin git@github.com-<github-username>:<reponame.git>
  git push
  git pull
  git branch -b <branch-name>
  git add <file-name>
  git commit -m "<commit-message>"
  git push --origin
  ```

  > Git local user:

  ```
  git config --list
  git config user.email "<email-address>"
  git config user.name "<github-username>"
  git config --global user.email "<email-address>"
  git config --global user.name "<github-username>"
  ```

  > Git commit:

  ```
  git init
  git add <filename>
  git commit -m "<commit-message>"
  git remote add origin https://github.com/<github-username>/<repository-name>
  git push -u origin main
  git push --set-upstream origin main
  git pull origin main
  git status
  ```

  > Git branch:

  ```
  git branch
  git checkout -b <branch-name>
  git branch -M <branch-name>
  git checkout <branch-name>
  git push origin <branch-name>
  git pull origin <branch-name>
  git checkout main
  git switch main
  git branch -d master
  ```

  > Historic:

  ```
  git log
  git log --oneline
  ```

  > Restore:

  ```
  git restore <filename>
  git checkout <filename>
  ```

  > Edit:
  ```
  git commit --amend --no-edit
  git push -f origin main
  ```

</details>

<details>

  <summary> :scroll: Linux</summary>

  > WSL:
  ```
  wsl --update
  wsl --set-default-version 2
  wsl --install
  ```

  > Node:
  ```
  curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
  sudo apt install Node.js
  sudo apt purge nodejs
  sudo apt autoremove
  sudo apt install nodejs
  ```

  > File:
  ```
  sudo mv <name-folder/> <target-folder/>
  cp <name-folder/file-name> <target-folder/>
  nano <file-name>
  touch <file-name>
  open <file-name>
  cat <file-name>
  less <file-name>
  rm -rf <folder-name|file-name>
  ls -ltra
  ls -la
  ```

  > Enviroment:
  ```
  printenv
  export ENV_VAR=value
  sudo su
  vi /root/.env
  vi /root/.profile [set -o allexport; source /root/.env; set o+ allexport;]
  echo $PATH
  ```

  > OpenSSL:
  ```
  openssl
  openssl genrsa
  openssl genrsa -aes256
  openssl genrsa -aes256 -out private.pem
  openssl rsa -in private.pem -outform PEM -pubout -out public.pem
  openssl genrsa -des3
  openssl genrsa 4096
  nslookup <url>
  ```

  > Encryption:
  ```
  md5 <file-name>
  shasum <file-name>
  shasum -a 256 <file-name>
  shasum -a 512 <file-name>
  ```

</details>

> :copyright: [Higor Eduardo Docs](https://github.com/higoreduardodocs)
