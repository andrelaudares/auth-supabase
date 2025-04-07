# FinanceAI

Sistema de autenticação completo utilizando React no frontend e FastAPI com Supabase no backend.

## Estrutura do Projeto

```
FinanceAI/
├── backend/              # API FastAPI
│   ├── app/
│   │   ├── api/          # Rotas da API
│   │   ├── core/         # Configurações e utilitários
│   │   ├── db/           # Conexão com banco de dados
│   │   └── models/       # Modelos de dados
│   ├── main.py           # Ponto de entrada da API
│   └── requirements.txt  # Dependências do backend
├── frontend/             # Interface React
│   ├── public/
│   ├── src/
│   │   ├── components/   # Componentes React
│   │   ├── pages/        # Páginas da aplicação
│   │   ├── services/     # Serviços de API
│   │   └── types/        # Tipos TypeScript
│   └── package.json      # Dependências do frontend
└── .env                  # Variáveis de ambiente
```

## Requisitos

- Python 3.9 ou superior
- Node.js 14 ou superior
- Ambiente virtual Python (opcional, mas recomendado)

## Configuração

### Banco de Dados (Supabase)

Antes de executar o projeto, certifique-se de:

1. Ter uma conta no Supabase e um projeto criado
2. Configurar as credenciais no arquivo `.env`
3. Ter a tabela `profiles` criada com os campos:
   - id (UUID, chave primária, referência para auth.users)
   - email (TEXT, único)
   - name (TEXT)
   - phone (TEXT)
   - created_at (TIMESTAMP)

### Backend (FastAPI)

1. Navegue até a pasta do backend:
   ```
   cd backend
   ```

2. Instale as dependências:
   ```
   pip install -r requirements.txt
   ```

3. Execute o servidor:
   ```
   python main.py
   ```

   O backend estará disponível em `http://localhost:8000`.

### Frontend (React)

1. Navegue até a pasta do frontend:
   ```
   cd frontend
   ```

2. Instale as dependências:
   ```
   npm install
   ```

3. Execute o servidor de desenvolvimento:
   ```
   npm start
   ```

   O frontend estará disponível em `http://localhost:3000`.

## Funcionalidades

### Autenticação

- Registro de usuários com validação de dados
- Login com email e senha
- Proteção de rotas autenticadas
- Logout de usuários

### Usuários

- Visualização de dados do usuário logado

## API Endpoints

### Autenticação

- `POST /api/auth/register`: Registra um novo usuário
- `POST /api/auth/login`: Autentica um usuário e retorna um token

### Usuários

- `GET /api/users/me`: Retorna informações do usuário autenticado 