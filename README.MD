<table align="center">
    <tr>
        <td align="center" width="25%">
            <img src="https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png" alt="Cutman">
        </td>
        <td align="center" width="75%">
          
# Cutman API
          
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/user/repository/actions)
[![Latest release](https://img.shields.io/github/v/release/user/CutmanAPI)](https://github.com/user/CutmanAPI/releases/latest)
        </td>
    </tr>
</table>

## 📌 Visão Geral
A **Cutman API** permite gerenciar robôs inspirados no universo de Mega Man. Ela fornece endpoints para listar, buscar e adicionar novos robôs. 

---
## 📖 Sumário
1. [Instalação](#instalação)
2. [Configuração do Projeto](#configuração-do-projeto)
3. [Endpoints](#endpoints)
4. [Fluxo de Uso](#fluxo-de-uso)
5. [Técnicas Utilizadas](#técnicas-utilizadas)
6. [Contribuições](#contribuições)
7. [Licença](#licença)

---
## 🛠️ Instalação
Clone o repositório e execute o projeto:
```sh
  git clone https://github.com/user/CutmanAPI.git
  cd CutmanAPI
  dotnet run
```

---
## ⚙️ Configuração do Projeto
| Dependência | Versão | Descrição |
|-------------|--------|-----------|
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/) | 3.1.8 | ORM para manipulação de banco de dados |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/) | 3.1.8 | Provedor para SQL Server |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/) | 12.0.2 | Manipulação de JSON |

Configuração de ambiente:
```sh
  export ASPNETCORE_ENVIRONMENT=Development
```

---
## 🚀 Endpoints
### 🔍 Listar todos os robôs
**GET** `/api/v1/robots`
```sh
  curl -X GET http://localhost:5000/api/v1/robots
```
Resposta esperada:
```json
  [
    {
      "id": 1,
      "code": "DLN/DRN-003",
      "name": "Cutman",
      "hp": 150
    }
  ]
```

### 🔍 Buscar robô por ID
**GET** `/api/v1/robots/{id}`
```sh
  curl -X GET http://localhost:5000/api/v1/robots/1
```
Resposta esperada:
```json
  {
    "id": 1,
    "code": "DLN/DRN-003",
    "name": "Cutman",
    "hp": 150
  }
```

### ➕ Criar um novo robô
**POST** `/api/v1/robots`
```sh
  curl -X POST http://localhost:5000/api/v1/robots -H "Content-Type: application/json" -d '{ "name": "NewRobot", "code": "DLN/DRN-004", "hp": 200 }'
```

---
## 🔄 Fluxo de Uso
1. O cliente faz uma requisição **GET** para listar os robôs.
2. O usuário pode buscar um robô específico através do seu ID.
3. Para adicionar um novo robô, o usuário envia uma requisição **POST**.

---
## 📌 Técnicas Utilizadas
- **Arquitetura MVC** para separação de responsabilidades.
- **Entity Framework Core** para acesso a banco de dados.
- **Injeção de Dependência** para desacoplamento do código.
- **Middleware** para interceptação de requisições.

---
## :gear: Arch

```🌐
src
├── 📂 Controllers      [Routes for endpoints]
├── 📂 Models           [Database models]
├── 📂 Services         [Business rules]
├── 📂 Middlewares      [Intermediate functions between the HTTP request and the final server response]
├── 📂 Database         [Structures related to the database]
│   ├── 📂 DTOs             [Input Models and View Models (Data Transfer Objects)]
│   ├── 📂 EntityFramework  [Files related to the ORM Entity Framework]
│   │     ├── 📂 Context         [Entity context settings]
│   │     ├── 📂 Migrations      [Migrations for database updates]
│   ├── 📂 Repositories     [Repository pattern]
```

---
## 🤝 Contribuições
Contribuições são bem-vindas! Para contribuir:
1. Faça um fork do repositório.
2. Crie uma nova branch (`git checkout -b feature/nova-feature`).
3. Faça suas alterações e commit (`git commit -m 'Adiciona nova feature'`).
4. Envie um pull request.

---
## 📜 Licença
Este projeto está licenciado sob a [MIT License](https://opensource.org/licenses/MIT).

---
⌨️ MarioCarvalho -
[Github](https://github.com/MarioECNacimento)
