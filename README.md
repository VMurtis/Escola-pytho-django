# 📚 Sistema Escolar API (Django REST Framework)

API REST desenvolvida com Django REST Framework para gerenciamento de estudantes, cursos e matrículas.

O sistema permite criar, listar, atualizar e remover dados, além de consultar matrículas por estudante ou curso.

---
# 📚 Sistema Escolar API

## 🎥 Demonstração
https://youtu.be/0wsaIV2L46U


## 🚀 Funcionalidades

* CRUD completo de estudantes
* CRUD completo de cursos
* CRUD de matrículas
* Relacionamento entre estudantes e cursos
* Listagem de matrículas por estudante
* Listagem de matrículas por curso
* Painel administrativo com Django Admin
* API REST com Django REST Framework

---

## 🛠️ Tecnologias utilizadas

* Python
* Django
* Django REST Framework
* SQLite
* Django Admin
* Git & GitHub

---

## 📦 Modelos do sistema

### 👨‍🎓 Estudante

* nome
* email
* cpf
* data de nascimento
* celular

---

### 📘 Curso

* código
* descrição
* nível:

  * B → Básico
  * I → Intermediário
  * A → Avançado

---

### 🧾 Matrícula
* período:

  * M → Matutino
  * V → Vespertino
  * N → Noturno
* estudante (ForeignKey)
* curso (ForeignKey)

---

## 🔗 Endpoints da API

### 📌 Estudantes

* GET `/estudantes/`
* POST `/estudantes/`
* GET `/estudantes/{id}/`
* PUT `/estudantes/{id}/`
* DELETE `/estudantes/{id}/`

---

### 📌 Cursos

* GET `/cursos/`
* POST `/cursos/`
* GET `/cursos/{id}/`
* PUT `/cursos/{id}/`
* DELETE `/cursos/{id}/`

---

### 📌 Matrículas

* GET `/matriculas/`
* POST `/matriculas/`
* GET `/matriculas/{id}/`

---



