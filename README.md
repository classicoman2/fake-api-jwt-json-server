# JSONServer + JWT Auth
A Fake Rest API using registration, authentification and authorization, taking advantage of [jsonwebtoken package](https://www.npmjs.com/package/jsonwebtoken). [Forked from here](https://github.com/techiediaries/fake-api-jwt-json-server).

## Table of contents

<!-- toc -->

- [Intro](#intro)
- [TODO - CHANGES](#todo---changes)
- [Install](#install)
- [Run](#run)
- [How to register?](#how-to-register)
- [How to Login?](#how-to-login)
- [How to use API?](#how-to-use-api)
- [Webgraphy](#webgraphy)

<!-- tocstop -->

## Intro

A Fake REST API using json-server with JWT authentication. 
Implemented End-points: 
- register
- login
- use API only with Authentication token

## TODO - CHANGES
- [x] Login is checking if the user exists and returns Authentication token
- [ ] README updated

## Install
```bash
$ npm i
```

Might need to run
```bash
$ npm audit fix
```

## Run 

```bash
$ npm run dev
```

## How to Register?
You can register by sending a POST request to
```
POST http://localhost:3001/auth/register
```

with the following data in body (basic example)
```
{
  "email": "pepe@email.com",
  "password":"1234567"
}
```

- You should receive an access token with the following format 
```json
{
   "access_token": "<ACCESS_TOKEN>"
}
```

## How to Login?
You can login by sending a GET request to
```
http://localhost:3001/auth/login
```

- Use `Basic Auth` to send username and password in the headers. You should receive an access token with the following format:
```json
{
   "access_token": "<ACCESS_TOKEN>"
}
```

## How to access the data of the API (characters resource)?

Els _characters_ estan disponibles a la url:
```
http://localhost:3001/characters
```

Però necessitam el _Token_ (Bearer) generat amb el Registre o el Login per poder recuperar la informació

```
Authorization: Bearer <ACCESS_TOKEN>
```

En cas contrari, es produirà un error.


## Webgraphy
Check out these tutorials:
- [Mocking a REST API Back-End for Your Angular App with JSON-Server and Faker.js](https://www.techiediaries.com/angular-mock-backend)
- [Building a Fake and JWT Protected REST API with json-server](https://www.techiediaries.com/fake-api-jwt-json-server)
- [Angular 9 Tutorial: Build an Example App with Angular CLI, Angular Router, HttpClient & Angular Material](https://www.shabang.dev/angular-tutorial-build-an-example-app-with-angular-cli-router-httpclient-and-angular-material/)
- [jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken) npm package


