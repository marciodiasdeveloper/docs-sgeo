# Api modo público

---

- [Bancos](#section-1)
- [Países](#section-1)
- [Estados](#section-1)
- [Cidades](#section-1)
- [Níveis educationais](#section-1)
- [Sexo](#section-1)
- [Como conheceu](#section-1)
- [Profissões](#section-1)
- [Cep](#section-1)
- [Salário mínimo](#section-1)
- [Zona de horários](#section-1)
- [Idiomas](#section-1)

<a name="section-1"></a>
## Bancos
### Listar bancos

Listagem dos bancos cadastrados

### Requisição

| Method | Url                                             |
|--------|-------------------------------------------------|
| GET    | https://api.marciodias.me/api/v1/official/banks |

---

<a name="section-1"></a>
## Países

### Requisições

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/countries | Listar países |
| GET    | https://api.marciodias.me/api/v1/official/countries/default | País padrão |
| GET    | https://api.marciodias.me/api/v1/official/countries/{country_id} | Estados do país |

---

<a name="section-1"></a>
## Estados

### Requisições

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/states | Listar estados |

---

<a name="section-1"></a>
## Cidades

### Requisições

| Method | Url                                             | Parâmetro | Descrição |
|--------|-------------------------------------------------| --------- | --------- |
| GET    | https://api.marciodias.me/api/v1/official/states/{state_id} | {state_id} | Listar cidades de um estado |

---

<a name="section-1"></a>
## Níveis educacionais

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/educations | Listar níveis |

-- 

<a name="section-1"></a>
## Sexo

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/genders | Listar níveis |

-- 

<a name="section-1"></a>
## Como conheceu

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/origins | Como conheceu |

-- 

<a name="section-1"></a>
## Profissões

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/professions | Listar profissões |

-- 

<a name="section-1"></a>
## Cep

### Requisição

| Method | Url                                             | Descrição | Formato |
|--------|-------------------------------------------------| --------- | ------- |
| GET    | https://api.marciodias.me/api/v1/official/zipcodes/{zipcode}  | Retorna informações referente ao cep | 99999-999 e 999999999 |

-- 

<a name="section-1"></a>
## Salário mínimo

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/minimum_wages  | Histórico de alterações e valores do salário mínimo |

-- 

<a name="section-1"></a>
## Zona de Horários 

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/timezones  | Zona de Horários para o usuário |

-- 

<a name="section-1"></a>
## Idiomas

### Requisição

| Method | Url                                             | Descrição |
|--------|-------------------------------------------------| --------- |
| GET    | https://api.marciodias.me/api/v1/official/languages | Listar idiomas |

-- 