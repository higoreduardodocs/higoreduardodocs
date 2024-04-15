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
  git branch
  git branch -a
  git checkout <origin/branch-name>
  git checkout <branch-name>
  git branch -m <new-branch-name>
  git branch -m <old-branch-name> <new-branch-name>
  git push origin -u <new-branch-name>
  git push origin --delete <old-branch-name>
  git reflog
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
  git reset --hard HEAD~1
  git reset --hard HEAD^
  git push origin HEAD --force
  git reset HEAD@{1}
  git push origin +HEAD^:main
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
  docker inspect <container-name>
  docker inspect <container-name> | grep IPAddress
  docker network ls
  docker info
  sudo lsof -i -P -n | grep <container-port>
  sudo systemctl stop <service-name>
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
  docker volume prune
  docker container prune
  docker image prune
  docker volume rm <volume-id>
  docker volume rm $(docker volume ls -qf dangling=true)
  docker volume rm $(docker volume ls -q --filter dangling=true)
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

  nest new <project-name>
  nest generate module <module-name>
  nest generate service <service-name>
  nest generate controller <controller-name>
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

  > CLI:
  ```
  python3 <file-name>
  python -V
  python3 -V

  python3 -m venv venv
  source ./venv/bin/activate
  deactivate

  pip list
  pip freeze
  pip freeze > requirements.txt
  pip install <dependency-name>
  pip install -r requirements.txt
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

  Variáveis:
  - foo = 'Lorem ipsum'
  - foo = 10
  - foo = 10.8976
  - foo = True

  IO/Cast:
  - foo = input('input: ')
  - foo = str(input('input: '))
  - foo = int(input('input: '))
  - foo = float(input('input: '))
  - foo = bool(input('input: '))

  - print('foo')
  - print('foo', 5)
  - print('foo' + 'bar')
  - print('foo:{0} bar:{:20}! \n xpto:{:>10} foobar:{:-^10} {:.3f}'.format(foo, bar, xpto, foobar, foo))
  - print(f'foo:{foo} bar:{bar:20}')
  - print('='*5, end='')
  - print(type(foo))
  - print(id(10))

  String methods:
  - len(foo)

  - foo.capitalize()
  - foo.title()
  - foo.lower()
  - foo.upper()
  - foo.swapcase()
  - foo.split()
  - '-'.join(foo)
  - foo.replace('foo', 'bar')

  - foo.count('o')
  - foo.count('o', 0, 1)
  - foo.startswith('f')
  - foo.endswith('o')
  - foo.find('o')
  - 'foo' in foo
  
  - foo.isalnum()
  - foo.isalpha()
  - foo.islower()
  - foo.isupper()
  - foo.isnumeric()

  -  foo.ljust(10)
  - foo.rjust(10)
  - foo.center(10)
  - foo.lstrip()
  - foo.rstrip()
  - foo.strip()

  - print(foo[2])
  - print(foo[1:])
  - print(foo[:3])
  - print(foo[1:3])
  - print(foo[1:9:2])
  - print(foo[1::2])
  - print(foo[:9:2])
  - print(foo[:])

  Operadores aritméticos
  - xpto = foo + bar
  - xpto = foo - bar
  - xpto = foo * bar
  - xpto = foo / bar
  - xpto = foo // bar
  - xpto = foo ** bar = pow(foo,bar)
  - xpto = foo % bar

  Operadores relacionais/comparativos:
  - print(foo == bar)
  - print(foo != bar)
  - print(foo > bar)
  - print(foo >= bar)
  - print(foo < bar)
  - print(foo <= bar)

  Operadores lógicos:
  - print(not foo)
  - print(foo and bar)
  - print(foo or bar)

  Estruturas condicionais
  if not foo:
    print('foo')
  elif not bar and not bar:
    print(bar)
  else:
    print('bar')
  
  print('foo' if not foo else 'bar')
  if 'hello' in 'hello world':
    print('hello')

  Estruturas de repetição:
  i = 0
  while i < 5:
    print(i)
    i += 2
  
  while True:
    foo = int(input('Informe um número: '))
    if foo == 999:
      break
    print(f'{foo:.2f}')

  for i in range(5, 0, -2):
    print(i)

  for i in foo:
    print(i)

  Tuplas:
  foo = 'foo', 'bar', 'foobar'
  foo = (1, 2, 3, 4, 'foo', 'bar')
  bar = (6, 5)
  
  print(foo[0])
  print(foo[0:1])
  print(foo[:-1])
  print(foo[-2])
  
  print(len(foo))
  print(sorted(bar))
  print(foo+bar)
  print(bar.count(6))
  print(bar.index(5, 0))
  
  for i in foo:
    print(f'value: {i}')
  for i in range(0, len(foo)):
    print(f'item: {i} value: {foo[i]}')
  for i, v in enumerate(foo):
    print(f'item: {i} value: {v}')

  del(foo)

  T = (10,20,30,40,50)
  a,b,c,d,e = T
  print("a=",a,"b=",b)

  Listas:
  foo = ['foo', 'bar', 'foobar']
  bar = list(range(3, 10))
  barfoo = list()
  foobar = bar[:]
  barfoo = foo + bar
  barfoo = foo * 2
  barfoo = list(range(2,11,3))
  
  foo.append(4)
  foo.insert(2, 0)
  barfoo.append(foo[:])
  bar.extend(barfoo)
  foobar.append(50)
  foobar.clear()
  foo.pop(2)
  foo.remove('foo')
  bar.sort(reverse=True)
  bar.reverse()
  del foo[2]
  
  print(foo)
  print(barfoo[0][0])
  print(barfoo[0][0:2:1])
  print(len(foo))
  print(min(foo))
  print(max(foo))
  print(max(foo))
  print(sorted(foo))
  print('foo' if 3 in bar else 'bar')
  
  for i in foo:
    print(f'value: {i}')
  for i, v in enumerate(foo):
    print(f'item: {i} value: {v}', end='-->')

  T = [10,20,30,40,50]
  a,b,c,d,e = T
  print("a=",a,"b=",b)

  Dicionários:
  foo = dict()
  bar = dict({"id": 1, **foo})
  foo = { 'key': 'key', 'value': 'value' }
  foo['foo'] = 'foo'
  bar = foo.copy()
  foobar = json.dumps(json)
  json = json.loads(foobar)
  
  del foo['foo']
  
  print(foo)
  print(bar)
  print('key' in foo)
  print(foo['key'])
  print(foo.keys())
  print(foo.values())
  print(foo.items())

  for i in foo.keys():
    print(f'item: {i} value: {foo[i]}')
  for v in foo.values():
    print(f'value: {v}')
  for i, v in foo.items():
    print(f'item: {i} value: {v}', end=' --> ')

  Conjuntos:
  foo = variable = {"Name", "Lastname", 10}
  bar = set(["Name", "Lastname", 10])

  foo.add(20)
  foo.union(bar) ou foo | bar
  foo.intersection(bar) ou foo & bar
  foo..difference(bar) ou foo - bar

  Funções:
  def hello_world(params, other_params=None):
    print(params)
    print(other_params)
    return f"{params} {other_params}"
  hello_world("My name is", other_params="Is my name")

  def unPackage(*data):
    for i in data:
    print(i)

  def sum(a = 0, b = 0, *c):
    global x
    x = 10
    s = a + b
    if len(c) > 0:
      for i in c:
        s += i
    return s
  print(sum(a=0, b=2))
  print(x)

  def function_blank():
    ...
  def function_pass():
    pass

  Bibliotecas:
  from math import sqrt, floor
  from random import randint, random
  from utils import numbers
  import emoji

  print('{:.2f}'.format(floor(sqrt(9))))
  print('{:.2f} - {:.2f}'.format(random(), randint(1, 10)))
  print(f'{numbers.fat(5)}')
  print(emoji.emojize('hello world :sunglasses:'))

  Classes:
  class ClassHelloWorld:
    def __init__(self, params): # constructor
      self.params = params
  
    def new_params(self, new_params): # comportamento
      self.params = new_params
  
    def instance_method(self): # Obrigatório ter um obj (instância)
      return ("Método de instância", self)
  
    @classmethod
    def class_method(cls): # Não obrigatório
      return ("Método de classe, cls)
  
    @staticmethod
    def static_method(): # Não obrigatório
      return ("Método estático")
  
  hello_world = ClassHelloWorld("My name is")
  hello_world.new_params("Is my name")
  print(hello_world.params)
  print(hello_world.instance_method())
  print(ClassHelloWorld.class_method())
  print(ClassHelloWorld.static_method())
  
  class ClassBlank:
    ...
  
  class ClassPass:
    pass
  ```