## ▶️ Como executar o projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/VMurtis/Escola-pytho-django.git
```

---

### 2. Criar ambiente virtual

```bash
python -m venv venv
```

---

### 3. Ativar ambiente virtual (Windows)

```bash
venv\Scripts\activate
```

---

### 4. Instalar dependências

```bash
pip install -r requirements.txt
```

---

### 5. Aplicar migrações

```bash
python manage.py migrate
```

---

### 6. Criar superusuário

```bash
python manage.py createsuperuser
```

---

### 7. Rodar servidor

```bash
python manage.py runserver
```

---

## 📁 Estrutura do projeto

```
escola/
├── models.py
├── serializers.py
├── views.py
├── admin.py
├── urls.py
manage.py
```

---

## 🧪 Exemplo de requisição


### Criar estudante (POST)

Endpoint:

POST /estudantes/

```json
{ 
	"nome": "Ana Silva", 
	"email": "ana@email.com", 
	"cpf": "11111111111", 
	"data_nascimento": "2000-01-01", 
	"celular": "11999999999" 
}
```

```json
{ 
	"nome": "Jose Jones", 
	"email": "jose@email.com", 
	"cpf": "22222222222", 
	"data_nascimento": "1999-05-07", 
	"celular": "11988888888" 
}
```

```json
{ 
	"nome": "Rosa Nunes", 
	"email": "rosa@email.com", 
	"cpf": "33333333333", 
	"data_nascimento": "2000-10-01", 
	"celular": "11777777777" 
}
```

---

### Listar estudantes (GET)
Endpoint:

GET /estudantes/1

```json
{
  "id": 1,
  "nome": "Ana Silva",
  "email": "ana@email.com",
  "cpf": "11111111111",
  "data_nascimento": "2000-01-01",
  "celular": "11999999999"
}
```
---
📌 Listar estudantes (GET)

Endpoint:

GET /estudantes/

Response:
```json
[
  {
    "id": 1,
    "nome": "Ana Silva",
    "email": "ana@email.com",
    "cpf": "11111111111",
    "data_nascimento": "2000-01-01",
    "celular": "11999999999"
  },
  {
    "id": 2,
  	"nome": "Jose Jones", 
  	"email": "jose@email.com", 
  	"cpf": "22222222222", 
  	"data_nascimento": "1999-05-07", 
  	"celular": "11988888888" 
  },
  {
    "id": 3,
  	"nome": "Rosa Nunes", 
  	"email": "rosa@email.com", 
  	"cpf": "33333333333", 
  	"data_nascimento": "2000-10-01", 
  	"celular": "11777777777" 
  }
]
```
---
## Atualizar estudante (PUT)

Endpoint:

PUT /estudantes/1/

Request body:
```
{
  "nome": "Ana Silva Atualizada",
  "email": "ana@email.com",
  "cpf": "11111111111",
  "data_nascimento": "2000-01-01",
  "celular": "11988888888"
}
```
Response:
```
{
  "id": 1,
  "nome": "Ana Silva Atualizada",
  "email": "ana@email.com",
  "cpf": "11111111111",
  "data_nascimento": "2000-01-01",
  "celular": "11988888888"
}
```
---
## Deletar estudante (DELETE)

Endpoint:

DELETE /estudantes/1/

Response:
```
{
  "detail": "No Content"
}
```
---

### Criar curso

Endpoint:
POST /cursos/

```json
{
    "codigo": "LOG",
    "descricao": "Lógica de Programação",
    "nivel": "B"
} 
```

```json
{
    "codigo": "WEB",
    "descricao": "Desenvolvimento Web com Flask",
    "nivel": "I"
}
```

```json
{
    "codigo": "DS",
    "descricao": "Ciência de Dados com Python",
    "nivel": "A"
}
```
---
 Listar cursos (GET)

Endpoint:
GET /cursos/

Response:
```
[
  {
    "id": 1,
    "codigo": "LOG",
    "descricao": "Lógica de Programação",
    "nivel": "B"
  },
  {
      "codigo": "WEB",
      "descricao": "Desenvolvimento Web com Flask",
      "nivel": "I"
  },
  {
      "codigo": "DS",
      "descricao": "Ciência de Dados com Python",
      "nivel": "A"
  }
]
```
---
 Atualizar curso (PUT)

Endpoint:
PUT /cursos/1/

Request body:
```
{
  "codigo": "LOG",
  "descricao": "Lógica de Programação Atualizada",
  "nivel": "I"
}
```
Response:
```
{
  "id": 1,
  "codigo": "LOG",
  "descricao": "Lógica de Programação Atualizada",
  "nivel": "I"
}
```
---
 Deletar curso (DELETE)

Endpoint:
DELETE /cursos/1/

Response:
```
{
  "detail": "No Content"
}
```
---
### Criar matricula
Endpoint:
POST /matriculas/

```json
{
    "periodo": "M",
    "estudante": 1,
    "curso": 1
}
```

```json
{
    "periodo": "V",
    "estudante": 2,
    "curso": 3
}
```

```json
{
    "periodo": "N",
    "estudante": 3,
    "curso": 2
}
```
---
## 🔎 Endpoints personalizados

### Matrículas por estudante

Endpoint:
POST /matriculas/

Retorno:

```json
{
  "periodo": "M",
  "estudante": 1,
  "curso": 1
}
```
---

## Listar matrículas (GET)

Endpoint:
GET /matriculas/

Response:
```
[
  {
    "id": 1,
    "periodo": "M",
    "estudante": 1,
    "curso": 1
  },
  {
      "periodo": "V",
      "estudante": 2,
      "curso": 3
  },
  {
    "periodo": "N",
    "estudante": 3,
    "curso": 2
  }
]
```
---
## Atualizar matrícula (PUT)

Endpoint:
PUT /matriculas/1/

Request body:
```
{
  "periodo": "V",
  "estudante": 1,
  "curso": 2
}
```
Response:
```
{
  "id": 1,
  "periodo": "V",
  "estudante": 1,
  "curso": 2
}
```
---
 Deletar matrícula (DELETE)

Endpoint:
DELETE /matriculas/1/

Response:
```
{
  "detail": "No Content"
}
```
---
## 🔎 Endpoints de relacionamento

### 📌 Matrículas por estudante

**Endpoint:**
GET `/estudantes/{id}/matriculas/`

**Descrição:**
Retorna todas as matrículas de um estudante específico.

**Exemplo:**
GET `/estudantes/1/matriculas/`

**Response:**

```json id="c0r9xw"
[
  {
    "curso": "Lógica de Programação",
    "periodo": "Matutino"
  }
]
```

---

### 📌 Matrículas por curso

**Endpoint:**
GET `/cursos/{id}/matriculas/`

**Descrição:**
Retorna todos os estudantes matriculados em um curso.

**Exemplo:**
GET `/cursos/1/matriculas/`

**Response:**

```json id="d7y2qp"
[
  {
    "estudante_nome": "Ana Silva"
  }
]
```


## 🔐 Autenticação

O projeto utiliza autenticação básica do Django REST Framework.

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.BasicAuthentication',
    ],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```
---
## 📌 Status do projeto
🚧 Em desenvolvimento / melhorias contínuas
