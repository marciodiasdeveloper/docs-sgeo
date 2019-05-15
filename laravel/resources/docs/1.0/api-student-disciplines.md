# Disciplinas

---

- [Listar disciplinas](#section-disciplines)

<a name="section-login"></a>
### Listar disciplinas

Lista as disciplinas inclusas na matrícula do aluno.

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET   | https://api.marciodias.me/api/v1/school/student/disciplines |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato    |
|----------- |-------------------------------------------------| ---------- |
| id         | Identificador da matrícula/disciplina do aluno  | (int)      |
| token      | Token da matrícula/disciplina do aluno          | (int)      |
| name       | Nome da disciplina                              | (string)   |
| points_total | Pontos do aluno na disciplina                 | (int)      |
| status | Status referente ao total de pontos                 | (string)   |
| teachers | Professores                                       | (array)    |
| teachers['name'] | Nome do professor                         | (string)   |

###### Sucesso

Status 402 Acceppted

```json 
[
	{
	    "id": 25,
	    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9",
	    "name": "Português",
	    "points_total": 62,
	    "status": Aprovado,
	    "teachers": {
	    	"name": 'Francisco Dias',
	    }
	},
	{
	    "id": 26,
	    "token": "eyJzdWIiOjIsImlzcyI6Imh0dHB",
	    "name": "Matemática",
	    "points_total": 74,
	    "status": Aprovado,
	    "teachers": {
	    	"name": 'José Roberto Silva',
	    }
	},
]
```

---