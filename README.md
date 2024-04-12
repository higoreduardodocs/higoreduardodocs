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

<details>

  <summary> :scroll: DevOps</summary>

  > Help:
  ```
  docker compose --help
  docker volume --help
  ```

  > Build:
  ```
  docker build .
  docker build . -t <file-name>
  docker build . --tag <username>/<repository-name>:<version>
  docker compose -f <docker-compose.yml> build
  ```

  > Run:
  ```
  docker start <container-id|container-name>
  docker run <image-name>
  docker run -d --name <container-name> <image-name>
  docker run -p 3000:3000 -d --name <container-name> <image-name>
  docker run -p 3000:3000 -v $(pwd):/app -d --name <container-name> <image-name>
  docker run -p 3000:3000 -v $(pwd):/app -v /app/node_modules -d --name <container-name> <image-name>
  docker run -p 3000:3000 -v $(pwd):/app:ro -v /app/node_modules -d --name <container-name> <image-name>
  docker run --env PORT=4000 -p 3000:4000 -v $(pwd):/app:ro -v /app/node_modules -d --name <container-name> <image-name>
  docker run --env-file ./.env -p 3000:4000 -v $(pwd):/app:ro -v /app/node_modules -d --name <container-name> <image-name>
  docker run --name <container-name> \
    -p <port>:<port> \
    -v jenkins_home_3:/var/jenkins_home \
    -v jenkins_backup_3:/srv/backup \
    <username>/<repository-name>:<version>
  ```

  > Up:
  ```
  docker compose up
  docker compose up -d
  docker compose up -d --build
  docker compose -f <docker-compose.yml> up -d
  docker compose -f <docker-compose.yml> up -d --build
  docker compose -f <docker-compose.yml> up -d --build -V
  docker compose -f <docker-compose.yml> up -d --build <service-name> --no-deps
  docker compose -f <docker-compose.yml> up -d --force-recreate <service-name> --no-deps
  docker compose -f <docker-compose.yml> up -d <service-name>
  docker compose -f <docker-compose.yml> up -d <service-name> --node-deps
  docker compose -f <docker-compose.yml> up -d --scale <service-name>=2
  ENV_SETUP=value docker compose -f <docker-compose.yml> up -d
  ```

  > Down:
  ```
  docker stop <container-id|container-name>
  docker compose down
  docker compose down -v
  docker compose -f <docker-compose.yml> down
  docker compose -f <docker-compose.yml> down -v
  docker swarm leave -f
  ```

  > Exec:
  ```
  docker exec -it <container-name> <function>
  mongo -u "<username>" -p "<password>"
  docker exec -it <container-mongo> mongo -u "<username>" -p "<password>"
  docker compose exec <service-name> <function>
  ```

  > Logs:
  ```
  docker logs <container-id|container-name>
  docker logs <container-id|container-name> -f
  docker compose logs <service-name>
  docker compose logs <service-name> -f
  ```

  > Inspect:
  ```
  docker inspect <container-name> | grep backup
  docker network ls
  docker info
  ```

  > Container list:
  ```
  docker images
  docker ps
  docker ps -a
  docker container ps
  docker container ps -a
  docker volume ls
  ```

  > Remove container:
  ```
  docker rm <container-id|container-name>
  docker rm <container-id|container-name> -f
  docker rm <container-id|container-name> -fv
  docker rmi <image-id|image-name>
  docker system prune
  docker volume rm <volume-id>
  ```

  > Swarm:
  ```
  ip addr [eth0]
  http://<ip-address>
  docker swarm init --advertise-addr <ip-address>
  docker compose -f <docker-compose.yml> build
  ENV_SETUP=value docker stack deploy -c <docker-compose.yml> <app-name>
  ```

  > Swarm list:
  ```
  docker node ls
  docker stack ls
  docker service ls
  docker stack services <app-name>
  docker stack ps <app-name>
  ```

  > Docker hub:
  ```
  docker login
  docker logout
  cat /home/<username>/.docker/config.json

  docker image tag <local-image-name> <username>/<repository-name>:<version>
  docker push <username>/<repository-name>:<version>
  docker compose -f <docker-compose.yml> push <username>/<repository-name>:<version>

  docker pull <username>/<repository-name>:<version>
  docker compose -f <docker-compose.yml> pull
  docker compose -f <docker-compose.yml> pull <service-name>
  ```

  > SSL:
  ```
  FROM nginx:table-alpine
  docker exec -it <container-name> sh
  apk update && apk upgrade
  apk add openssl
  mkdir /etc/nginx/certificate
  cd /etc/nginx/certificate
  openssl req -new -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out nginx-certificate.crt -keyout nginx.key
  vi /etc/nginx/conf.d/default.conf (1,$d | wq)
  cd /etc/init.d/
  nginx -s reload

  FROM nginx:latest
  docker exec -it <container-name> bash
  ln -s /etc/nginx/conf.d/default.conf /etc/nginx/sites-enabled/
  apt-get update
  apt-get install certbot python3-certbot-nginx
  certbot --nginx -d www.localhost
  ```

</details>

