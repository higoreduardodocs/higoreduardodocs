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
