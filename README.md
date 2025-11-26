# Hook Collector

Sistema para capturar e inspecionar requisições de webhooks. O projeto consiste em uma API backend e uma interface web para visualização dos webhooks recebidos.

## 🚀 Tecnologias

### Backend (API)

- **Fastify** - Framework web rápido
- **TypeScript** - Tipagem estática
- **Drizzle ORM** - ORM para PostgreSQL
- **PostgreSQL** - Banco de dados
- **Zod** - Validação de schemas
- **Scalar** - Documentação da API

### Frontend (Web)

- **React** - Biblioteca UI
- **TypeScript** - Tipagem estática
- **Vite** - Build tool e dev server

### Infraestrutura

- **Docker Compose** - Containerização do PostgreSQL
- **npm workspaces** - Gerenciamento de monorepo

## 📦 Instalação

### Pré-requisitos

- Node.js (versão 18 ou superior)
- Docker e Docker Compose

### Passos

1. Clone o repositório:

```bash
git clone <url-do-repositorio>
cd hook-collector
```

2. Instale as dependências:

```bash
npm install
```

3. Configure as variáveis de ambiente. Crie um arquivo `.env` na pasta `api`:

```env
DATABASE_URL=postgresql://docker:docker@localhost:5432/hook_collector
PORT=3333
NODE_ENV=development
```

4. Inicie o banco de dados PostgreSQL:

```bash
cd api
docker-compose up -d
```

5. Execute as migrações do banco de dados:

```bash
npm run db:migrate
```

## 🎯 Uso

### Desenvolvimento

Para iniciar o servidor da API em modo de desenvolvimento:

```bash
cd api
npm run dev
```

A API estará disponível em `http://localhost:3333`
A documentação da API estará disponível em `http://localhost:3333/docs`

Para iniciar a aplicação web:

```bash
cd web
npm run dev
```

A aplicação web estará disponível em `http://localhost:5173` (porta padrão do Vite)

### Scripts Úteis

#### API

- `npm run dev` - Inicia o servidor em modo desenvolvimento
- `npm run start` - Inicia o servidor em produção
- `npm run db:generate` - Gera migrações do banco de dados
- `npm run db:migrate` - Executa migrações do banco de dados
- `npm run db:studio` - Abre o Drizzle Studio para visualizar dados

#### Web

- `npm run dev` - Inicia o servidor de desenvolvimento
- `npm run build` - Cria build de produção
- `npm run preview` - Preview do build de produção

## 📝 Estrutura do Projeto

```
hook-collector/
├── api/              # Backend API
│   ├── src/
│   │   ├── db/       # Configuração do banco de dados
│   │   ├── routes/   # Rotas da API
│   │   └── server.ts # Servidor principal
│   └── docker-compose.yml
└── web/              # Frontend React
    └── src/
        └── app.tsx   # Componente principal
```

## 🔧 Configuração

O projeto utiliza variáveis de ambiente para configuração. Certifique-se de configurar:

- `DATABASE_URL` - URL de conexão com o PostgreSQL
- `PORT` - Porta do servidor (padrão: 3333)
- `NODE_ENV` - Ambiente de execução (development/production/test)
