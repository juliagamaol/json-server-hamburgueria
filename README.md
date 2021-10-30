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