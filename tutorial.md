# Configurar Projeto rails para usar o postgres 

```
gem install pg 
```

 Vc pode iniciar o projeto configurado com o postgres ou configurar depois 

 para iniciar vc deve usar o seguinte comando abaixo:

```
$ rails new myapp -d postgresql
```
mas caso o projeto ja exista deve-se configurar o GEMFILE e o config/database.yml

no GEMFILE deve ser adicionado a gem para fazer interface com o postgree adicionando a linha:

```
gem 'pg'	
```
e apos isso rodar este comando pra instalar as dependencias do projeto:

```
$ bundle install
```

no arquivo de config do banco deve ser mudado o adpter a adicionado o campo de usuário e senha do banco:
``` 
development:
  adapter: postgresql
  host: localhost
  pool: 5
  timeout: 5000
  database: myapp_development
  username: tutorial
  password: tutorial 
```

para garantir que seja possivel se conectar ao banco o usuario tutorial deve existir usando o comando:
```
$ sudo -u postgres createuser -s tutorial
```

para adicionar a senha ao usuário acesse o console do postgres:
```
$ sudo -u postgres psql
```
e então use este comando para trocar a senha:
```
\password pguser
```
após isso  para criar a coneção e criar o banco de dados use o seguinte comando:

```
$ rake db:create
```

após isso tes