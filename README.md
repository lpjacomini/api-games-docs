# Api de Games
Esta API é utilizada para consulta de games

## Endpoints
### GET /games
#### Esse endpoint é responsavel por retornar a listagem de todos os games cadastrados no banco de dados
##### Parametros
Nenhum
##### Respostas
###### OK! - 200
Caso esta resposta aconteça voce vai receber todos os games <br>
Exemplo de resposta
```
[
	{
		"id": 23,
		"title": "Call of duty MW",
		"year": "2019",
		"price": "75"
	},
	{
		"id": 65,
		"title": "Sea of Thieves",
		"year": 2018,
		"price": 40
	},
	{
		"id": 2,
		"title": "Minecraft",
		"year": 2012,
		"price": 20
	},
	{
		"id": 2323,
		"title": "Terraria",
		"price": "19",
		"year": "2010"
	}
]
```
###### Falha na autenticação! - 401
Caso essa resposta aconteça, isso significa que ocorreu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado. <br>

Exemplo de resposta: 

```
{
	"err": "Token inválido"
}
```

### POST /auth
#### Esse endpoint é responsavel por fazer o processo de login.
##### Parametros
email: E-mail do usuário cadastrado no sistema. <br>

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail. <br>

Exemplo: 
```
{
	"email": "lucasparizijacomini@gmail.com",
	"password": "1234"
}

```
##### Respostas
###### OK! - 200
Caso esta resposta aconteça voce vai receber o token de acesso <br>
Exemplo de resposta
```
{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJsdWNhc3Bhcml6aWphY29taW5pQGdtYWlsLmNvbSIsImlhdCI6MTY0NzcxMTkyMiwiZXhwIjoxNjQ3ODg0NzIyfQ.W5zKtlash62Rj2IRYXXcUKkkVU3q6OaqhsHG3eI_FiQ"
}
```

###### Falha na autenticação! - 401
Caso essa resposta aconteça, isso significa que ocorreu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou email inválido. <br>

Exemplo de resposta: 

```
{
	"err": "Credenciais inválidas"
}

```





