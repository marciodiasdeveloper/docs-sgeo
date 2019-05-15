# Módulo Gestão Escolar - Estudante

---

- [Autenticação](#section-autenticacao)
- [Dashboard](#section-dashboard)
- [Notas](#section-notas)
- [Diário](#section-diario)
- [Ocorrências](#section-ocorrencias)
- [Avisos e comunicados](#section-avisosecomunicados)
- [Meu perfil](#section-meuperfil)

<a name="section-autenticacao"></a>
## Autenticação
- [Login](#section-autenticacao-login)
- [Esqueci minha senha](#section-autenticacao-forgetpassword)

## Dados de acesso ao sandbox (Aluno)
- Login: aluno@sgeo.com.br
- Senha: 12345

<a name="section-autenticacao-login"></a>
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

<a name="section-autenticacao-forgetpassword"></a>
### Esqueci minha senha

Envie os parâmetros via POST para solicitar uma nova senha.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| get   | https://api.marciodias.me/api/v1/school/student/authentication |

---

<a name="section-dashboard"></a>
## Dashboard
### Carregar informações da matrícula

Informações da matrícula do aluno, período, curso, turma, disciplinas em que o aluno encontra-se matriculado.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/dashboard/enrollment |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| id         | Identificador da matrícula do aluno             | integer |
| date_start | Data início matrícula                           | 99/99/9999 |
| date_start | Data fim matrícula                              | 99/99/9999 |
| class_order | Número de registro na chamada da turma         | integer |
| actived    | Status da matrícula                             | cursando |
| courses    | Cursos que o aluno está cursando                | array |
| courses['id']    | Identificador curso                       | integer |
| courses['name']    | Nome do curso                           | string |
| courses['classes']    | Turmas que o aluno está cursando     | array |
| courses['classes']['id']    | Identificador turma            | integer |
| courses['classes']['name']    | Nome da turma                | string |
| courses['classes']['disciplines']    | Disciplinas que o aluno está cursando | array |
| courses['classes']['disciplines']['id']    | Identificador disciplina        | integer |
| courses['classes']['disciplines']['name']    | Nome da disciplina            | string |

###### Sucesso

Status 402 Acceppted

```json 
{
    "id": 1,
    "date_start": "13/01/2019",
    "date_end": "24/12/2019",
    "class_order": 7,
    "actived": 1,
    "courses": {
        "id": 151,
        "name": "Ensino médio",
        "classes": {
            "id": 233,
            "name": "2º Ano Laranja",
            "disciplines": [
                {
                    "id": 255,
                    "name": "Matemática",                
                },
                {
                    "id": 256,
                    "name": "Geografia",                
                },  
                {
                    "id": 257,
                    "name": "Português",                
                },          
                {
                    "id": 258,
                    "name": "História",                
                }
            ]
        }
    }
}
```

---

#### Erros

- Status 401 - student_without_access (Aluno não encontrado)
- Status 401 - student_without_enrollments (Aluno sem matrícula)

--

### Últimos lançamentos

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/dashboard/bulletins |

Retorna as últimas notas lançadas para o aluno por ordem de data decrescente

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| id         | Identificador do lançamento                     | integer |
| discipline | Nome da disciplina                              | string  |
| points     | Pontuação do aluno                              | decimal |
| points_distributed | Pontos distribuídos                     | decimal |
| type_of_note | Tipo de nota (Prova, Tarefa, etc...)          | string  |
| teacher    | Nome do professor                               | string  |
| average    | Informa se a nota está dentro da média          | bollean  |
| created_at | Data e hora do lançamento                       | timestamp |

###### Sucesso

Status 402 Acceppted

--



<a name="section-notas"></a>
## Disciplinas
### Listar notas



Lista todas as notas do aluno por ordem decrescente de lançamento.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/disciplines |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato |
|----------- |-------------------------------------------------| ------- |
| id         | Identificador do lançamento                     | integer |
| token      | Nome da disciplina                              | string  |
| name       | Pontuação do aluno                              | decimal |
| points_total | Pontos distribuídos                     | decimal |

###### Sucesso

Status 402 Acceppted

```json 
{
    
}
```

---

<a name="section-diario"></a>
## Diário

---

<a name="section-ocorrencias"></a>
## Ocorrências
### Listar ocorrências

Lista todas as ocorrências do aluno por ordem decrescente de lançamento.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/occurrences |


### Retorno

###### Sucesso

Status 402 Acceppted

```json 
{
    
}
```

---

<a name="section-avisosecomunicados"></a>
## Avisos e comunicados
### Listar avisos e comunicados

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/noticeboard |

### Retorno

###### Sucesso

Status 402 Acceppted

```json 
{
    
}
```


---

<a name="section-meuperfil"></a>
## Meu perfil
### Listar informações do perfil

Carregue as informações principais do perfil.

---

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/school/student/profile |

### Retorno

###### Sucesso

Status 402 Acceppted

```json 
{
    
}
```

---
