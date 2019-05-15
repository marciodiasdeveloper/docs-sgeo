# Disciplina

---

- [Informações da disciplina](#section-discipline)
- [Notas do aluno na disciplina](#section-results)

<a name="section-discipline"></a>
### Informações da disciplina

Lista as informações do aluno dentro da disciplina selecionada.

### Requisição

O Parâmetro {token} é o registro da matrícula do aluno dentro da disciplina, este token é fornecido dentro da rota de Disciplinas em que o aluno está cursando, documentação em [Disciplinas](/docs/api/1.0/api-school-student-disciplines).

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET   | https://api.marciodias.me/api/v1/school/student/discipline/{token} |

### Retorno

###### Parâmetros retorno

| Parâmetro  | Descrição                                       | Formato    |
|----------- |-------------------------------------------------| ---------- |
| id         | Identificador da matrícula/disciplina do aluno  | (int)      |
| token      | Token da matrícula/disciplina do aluno          | (int)      |
| name       | Nome da disciplina                              | (string)   |
| points_total | Pontos do aluno na disciplina                 | (int)      |
| status | Status referente ao total de pontos                 | (string)   |
| actived | Status referente ao total de pontos                | (integer)  |
| results  | Professores                                       | (integer)  |
| updated_at | Data e hora última atualização do aluno         | (timestamp)|
| created_at | Data e hora da matrícula do aluno na disciplina | (timestamp)   |


---

<a name="section-results"></a>
### Notas do aluno na disciplina

Lista as notas do aluno na disciplina, por ordem de lançamento decrescente

### Requisição

O Parâmetro {token} é o registro da matrícula do aluno dentro da disciplina, este token é fornecido dentro da rota de Disciplinas em que o aluno está cursando, documentação em [Disciplinas](/docs/api/1.0/api-school-student-disciplines).

| Method | Url                                                                                     |
|--------|-----------------------------------------------------------------------------------------|
| GET   | https://api.marciodias.me/api/v1/school/student/discipline/{token}/bulletins?page={page} |

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

---
