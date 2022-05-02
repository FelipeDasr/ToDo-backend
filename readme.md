﻿# Todo back-end

<div align="center"></br>
  <img alt="Typescript badge" src="https://img.shields.io/badge/Typescript-00B1EA?style=for-the-badge&logo=typescript&logoColor=white" />
  <img alt="NodeJS badge" src="https://img.shields.io/badge/Node.js-90C53F?style=for-the-badge&logo=node.js&logoColor=white"/>
  <img alt="API badge" src="https://img.shields.io/badge/API%20REST-E64D80?style=for-the-badge" />
  <img alt="ExpressJS badge" src="https://img.shields.io/badge/Express.js-333331?style=for-the-badge" />
  <img alt="TypeORM badge" src="https://img.shields.io/badge/TYPEORM-FFAB00?style=for-the-badge" />
</div></br>

Aplicação feita em typescript, com o objetivo de demonstrar minhas habilidades com TS. Essa API REST é capaz de armazenar tarefas de cada usuário individualmente, fazendo possível agendar e visualizar objetivos diariamente, semanalmente e mensalmente. A aplicação é um CRUD em si, capaz de criar, consultar, alterar e deletar dados. Feita utilizando boas práticas e tecnologias muito usadas hoje em dia.

# Iniciando
    > npm start

Caso tudo ocorra com sucesso a saida deverá ser:

    [OK] API IS RUNNING AT http://back-end-host:3000

    [OK] CONNECTION TO DATABASE SUCCESSFUL

# SignUp

| Rota          | Método     |
|---------------|------------|
| **`/signup`** | **`POST`** |


**Parâmetros obrigatórios**

| Campo           | Tipo         | Local | Descrição                |
|-----------------|--------------|-------|--------------------------|
| **`firstname`** | **`string`** | body  | Primeiro nome do usuário |
| **`lastname`**  | **`string`** | body  | Ultimo nome do usuário   |
| **`email`**     | **`string`** | body  | Endereço de e-mail       |
| **`password`**  | **`string`** | body  | Senha da nova conta      |

**Exemplo de requisição**

```json
{
	"firstname": "Felipe",
	"lastname": "Dasr",
	"email": "felipedasr@email.com",
	"password": "strongpassword"
}
```

**Resposta de sucesso**

**Código**: **`201 CREATED`**

```json
{
	"id": "4f2bdf94-6438-4495-a3fb-1b6f2adba0df",
	"firstname": "Felipe",
	"lastname": "Dasr",
	"email": "felipedasr@email.com",
	"createdAt": "2022-04-28T23:48:14.491Z",
	"updatedAt": "2022-04-28T23:48:14.491Z"
}
```

Logo depois do usuário ser criado, um e-mail de boas vindas será enviado a ele.

### E-mail de boas vindas:
![welcome_message](docs/images/welcomeMessage.PNG)

# SignIn

| Rota          | Método     |
|---------------|------------|
| **`/signin`** | **`POST`** |


**Parâmetros obrigatórios**

| Campo          | Tipo         | Local | Descrição         |
|----------------|--------------|-------|-------------------|
| **`email`**    | **`string`** | body  | E-mail do usuário |
| **`password`** | **`string`** | body  | Senha do usuário  |

**Exemplo de requisição**

```json
{
	"email": "felipedasr@gmail.com",
	"password": "strongpassword"
}
```

**Resposta de sucesso**

**Código**: **`200 OK`**

```json
{
	"user": {
		"id": "4f2bdf94-6438-4495-a3fb-1b6f2adba0df",
		"firstname": "Felipe",
		"lastname": "Dasr",
		"email": "felipedasr@email.com",
		"createdAt": "2022-04-28T23:48:14.491Z",
		"updatedAt": "2022-04-28T23:48:14.491Z"
	},
	"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjRmMmJkZjk0LTY0MzgtNDQ5NS1hM2ZiLTFiNmYyYWRiYTBkZiIsImlhdCI6MTY1MTUzNDA3MiwiZXhwIjoxNjUxNjIwNDcyfQ.XNn3VK3M2iEQsRtgwSNLt4q8GE9EKtrXnNtYkKfj5Sw",
	"refreshToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjRmMmJkZjk0LTY0MzgtNDQ5NS1hM2ZiLTFiNmYyYWRiYTBkZiIsImlhdCI6MTY1MTUzNDA3MiwiZXhwIjoxNjU0MTI2MDcyfQ.3R_OljyA4xgvnh0Dybk1x6mAYqvpyGCtW_9sXgLZSLg"
}
```
