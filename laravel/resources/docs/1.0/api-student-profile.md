# Editar perfil

---

- [Visualizar informações do cadastro](#section-show-profile)
- [Alterar informações do cadastro](#section-edit-profile)
- [Alterar e-mail](#section-edit-email)

<a name="section-show-profile"></a>

### Visualizar informações do cadastro

### Requisição

| Method | Url                                                                  |
|--------|----------------------------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/user/showUserProfile |

Retorna as informações do usuário

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| nick_name  | Como gostaria de ser chamado?                   | integer |
| phone      | Telefone do aluno                               | integer |
| birthday   | Data de nascimento, formato dd/mm/YYYY          | date    |
| gender     | Pontos distribuídos                             | integer |

###### Sucesso

Status 402 Acceppted

```json 
{
    "data": {
	    "nick_name": "Márcio Dias",
	    "phone": "3732128406",
	    "birthday": "13/09/1985",
	    "gender": 1,
    },
}
```

---

<a name="section-edit-profile"></a>

### Alterar informações do cadastro

### Requisição

| Method | Url                                                                     |
|--------|-------------------------------------------------------------------------|
| POST    | https://api.marciodias.me/api/v1/school/student/user/updateUserProfile |


### Parâmetros

| Parâmetro | Tipo                                            |
|-----------|-------------------------------------------------|
| nick_name | string |
| phone     | string |
| birthday  | string |
| gender    | string |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| nick_name  | Como gostaria de ser chamado?                   | integer |
| phone      | Telefone do aluno                               | integer |
| birthday   | Data de nascimento, formato dd/mm/YYYY          | date    |
| gender     | Pontos distribuídos                             | integer |

###### Sucesso

Status 402 Acceppted

```json 
{
    "data": {
	    "nick_name": "Márcio Dias",
	    "phone": "3732128406",
	    "birthday": "13/09/1985",
	    "gender": 1,
    },
}
```

---

<a name="section-edit-email"></a>

### Alterar e-mail

### Requisição

| Method | Url                                                                  |
|--------|----------------------------------------------------------------------|
| PUT    | https://api.marciodias.me/api/v1/school/student/user/email           |

### Parâmetros

| Parâmetro | Tipo                                            |
|-----------|-------------------------------------------------|
| email     | string                                          |