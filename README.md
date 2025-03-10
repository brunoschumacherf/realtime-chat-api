# 📱 Realtime Chat API

API de chat em tempo real utilizando **ASP.NET Core** e **SignalR** para comunicação via WebSockets.

## 🚀 Tecnologias Utilizadas
- **ASP.NET Core 8**
- **SignalR** (WebSockets)
- **Entity Framework Core** (Banco de Dados)
- **SQL Server/PostgreSQL**
- **JWT para autenticação**
- **CORS para integração com o frontend**

## 📀 Funcionalidades Principais
✅ **Autenticação de usuários (JWT)**  
✅ **Envio e recebimento de mensagens em tempo real**  
✅ **Mensagens privadas e salas de bate-papo**  
✅ **Histórico de mensagens armazenado no banco**  
✅ **Notificações para mensagens não lidas**  
✅ **Confirmação de leitura das mensagens**  
✅ **Lista de usuários online e offline**  

## 📚 Estrutura do Projeto
```
/realtime-chat-api
  ├── Controllers/     # Endpoints da API
  ├── Models/         # Modelos de dados
  ├── Services/       # Regras de negócio
  ├── Hubs/           # SignalR WebSockets
  ├── Data/           # Configuração do banco
  ├── Program.cs      # Inicialização da aplicação
  ├── appsettings.json # Configuração do banco
```

## ⚙️ Configuração e Execução

### 1️⃣ Clonar o Repositório
```sh
git clone https://github.com/seu-usuario/realtime-chat-api.git
cd realtime-chat-api
```

### 2️⃣ Instalar Dependências
```sh
dotnet restore
```

### 3️⃣ Configurar o Banco de Dados  
No arquivo `appsettings.json`, configure a string de conexão para seu banco de dados SQL Server ou PostgreSQL.

### 4️⃣ Executar as Migrações do Banco
```sh
dotnet ef database update
```

### 5️⃣ Executar o Projeto
```sh
dotnet run
```

O servidor estará rodando em `http://localhost:5000`.

## 🛠️ Endpoints Principais

| Método | Rota                  | Descrição                     |
|--------|------------------------|--------------------------------|
| POST   | `/api/auth/register`   | Cadastro de usuários          |
| POST   | `/api/auth/login`      | Autenticação (JWT)            |
| GET    | `/api/users`           | Lista de usuários online/offline |
| GET    | `/api/chat/messages`   | Histórico de mensagens        |
| POST   | `/api/chat/send`       | Enviar mensagem para um usuário ou sala |

---

## 💪 WebSockets (SignalR)

### **Eventos do Servidor**
| Evento            | Descrição                                |
|------------------|----------------------------------------|
| `ReceiveMessage` | Enviar mensagem recebida para clientes |
| `UserConnected`  | Notificar quando um usuário entra no chat |
| `UserDisconnected` | Notificar quando um usuário sai do chat |

### **Eventos do Cliente**
| Evento           | Descrição                             |
|-----------------|-------------------------------------|
| `SendMessage`   | Enviar uma mensagem                |
| `JoinRoom`      | Entrar em uma sala específica      |



