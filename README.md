# Next Talent - Backend

Este é o backend do projeto **Next Talent**, uma plataforma para centralizar e divulgar iniciativas de programas de formação para talentos em tecnologia. O projeto foi desenvolvido com **NestJS**, **Sequelize** e **PostgreSQL**.

## 🚀 Visão Geral

O backend é responsável por gerenciar os dados dos programas de formação, oferecendo uma API RESTful completa para operações de CRUD (Create, Read, Update, Delete). A arquitetura segue as melhores práticas de desenvolvimento, com uma estrutura modular e escalável.

## ✨ Tecnologias Utilizadas

- **Node.js** (v22.x)
- **NestJS** (v11.x)
- **Sequelize** (v6.x)
- **PostgreSQL** (v14.x ou superior)
- **TypeScript** (v5.x)

## 🛠️ Configuração do Ambiente

Siga os passos abaixo para configurar e executar o projeto em seu ambiente local.

### 1. Pré-requisitos

- **Node.js**: Certifique-se de ter o Node.js instalado (versão 22 ou superior).
- **PostgreSQL**: É necessário ter um servidor PostgreSQL rodando localmente ou acessível.
- **Gerenciador de Pacotes**: Este projeto utiliza o `npm`.

### 2. Clonar o Repositório

```bash
# (Caso você tenha recebido o projeto como .zip, descompacte-o)
unzip next-talent-backend.zip
cd next-talent-backend
```

### 3. Instalar Dependências

Instale todas as dependências do projeto com o seguinte comando:

```bash
npm install
```

### 4. Configurar Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto, copiando o exemplo `.env.example`:

```bash
cp .env.example .env
```

Abra o arquivo `.env` e ajuste as variáveis de conexão com o seu banco de dados PostgreSQL:

```ini
# Configuração do Banco de Dados PostgreSQL
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=seu_usuario_postgres
DB_PASSWORD=sua_senha_postgres
DB_DATABASE=next_talent_db

# Porta do servidor
PORT=3001

# Ambiente
NODE_ENV=development
```

**Importante**: Crie o banco de dados `next_talent_db` no seu servidor PostgreSQL antes de prosseguir.

### 5. Popular o Banco de Dados (Seed)

Para popular o banco de dados com dados de exemplo, execute o script de seed:

```bash
npm run seed
```

Este comando irá criar as tabelas e inserir os programas iniciais definidos no seeder.

## ▶️ Executando o Projeto

Após a configuração, inicie o servidor de desenvolvimento com o comando:

```bash
npm run start:dev
```

O servidor estará disponível em `http://localhost:3001`.

## 🧪 Testando a API

Uma collection completa do Insomnia (`insomnia_collection.json`) está incluída na raiz do projeto para facilitar os testes dos endpoints.

1.  **Importe** o arquivo `insomnia_collection.json` no seu Insomnia.
2.  O ambiente base já estará configurado para `http://localhost:3001`.
3.  Utilize as requisições pré-configuradas para testar o CRUD de programas.

## 📂 Estrutura de Pastas

A estrutura do projeto foi organizada de forma modular para garantir clareza e escalabilidade:

```
src/
├── config/         # Configurações (ex: banco de dados)
├── controllers/    # Camada de entrada da API (rotas)
├── database/
│   ├── migrations/ # (Opcional) Migrations do banco
│   └── seeders/    # Dados iniciais para o banco
├── dto/            # Data Transfer Objects (validação de dados)
├── models/         # Modelos do Sequelize (representação das tabelas)
├── repositories/   # Camada de acesso aos dados
├── services/       # Camada de regras de negócio
├── app.module.ts   # Módulo principal da aplicação
└── main.ts         # Ponto de entrada da aplicação
```

## 📝 Endpoints da API

A API oferece os seguintes endpoints para o recurso `programs`:

| Método | Rota                  | Descrição                               |
| :----- | :-------------------- | :---------------------------------------- |
| `GET`  | `/programs`           | Lista todos os programas.                 |
| `GET`  | `/programs/:id`       | Busca um programa específico por ID.      |
| `POST` | `/programs`           | Cria um novo programa.                    |
| `PUT`  | `/programs/:id`       | Atualiza um programa existente.           |
| `DELETE`| `/programs/:id`       | Deleta um programa.                       |
| `GET`  | `/programs/statistics`| Retorna estatísticas sobre os programas.  |

---