<details>

  <summary> :scroll: JavaScript/TypeScript</summary>

  > React/Native/Next:
  ```
  yarn create vite
  yarn create next-app
  yarn create expo
  yarn start
  yarn start --clear

  yarn add -D tailwindcss postcss autoprefixer
  yarn tailwindcss init -p

  yarn prisma init
  yarn prisma migrate dev --name <migrate-name>
  yarn prisma db push
  ```

  > Node:
  ```
  yarn tsc --init
  yarn init -y
  ```

</details>

<details>

  <summary> :scroll: Mongo</summary>

  > URI:
  ```
  mongodb://<username>:<password>@<ip-address>:<port>/<database>?authSource=admin
  mongodb://<ip-address>:<port>/<database>
  ```

  > Access bash:

  ```
  docker exec -it mongo bash
  docker exec -it mongo mongo -u<username> -p<password>
  docker exec -it mongo mongo
  mongo <database> -u <username> --authenticationDatabase <password> -p

  show dbs
  use <database>
  show users
  use admin
  db.createUser({user:"admin",pwd:"admin",roles:["root"]});
  db.createUser({user:"admin",pwd:"admin",roles:[{"role":"readWrite","db":"mongo-dev"}]});
  ```

</details>

<details>

  <summary> :scroll: PostgreSQL</summary>

  > Access bash:
  ```
  docker exec -it <service-name> psql -U <username> <database>

  \dt
  SELECT * FROM pg_catalog.<table>;
  sudo -u postgres psql
  ALTER USER postgres PASSWORD <password>;
  psql -h localhost -U postgres
  createdb -h localhost -U postgres -W <database>
  ```

</details>

<details>

  <summary> :scroll: PHP</summary>

  > Laravel:
  ```
  composer create-project --prefer-dist laravel/laravel <project-name>
  composer require laravel/jetstream
  php artisan jetstream:install livewire

  php artisan serve

  php artisan migrate
  php artisan migrate:fresh
  php artisan migrate:status
  php artisan migrate:rollback
  php artisan migrate:reset
  php artisan migrate:refresh

  php artisan make:migration create_products_table
  php artisan make:migration add_category_to_products_table

  php artisan make:controller EventController
  php artisan make:model Event

  @if(cond)
    ...
  @elseif(cond)
    ...
  @else
    ...
  @endif

  @for($i = 0; $i < count($arr), $i++)
    <p>{{ $arr[$i] }} - {{ $i }}</p>
  @endfor

  @foreach($arr as $var)
    <p>{{ $var }} - {{ $loop->index }}</p>
  @endforeach

  @php
    ...
  @endphp

  @yield('content')
  @yield('title')

  @extends('layouts.main')
  @section('title', 'Home')

  @section('content')
    ...
  @endsection

  @csrf
  @method("PUT")

  @auth
    ...
  @endauth

  @guest
    ...
  @endguest

  {{ $variable }}
  {{-- Comment --}}
  ```

</details>

<details>

  <summary> :scroll: Python</summary>

  > Overview:
  ```
  Linguagem dinâmica, possui IDLE (python3) já no instalador da linguagem. As variáveis são armazenadas referenciando endereço de memória, fazendo com que seja possíveis várias variáveis apontarem para mesmo endereço reduzindo consumo de memória. Suas classes possuem atributos e comporamentos quando instanciadas. O escopo da linguagem é fechado com indentação de código e não blocos. As funções podem receber parâmetros obrigatórios no-default arguments como opcionais default arguments, além disso em sua chamada esses parâmetros podem ser passados de forma posicional ou nomeadas também conhecido como keywords arguments. Atributos protected/private devem ter undescore em sua declação como exemplo: "\_variable". No desenvolvimento de API's é usual quando trabalhar com data/hora usar UTC-0 de acordo com padrão ISO 8601. Em testes a utilização de mocks é ideal para simular condições reais não fazendo requisições externas ou consumindo muito recursos da máquina, é ideal utilizar a cobertura completa de testes no projeto text coverage.
  ```

  > Default:
  ```
  Tipos primitivos:
  - String "Hello world"
  - Int 10
  - Float 9.99
  - Bool True/False
  - Empty: ""
  - Null: None

  Estruturas de dados:
  - Tuple (10, "Name")
  - List [10, 20, "Name"]
  - Set: {"Name", 20}
  - Dict: {"key": 20}

  Operadores aritméticos
  - Sum: 10 + 15
  - Subtract: 10 - 15
  - Multiply: 10 * 15
  - Divisão: `10 / 15`
  - Divisão inteira: `10 // 15`
  - Potência: `10 ** 15`
  - Módulo: `10 % 15`

  Operadores relacionais:
  - Igualdade: `2 == 2`
  - Diferença: `2 != 2`
  - Maior: `2 > 2`
  - Maior/Igual: `2 >= 2`
  - Menor: `2 < 2`
  - Menor/Igual: `2 <= 2`

  Operadores lógicos:
  - Negação: `not`
  - Conjunção: `and`
  - Disjunção: `or`

  Estruturas condicionais
  a = 10
  if a > 20:
    print("a > 20")
  elif a > 10:
    print("a > 10")
  else:
    print("a < 10")

  Estruturas de repetição:
  i = 1
  while i < 10:
    print(i)
    i += 1
  ```

</details>

> :copyright: [Higor Eduardo Docs](https://github.com/higoreduardodocs)