</details>

<details>

  <summary> :scroll: Flask</summary>

  ```
  flask run
  FLASK_APP=main.py FLASK_ENV=development flask run --port 8000
  ```

</details>

<details>

  <summary> :scroll: Django</summary>

  > Overview:
  ```
  Aplicação deve ser conter as urls do endpoint, e seus templates ser importados na raíz `<settings.py -> INSTALLED_APPS>`. O acesso admin da aplicação é em `http://localhost:3000/admin` e para cada modelo a ser manipulado pelo superadmin deve ser exposto na page admin do próprio app.

Primeiro passo é criar o ambiente de desenvolvimento: `python3 -m venv venv` e ativá-lo para instalar dependêncies e rodar o projeto: `source ./venv/bin/activate`.
Para instalação individual de dependências pode ser feito por: `pip install Django==4.2.4` ou para instalar a partir de um gerenciador por: `pip install -r requirements/dev.txt`

Com a instalação do Django é realizado a criação do projeto: `django-admin startproject <project-name> .`, para testar seu êxito rode o servidor: `python manage.py runserver`.
A criação de aplicação se dá a nível de entidades logo para cada aplicação deverá ser criada por: `django-admin startapp <app-name>`.

Assim é possível com a aplicação criada gerar seus `Models`, como exemplo:


