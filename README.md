<h1 align="center">Task Management API</h1>

<p align="center">
  API REST para gerenciamento de tarefas desenvolvida com NestJS e TypeScript.
</p>

<p align="center">
  <a href="#tecnologias">Tecnologias</a> •
  <a href="#funcionalidades">Funcionalidades</a> •
  <a href="#como-executar">Como executar</a> •
  <a href="#endpoints">Endpoints</a> •
  <a href="#contribuindo">Contribuindo</a>
</p>

## 📌 Sobre o projeto

A **Task Management API** é uma API REST para gerenciamento de tarefas, permitindo criar, consultar, atualizar e excluir tarefas.

O projeto foi desenvolvido com **NestJS e TypeScript**, utilizando **Prisma ORM** para acesso ao banco de dados, **Redis** e **Docker** para padronização e execução do ambiente.

## 💻 Tecnologias

- Node.js
- TypeScript
- NestJS
- Prisma ORM
- MySQL
- Redis
- Docker
- Docker Compose

## ⚙️ Funcionalidades

- Criar novas tarefas
- Listar todas as tarefas
- Atualizar informações de uma tarefa
- Alterar o status de conclusão
- Excluir tarefas

## 🚀 Como executar

A forma recomendada de executar o projeto é utilizando **Docker e Docker Compose**, permitindo iniciar a aplicação e suas dependências de forma padronizada.

### Pré-requisitos

Antes de começar, você precisa ter instalado:

- Docker
- Docker Compose
- Git

### 1. Clone o repositório

```bash
git clone https://github.com/pedro-henrique1/task-management-api.git
```

Entre no diretório:

```bash
cd task-management-api
```

### 2. Configure as variáveis de ambiente

Crie o arquivo `.env` utilizando o `.env.example` como referência:

```bash
cp .env.example .env
```

Configure as variáveis necessárias de acordo com seu ambiente.

### 3. Inicie a aplicação

```bash
docker compose up -d --build
```

Para acompanhar os logs:

```bash
docker compose logs -f
```

Para encerrar os containers:

```bash
docker compose down
```

## 📍 Endpoints

Principais endpoints disponíveis na API:

| Método | Endpoint | Descrição |
| --- | --- | --- |
| `GET` | `/tasks` | Lista todas as tarefas |
| `POST` | `/tasks` | Cria uma nova tarefa |
| `PUT` | `/tasks/:id` | Atualiza os dados de uma tarefa |
| `PATCH` | `/tasks/:id` | Atualiza o status de conclusão |
| `DELETE` | `/tasks/:id` | Exclui uma tarefa |

### Criar uma tarefa

```http
POST /tasks
```

Exemplo de requisição:

```json
{
  "title": "Estudar NestJS",
  "description": "Estudar arquitetura e boas práticas com NestJS",
  "completed": false
}
```

### Atualizar o status

```http
PATCH /tasks/:id
```

```json
{
  "completed": true
}
```

## 📁 Estrutura do projeto

```text
src
├── app.module.ts
├── main.ts
├── modules
│   ├── config
│   │   ├── configuration.ts
│   │   └── validation.ts
│   ├── prisma
│   │   ├── prisma.module.ts
│   │   └── prisma.service.ts
│   └── tasks
│       ├── dtos
│       ├── task.controller.ts
│       ├── task.module.ts
│       └── task.service.ts
└── redis-client.ts
```

O projeto segue a estrutura modular do NestJS, separando as responsabilidades da aplicação em módulos.


## 📄 Licença

Este projeto está sob a licença MIT. Consulte o arquivo [license](./LICENSE) para mais informações.


## 🤝 Contribuindo

Contribuições são bem-vindas.

1. Faça um fork do projeto.
2. Crie uma branch para sua alteração:

```bash
git checkout -b feature/nome-da-feature
```

3. Faça suas alterações e crie o commit.
4. Envie a branch para seu fork.
5. Abra um Pull Request descrevendo as alterações realizadas.
