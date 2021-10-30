<h1>Hamburgueria 2.0 - API</h1>

<p align = "center">Backend da aplicação da Hamburgueria 2.0 com typescript, com finalidade em poder se cadastrar e comprar seus lanches</p>

<p align="center">
  <a href="#endpoints">Endpoints</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

## **Endpoints**
A API tem 3 endpoints - podendo fazer login,cadastro e adicionar os lanches no carrinho.<br>
JSON para usar no insomia =>
URL base da API =>

Para importar o JSON no Insomnia

## Rotas que não precisam de autenticação

<h2 align="center">Criação de usuário</h2>

`POST/register - FORMATO DA REQUISIÇÃO`
```json
{
    "name":"kenzinho ferreira",
    "email":"kenzinho23@gmail.com",
    "password":"123456789"
}
```
Caso dê tudo certo, a resposta será assim:

`POST/register - FORMATO DA RESPOSTA - STATUS 201`
```json 

{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvMjNAZ21haWwuY29tIiwiaWF0IjoxNjM1NjEwMjIyLCJleHAiOjE2MzU2MTM4MjIsInN1YiI6IjIifQ.0YzL5HkEmPm-5Qf4lq7C0OsmKO1zbfsUQr1PBgWH3Jk",
  "user": {
    "email": "kenzinho23@gmail.com",
    "name": "kenzinho ferreira",
    "id": 2
  }
}

```
<h2 align="center">Possíveis erros</h2>
``` 
Email já cadastrado:
`POST/register - `
`` FORMATO DA RESPOSTA - STATUS 400``
```json 

"Email already exists"

```
<h2 align = "center">Login</h2>

`POST /login - FORMATO DA REQUISIÇÃO`
```json
{
  "email":"kenzinho23@gmail.com",
  "password":"123456789"
}
```
Caso dê tudo certo, a resposta será assim:

`POST /register -  FORMATO DA RESPOSTA - STATUS 201`
```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvMjNAZ21haWwuY29tIiwiaWF0IjoxNjM1NjEwODIwLCJleHAiOjE2MzU2MTQ0MjAsInN1YiI6IjIifQ.28cMb2lizv5ZQMHso4WBKuncYvRy1evc_fAnWatFe_0",
  "user": {
    "email": "kenzinho23@gmail.com",
    "name": "kenzinho ferreira",
    "id": 2
  }
}
```
Com essa resposta, vemos que temos duas informações, o user e o token respectivo, dessa forma você pode guardar o token e o usuário logado no localStorage para fazer a gestão do usuário no seu frontend.

<h2 align = "center">Adicionar ao carrinho</h2>

`POST /cart -  FORMATO DA RESPOSTA - STATUS 200`
```json
[
  {
    "title": "Hamburguer",
    "type": "Sanduíches",
    "price": "14",
    "image": "https://i.ibb.co/DfdVC0F/202109090436-skn5yx754p-1.png",
    "userId": 3,
    "quantity": 4,
    "id": 2
  }
]

```
<h2 align = "center">Listando os hambúrgueres</h2>

`GET /cart -  FORMATO DA RESPOSTA - STATUS 200`
```json
[
  {
    "title": "Hamburguer",
    "type": "Sanduíches",
    "price": "14",
    "image": "https://i.ibb.co/DfdVC0F/202109090436-skn5yx754p-1.png",
    "userId": 3,
    "quantity": 4,
    "id": 2
  }
]

```
## Rotas que necessitam de autorização

Rotas que necessitam de autorização deve ser informado no cabeçalho da requisição no campo "Auth":

=> Auth: Bearer {token}

Após o login, o usuário consegue ler suas informações

<h2 align = "center">Listando as informações do usuário</h2>

Nessa aplicação o usuário precisa fazer login ou se cadastrar para ver suas informações.

FORMA DE ACESSO:
`GET /users/:id -  FORMATO DA RESPOSTA - STATUS 200`
```json
[
  {
    "email": "kenzinho23@gmail.com",
    "password": "$2a$10$T0uBxwNrVvKwa3oHgP6HYemFRdzvAk9Bl5kLYzNwZLxtQtvYRzxZe",
    "name": "kenzinho ferreira",
    "id": 2
  }
]
```

---
By julia-gama :wave: