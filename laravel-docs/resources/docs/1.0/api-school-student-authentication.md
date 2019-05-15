# Autenticação

---

- [Login](#section-login)
- [Esqueci minha senha](#section-forgot)
- [Token refresh](#section-jwt-refresh)

<a name="section-login"></a>
### Login

Sistema de autenticação utilizando JWT (JSON Web Token), envie um post com os parâmetros necessários para receber o token de autenticação.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| POST   | https://api.marciodias.me/api/v1/school/student/authentication |

### Parâmetros

| Parâmetro | Tipo                                            |
|-----------|-------------------------------------------------|
| email     | string:email |
| password  | string |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| token      | Token de acesso para salvar e fazer requisições | JSON Web Token |

###### Sucesso

Status 402 Acceppted

```json 
{
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOjIsImlzcyI6Imh0dHB"
}
```

---

#### Erros

- Status 401 - invalid_credentials (Login ou senha inválido)
- Status 401 - token_expired (Seu token de acesso expirou)
- Status 401 - token_invalid (Token inválido)
- Statos 401 - token_absent
- Status 500 - could_not_create_token (Não foi possível criar o token)

---

<a name="section-forgot"></a>
### Esqueci minha senha

Envie os parâmetros via POST para solicitar uma nova senha.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| get   | https://api.marciodias.me/api/v1/school/student/authentication |

---

<a name="section-jwt-refresh"></a>
### Token refresh

Se a aplicação receber um objeto com valor data.error == 'token_expired' você deve enviar o token antigo e solicitar um novo token.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| post   | https://api.marciodias.me/api/v1/school/student/authentication/refresh |

### Parâmetro

| Parâmetro | Tipo                                            |
|-----------|-------------------------------------------------|
| token     | jwt-auth-token                                  |