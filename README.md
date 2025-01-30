# Qulture Challenge

## Descrição
Este é um sistema completo composto por uma aplicação backend desenvolvida com **Ruby on Rails** e uma aplicação frontend criada em **React com JavaScript**. O backend oferece uma API para gerenciamento de empresas e seus funcionários, enquanto o frontend permite uma interface amigável para visualização e gestão dessas informações.

O projeto utiliza Docker e Docker Compose para gerenciamento e execução dos ambientes, garantindo consistência e facilidade na configuração.

**Dependência:** O frontend depende que o backend esteja em execução para funcionar corretamente.

---

## Tecnologias Utilizadas

### Backend
- ![Ruby on Rails](https://img.shields.io/badge/Ruby_on_Rails-CC0000?style=flat-square&logo=rubyonrails&logoColor=white) **Ruby on Rails**
- ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white) **PostgreSQL**
- ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) **Docker**

### Frontend
- ![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=white) **React**
- ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black) **JavaScript**
- ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) **Docker**

---

## Configuração do Projeto com Docker Compose

### Requisitos
Certifique-se de ter os seguintes softwares instalados:
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Passo a Passo
#### Backend
1. Clone o repositório backend:
   ```bash
   git clone git@github.com:lucsduartee/qulture-challenge.git
   cd qulture-challenge
   ```

2. Certifique-se de que o Docker esteja em execução.

3. Construa e inicie os contêineres:
   ```bash
   docker-compose up --build
   ```

4. A API estará disponível em [http://localhost:3001](http://localhost:3001).
5. Acesse o frontend da aplicação em [http://localhost:3000](http://localhost:3000).

### Comandos úteis
- Parar os contêineres:
  ```bash
  docker-compose down
  ```
- Ver os logs:
  ```bash
  docker-compose logs -f
  ```
---
### Testes unitários
É possível rodar alguns testes unitários tanto no backend quanto no front

1. No frontend:
   ```bash
   cd qulture-challenge
   docker compose run --rm nextjs bash

   # já no bash do container

   > npm run test
   ```

1. No backend:
   ```bash
   cd qulture-challenge
   docker compose run --rm api bash

   # já no bash do container

   > rails test
   ```

---

## Rotas da API

| Método | Endpoint                                | Descrição                               |              Payload                    |
|--------|-----------------------------------------|-----------------------------------------|-----------------------------------------|
| GET    | /api/companies                          | Lista todas as empresas                 |                                         |
| POST   | /api/companies                          | Cria uma nova empresa                   |            `{ "name": "" }`             |
| GET    | /api/companies/:id                      | Mostra uma empresa específica           |                                         |
| GET    | /api/companies/:company_id/employees    | Lista os funcionários de uma empresa    |                                         |
| POST   | /api/companies/:company_id/employees    | Cria um novo funcionário para a empresa |`{"email": "","name": "","picture":  ""}`|
| DELETE | /api/employees/:id                      | Exclui um funcionário                   |                                         |
| POST   | /api/employees/:id/promote              | Promove um funcionário                  |       `{ "employee_id": <number> }`      |
| GET    | /api/employees/:id/peers                | Lista colegas de um funcionário         |                                         |
| GET    | /api/employees/:id/subordinates         | Lista subordinados de um funcionário    |                                         |
| GET    | /api/employees/:id/deep_subordinates    | Lista subordinados em todos os níveis   |                                         |

---

## Páginas Principais

1. **Colaboradores:**  
   A página permite a visualização de uma lista de colaboradores, além de suas informações detalhadas.

2. **Empresas:**  
   Nesta página é possível visualizar as empresas cadastradas e gerenciar suas informações.

---

## Wireframes
> **Espaço reservado para prints de wireframes:**
> Cole aqui capturas de tela que representem as páginas principais e funcionalidades da aplicação.

---

## Referências
- [Documentação do Docker](https://docs.docker.com/)

