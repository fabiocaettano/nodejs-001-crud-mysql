# Crud com Nodejs e Mysql

[NODE](#node)

[CURL](#curl)


## Node

Criar o package.json :

```
npm init -y
```

Alterar a chave main e incluir a chave scripts > start.
Na chave main alterar para server.js.
E incluir o comando nodemon server.js na chave scripts > start:

``` json
{
  "name": "crud-mysql-01",
  "version": "1.0.0",
  "description": "",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "nodemon server.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

Criar a imagem e subeir o container:

``` 
docker-compose up -d --build
```

Listar o containers:
```
docker container ls
```

Checar mensagens de logs:

```
docker logs idContainer
```


Se necessário excluir os containers:

```
docker-compose down
```


## CURL

Acessar o container do node:

```
docker exec -it idContainer /bin/bash
```

Testar os endpoints:

``` cli
curl -X "GET" http://localhost:8080/
```

``` cli
curl -X "POST" http://localhost:8080/crud/companies -H "Content-Type: application/json"  -d '{"title": "title 6","type":"type 6","position":"6"}'
```

``` cli
curl -X "GET" http://localhost:8080/crud/companies
```

``` cli
curl -X "GET" http://localhost:8080/crud/companies/6
```

``` cli
curl -X "DELETE" http://localhost:8080/crud/companies
```

``` cli
curl -X "DELETE" http://localhost:8080/crud/companies/4
```

``` cli
curl -X "PUT" http://localhost:8080/crud/companies/5 -H "Content-Type: application/json"  -d '{"title": "title 5","type":"type 5","position":"5"}'
```

## Referências:

[Node.js + MySQL CRUD Automation API](https://medium.com/@bharatrawat986/node-js-mysql-crud-automation-api-78b3f69de839)

[CURL 1](https://phoenixnap.com/kb/curl-command)

[CURL 2](https://reqbin.com/curl)