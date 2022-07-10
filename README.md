# json-server-Food

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para plataforma kenzie shoop.
​

## Endpoints


A API tem endpoints desenvolvidas para aplicação configurados conforme abaixo:

url base da API é: https://kenzieshopapi.herokuapp.com/



### Cadastro do user

​
Para acessar a plataforma é necessário, fazer o cadastro do usuário.
​
POST /register
​
{
"email": "kenzinho@mail.com",
"password": "12345",
"name": "Kenzinho",
"lastName": "kenzado",
"tel": 914431544,
"isAdm": true
}
​
Caso dê tudo certo, a resposta será assim:
​
POST /register - FORMATO DA RESPOSTA - STATUS 201
​
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Inh4ZGFya2x1Y2FzeHhAaG90bWFpbC5jb20iLCJpYXQiOjE2NTc0NzYyNzIsImV4cCI6MTY1NzQ3OTg3Miwic3ViIjoiMiJ9.7P5mVf4UGp0wc4Pq5hKqr4qBn38cYv4pYTXWYzDzn5I",
"user": {
"email": "kenzinho@mail.com",
"name": "Kenzinho",
"lastName": "kenzado",
"tel": 914431544,
"isAdm": true,
"id": 2
}
}
​

### Login

​
POST /login - FORMATO DA REQUISIÇÃO
{
"email": "nome@email.com",
"password": "123456"
}
​
Caso dê tudo certo, a resposta será assim:
​
POST /login - FORMATO DA RESPOSTA - STATUS 200
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Inh4ZGFya2x1Y2FzeHhAaG90bWFpbC5jb20iLCJpYXQiOjE2NTc0NzYzNTMsImV4cCI6MTY1NzQ3OTk1Mywic3ViIjoiMiJ9.zErG2B768U3JKzE8HoaHOptFIsei-LNiPHhdetPNt28",
"user": {
"email": "kenzinho@mail.com",
"name": "Kenzinho",
"lastName": "kenzado",
"tel": 914431544,
"isAdm": true,
"id": 2
}
}
​

### lista de food

lista de food

Get /food
[
{
"name": "Quarteirão Duplo",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/03-21.png",
"description": "O Quarteirão Duplo possui 2 hambúrgueres de extrema qualidade com um pão con gergelim e salada.",
"price": 30,
"id": 1
},
{
"name": "X-Tudo",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/08/02-19.png",
"description": "O X-Tudo e o hambúrguer perfeito para matar sua fome, com produtos de excelente qualidades.",
"price": 28,
"id": 2
},
{
"name": "Combo com Tudo",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/02/18-2.png",
"description": "Combo com um copo de 600 de um refrigerante da sua escolha, uma batata media d e um Hambúrguer ganhe mais suculento e com 2 amburgues",
"price": 34,
"id": 3
},
{
"name": "X-Frango",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/08-8.png",
"description": "O X-frango e o hambúrguer perfeito para matar sua fome e com um hambúrguer de frango suculento, com produtos de excelente qualidades.",
"price": 32,
"id": 4
},
{
"name": "Prato Executivo",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/07/01-1.png",
"description": "Arroz, salada, palmito. ervilha, legumes no vapor com um frango grelhado de deixar agua na boca.",
"price": 19,
"id": 5
},
{
"name": "Porção de Batata Grande",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/08/05-4.png",
"description": "Porção de batata suculenta e sequinhas",
"price": 20,
"id": 6
}
]

Essas rotas necessitam de autorização deve ser informado no cabeçalho da requisição o campo "Authorization", dessa forma:
​
Authorization: Bearer {token}
​
POST/food
{
"name": "Quarteirão ",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/03-21.png",
"description": "O Quarteirão Duplo possui 2 hambúrgueres de extrema qualidade com um pão con gergelim e salada.",
"price": 30
}

​Caso dê tudo certo, a resposta será assim:

{
"name": "Quarteirão ",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/03-21.png",
"description": "O Quarteirão Duplo possui 2 hambúrgueres de extrema qualidade com um pão con gergelim e salada.",
"price": 30,
"id": 7
}

PATH/food/:id
{
"descricao": "Texto alterado"
}

​​Caso dê tudo certo, a resposta será assim:

{
"name": "Quarteirão ",
"img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/03-21.png",
"description": "O Quarteirão Duplo possui 2 hambúrgueres de extrema qualidade com um pão con gergelim e salada.",
"price": 5,
"id": 1
}

DELETE/food/:id
​
​
