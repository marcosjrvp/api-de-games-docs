# API de games
Está API é utilizada para 
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de respota:
```[
    {
        "id": 23,
        "title": "Call of Duty Mw",
        "year": 2019,
        "price": 60
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta : 

```
{
    "err": "Token inválido"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
email : Email do usuário cadastrado no sistema

password: Senha do usuário cadastrado no sistema, com aquele determinado email

Exemplo:

```
{
   "email": "victorlimadev@gmail.com",
   "password": "nodejs<3"
    
}
```
#### Respostas
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Email ou senhas incorretos.

Exemplo de resposta:

```
{ err: "Credenciais inválidas!" }

```


##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de respota:

```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JsaW1hZGV2QGdtYWlsLmNvbSIsImlhdCI6MTY3OTY5ODQ0MSwiZXhwIjoxNjc5ODcxMjQxfQ.0n4HpSQQsGG3hCi9LvpBg-gXzDB5lKoP7yED7Q-pXw0"
}
```
