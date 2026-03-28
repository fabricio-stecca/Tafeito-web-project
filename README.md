# Tá Feito - Gerenciador de Checklists

![Tá Feito](https://img.shields.io/badge/Tá%20Feito-v1.0.0-blue)
![Angular](https://img.shields.io/badge/Angular-18.2.0-red)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-green)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-orange)

Um aplicativo web completo para criar, gerenciar e acompanhar checklists e listas de tarefas. Desenvolvido com **Angular** no frontend e **FastAPI** no backend, com **Firebase Firestore** como banco de dados.

## ✨ Features

### Autenticação & Usuário
- ✅ Cadastro de usuários com email/senha
- ✅ Login com JWT
- ✅ Gerenciamento de perfil (nome, telefone)
- ✅ Alteração de senha
- ✅ Token de autenticação (30 minutos)

### Checklists
- ✅ Criar nova checklist
- ✅ Editar checklist existente
- ✅ Deletar checklist
- ✅ Categorizar checklists
- ✅ Descrição de checklist
- ✅ Data limite (opcional)
- ✅ Mudança de cor por data limite
- ✅ Mensagens motivacionais

### Tarefas/Items
- ✅ Adicionar itens à checklist
- ✅ Marcar itens como concluído
- ✅ Editar itens
- ✅ Deletar itens
- ✅ Descrição para cada item
- ✅ Atualização em massa de itens

### Interface
- ✅ Design responsivo
- ✅ Tema moderno
- ✅ Componentes reutilizáveis
- ✅ Página "Sobre Nós"
- ✅ Página de Contato
- ✅ Notificações (toastr)

## 🏗️ Arquitetura

```
┌─────────────────┐
│   Frontend      │
│    Angular      │
│   (Port 4200)   │
└────────┬────────┘
         │ HTTP/REST
         │
┌────────▼────────────────┐
│   Backend API           │
│   FastAPI-CORS          │
│   (Port 8001)           │
└────────┬────────────────┘
         │ Admin SDK
         │
┌────────▼────────────────┐
│   Firebase Firestore    │
│   (Database)            │
└─────────────────────────┘
```

## 🛠️ Tecnologias

### Frontend
- **Angular** 18.2.0 - Framework web
- **Angular Material** - UI Components
- **RxJS** - Reactive Programming
- **TypeScript** - Linguagem de tipagem
- **SCSS** - Estilização
- **ng-otp-input** - Entrada de OTP
- **ngx-mask** - Máscara de input
- **ngx-toastr** - Notificações

### Backend
- **FastAPI** 0.104.1 - Framework API
- **Uvicorn** - Servidor WSGI
- **Firebase Admin SDK** - Gerenciamento Firestore
- **Pydantic** - Validação de dados
- **JWT (python-jose)** - Autenticação
- **Passlib + Bcrypt** - Hash de senhas
- **CORS Middleware** - Requisições entre domínios

### Database
- **Firebase Firestore** - NoSQL database em tempo real
- **Authentication Rules** - Segurança de dados

## 📁 Prévia de Estrutura

```
Tafeito-web-project/
├── tf-backend/
│   ├── main.py                      # API principal (FastAPI)
│   ├── config.py                    # Configurações
│   ├── models.py                    # Schemas Pydantic
│   ├── firebase_service.py          # Serviço Firebase
│   ├── requirements.txt             # Dependências Python
│   ├── FIREBASE_SETUP.md            # Setup Firebase
│   ├── test_api.py                  # Testes de API
│   ├── test_checklist_robust.py     # Testes de Checklist
│   ├── .gitignore
│   └── firebase-credentials.json    # 
│
├── tf-frontend/
│   ├── src/
│   │   ├── app/
│   │   │   ├── pages/               # Componentes de páginas
│   │   │   │   ├── initial/         # Página inicial
│   │   │   │   ├── login/           # Login
│   │   │   │   ├── signup/          # Cadastro
│   │   │   │   ├── home/            # Home
│   │   │   │   ├── new-checklist/   # Nova checklist
│   │   │   │   ├── checklist-tasks/ # Tarefas
│   │   │   │   ├── edit-checklist/  # Editar checklist
│   │   │   │   ├── account/         # Minha Conta
│   │   │   │   ├── about-us/        # Sobre Nós
│   │   │   │   ├── contact/         # Contato
│   │   │   │   └── confirm-email/   # Confirmar Email
│   │   │   ├── components/          # Componentes reutilizáveis
│   │   │   │   ├── button/
│   │   │   │   ├── header/
│   │   │   │   ├── footer/
│   │   │   │   ├── input/
│   │   │   │   ├── loading/
│   │   │   │   ├── confirmation-modal/
│   │   │   │   └── checklist-card/
│   │   │   ├── services/            # Serviços HTTP
│   │   │   ├── guards/              # Guards de rota
│   │   │   │   ├── auth.guard.ts
│   │   │   │   ├── noauth.guard.ts
│   │   │   │   └── 404.guard.ts
│   │   │   ├── interceptors/        # HTTP Interceptors
│   │   │   │   └── auth.interceptor.ts
│   │   │   ├── helpers/
│   │   │   │   ├── directives/      # Diretivas customizadas
│   │   │   │   ├── types/           # Tipos TypeScript
│   │   │   │   └── validators/      # Validadores
│   │   │   ├── app.routes.ts        # Definição de rotas
│   │   │   ├── app.config.ts        # Configuração app
│   │   │   ├── app.component.ts     # Root component
│   │   │   └── app.component.html
│   │   ├── styles.scss              # Estilos globais
│   │   ├── index.html
│   │   └── main.ts                  # Entry point
│   ├── public/
│   │   ├── images/                  # Assets de imagens
│   │   └── json/
│   │       └── frases.json          # Mensagens motivacionais
│   ├── package.json                 # Dependências Node
│   ├── angular.json                 # Configuração Angular
│   ├── tsconfig.json                # Configuração TypeScript
│   └── .gitignore
│
├── .gitignore
└── README.md                        # Este arquivo
```

## 🚀 Setup e Instalação

### Pré-requisitos

- **Node.js** 18+ e **npm**
- **Python** 3.9+
- **Git**
- **Conta Firebase** com projeto criado

### 1️⃣ Clone o Repositório

```bash
git clone https://github.com/seu-usuario/Tafeito-web-project.git
cd Tafeito-web-project
```

### 2️⃣ Setup Firebase

Siga o guia completo em [tf-backend/FIREBASE_SETUP.md](tf-backend/FIREBASE_SETUP.md):

1. Criar projeto no [Firebase Console](https://console.firebase.google.com/)
2. Ativar Firestore Database em modo teste
3. Baixar credenciais (Service Account JSON)
4. Colocar arquivo em `tf-backend/firebase-credentials.json`

### 3️⃣ Backend Setup

```bash
cd tf-backend

# Instalar dependências
pip install -r requirements.txt

# Configurar variáveis de ambiente (opcional)
# Criar arquivo .env com as configurações necessárias
```

### 4️⃣ Frontend Setup

```bash
cd tf-frontend

# Instalar dependências
npm install
```

## 🏃 Como Rodar Localmente

### Backend

```bash
cd tf-backend

# Rodar servidor
python main.py

# Servidor estará em http://localhost:8001
# Documentação da API: http://localhost:8001/docs
```

### Frontend

```bash
cd tf-frontend

# Rodar servidor de desenvolvimento
npm start

# Frontend estará em http://localhost:4200
```

### Testar API

```bash
cd tf-backend

# Teste básico da API
python test_api.py

# Teste robusto de checklist
python test_checklist_robust.py
```

## 📡 Endpoints da API

### 🔐 Autenticação

| Método | Endpoint | Descrição | Auth |
|--------|----------|-----------|------|
| POST | `/auth/signup` | Cadastrar novo usuário | ❌ |
| POST | `/auth/login` | Fazer login | ❌ |
| GET | `/auth/me` | Obter dados do usuário logado | ✅ |
| PUT | `/auth/profile` | Atualizar perfil | ✅ |
| PUT | `/auth/password` | Alterar senha | ✅ |

### 📋 Checklists

| Método | Endpoint | Descrição | Auth |
|--------|----------|-----------|------|
| POST | `/checklists` | Criar nova checklist | ✅ |
| GET | `/checklists` | Listar checklists do usuário | ✅ |
| GET | `/checklists/{id}` | Obter checklist específica | ✅ |
| PUT | `/checklists/{id}` | Atualizar checklist | ✅ |
| DELETE | `/checklists/{id}` | Deletar checklist | ✅ |
| PUT | `/checklists/{id}/items` | Atualizar items em massa | ✅ |

### 📝 Exemplo de Requisição

**Criar Checklist:**
```bash
curl -X POST http://localhost:8001/checklists \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Minha Checklist",
    "category": "Trabalho",
    "description": "Tarefas importantes",
    "limit_date": "2024-12-31T23:59:59",
    "change_color_by_date": true,
    "show_motivational_msg": true
  }'
```

## 🗄️ Estrutura do Banco de Dados

### Coleção: `users`

```json
{
  "id": "uuid",
  "email": "user@example.com",
  "name": "João Silva",
  "phone": "+55 11 98765-4321",
  "password": "hashed_password_bcrypt",
  "created_at": "2024-03-28T10:30:00Z",
  "updated_at": "2024-03-28T10:30:00Z"
}
```

### Coleção: `checklists`

```json
{
  "id": "uuid",
  "user_id": "uuid",
  "name": "Compras do mês",
  "category": "Pessoal",
  "description": "Itens essenciais para comprar",
  "limit_date": "2024-04-30T23:59:59Z",
  "change_color_by_date": true,
  "show_motivational_msg": true,
  "created_at": "2024-03-28T10:30:00Z",
  "updated_at": "2024-03-28T10:30:00Z"
}
```

### Coleção: `checklist_items`

```json
{
  "id": "uuid",
  "checklist_id": "uuid",
  "title": "Leite integral",
  "description": "2 litros",
  "completed": false,
  "created_at": "2024-03-28T10:30:00Z",
  "updated_at": "2024-03-28T10:30:00Z"
}
```

## 📚 Guias

### Como Adicionar uma Nova Rota no Frontend

1. Criar novo componente:
```bash
ng generate component pages/nova-pagina
```

2. Adicionar em `app.routes.ts`:
```typescript
{
  path: 'nova-pagina',
  loadComponent: () => import('./pages/nova-pagina/nova-pagina.component').then(m => m.NovaPaginaComponent),
  canActivate: [AuthGuard],
  title: 'Tá Feito - Nova Página'
}
```


### Configurar Variáveis de Ambiente

Criar arquivo `.env` em `tf-backend/`:
```
FIREBASE_PROJECT_ID=project-tafeito
SECRET_KEY=sua-chave-secreta-super-segura
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
DEBUG=False
```

### Deploy no Firebase Hosting (Frontend)

```bash
cd tf-frontend

# Build para produção
npm run build

# Deploy (requer Firebase CLI)
firebase deploy --only hosting
```

## 🤝 Contribuindo

Contribuições são bem-vindas! Por favor:

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para detalhes.


## 🎯 Roadmap

- [ ] Integração com OAuth (Google, GitHub)
- [ ] Exportar checklists em PDF
- [ ] Compartilhamento de checklists entre usuários
- [ ] Sistema de lembretes e notificações
- [ ] Aplicativo mobile (React Native)
- [ ] Sincronização em tempo real com WebSocket
- [ ] Análise de produtividade e estatísticas
- [ ] Temas customizáveis

---

**Desenvolvido com ❤️ usando Angular, FastAPI e Firebase**
