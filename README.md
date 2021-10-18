# Setup Docker Para Projetos Laravel 8


### Passo a passo
Clone Repositório
```sh
git clone https://github.com/carloshsanto/Setup-Docker-Laravel8.git
```


Instalar do Laravel via git bast
```sh
 composer create-project laravel/laravel example-project
```


Copie os arquivos docker-compose.yml, Dockerfile e o diretório docker/ para o seu projeto
```sh
cp -r setup-docker-laravel/* example-project/
```


remover versionamento .git
```sh
$ rm -rf .git
```


Crie o Arquivo .env
```sh
cd example-project/
cp .env.example .env
```


Atualizar as variáveis de ambiente do arquivo .env
```dosini
APP_NAME=lcs-app
APP_URL=http://localhost:8989

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3388
DB_DATABASE=nome_que_desejar_db
DB_USERNAME=root
DB_PASSWORD=root

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```


Suba os containers do projeto
```sh
docker-compose up -d
```


Acessar o container
```sh
docker-compose exec lcs-app bash
```


Instalar as dependências do projeto
```sh
composer install
```


Gerar a key do projeto Laravel
```sh
php artisan key:generate
```


Acessar o projeto
[http://localhost:8989](http://localhost:8989)