from django.db import models


class Agendamento(models.Model):
  data_agendamento = models.DateTimeField()
  nome_cliente = models.CharField(max_length=255)
  email_cliente = models.EmailField()
  telefone_cliente = models.CharField(max_length=20)
  cancelado = models.BooleanField(default=False)


Após a criação do models é nencessário gerar suas migrations: `python manage.py makemigrations` e `python manage.py migrate`

As configurações do projeto é importante ser separada pelo escopo do ambiente em questão. Assim em `/api/settings` gere um `__init__.py` para modularizar o dir, e dentro especifique suas configurações `base`, `dev` e `prod`. Após as configurações definidas devem ser passadas para os arquivos de carregamento em: `/api/asgi.py`, `/api/wsgi.py` e `/manage.py`

    - Django Create: `django-admin startproject <project-name> .`
    - Django Create app: `django-admin startapp <app-name>`
    - Django Run: `python manage.py runserver`
    - Django Migrations: `python manage.py makemigrations`
    - Django Migrate: `python manage.py migrate`
    - Django DBShell: `python manage.py dbshell`
    - Django PyShell: `python manage.py shell`
    - Django Superuser: `python manage.py createsuperuser`
    - Django Test:
      `  python manage.py test
    pytest
    pytest --cov`
    - Django Settings: `DJANGO_SETTINGS_MODULE=api.settings.prod python manage.py runserver`
  ```

  > CLI:
  ```
  - DbShell Tables: `.tables`
  - DbShell Header: `.header ON`
  - DbShell Null: `.nullvalue NULL`

  - PyShell ORM Import: `from agenda.models import Categoria, Evento`
  - PyShell ORM Create: `Categoria.objects.create(nome="BackEnd")`
  - PyShell ORM Save: `categoria.save()`
  - PyShell ORM All: `Categoria.objects.all()`
  - PyShell ORM Filter: `Categoria.objects.filter(nome="BackEnd")`
  - PyShell ORM Object: `Categoria.objects.filter(nome="BackEnd")[0]`
  - PyShell ORM ForeignKey: `Evento(nome="Nome", categoria=Categoria.objects.filter(nome="BackEnd")[0])`
  - PyShell ORM Filter ForeignKey: `Evento.objects.filter(categoria__nome="BackEnd")`
  - PyShell ORM Filter Date: `Evento.objects.filter(data__gte=date.today())`
  - PyShell ORM Filter Unique: `Evento.objects.get(id=id)`
  ```

</details>

> :copyright: [Higor Eduardo Docs](https://github.com/higoreduardodocs)
