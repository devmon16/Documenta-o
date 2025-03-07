# Megaman API

## Descrição
Este projeto é uma API desenvolvida em .NET Core 3.1 para listar os dados dos bosses do jogo Megaman. O principal objetivo é fornecer um backend que retorna dados em formato JSON conforme o exemplo abaixo:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## Tecnologias Utilizadas
- [.NET Core 3.1](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/)
- [SQL Server](https://www.microsoft.com/en-us/sql-server)
- [Newtonsoft.Json](https://www.newtonsoft.com/json)

## Estrutura do Projeto
```plaintext
.vs
.vscode
bin
Controllers
Database
middlewares
Models
obj
Properties
Services
appsettings.Development.json
appsettings.json  
global.json
MegamanApi.csproj  
MegamanApi.sln
Program.cs
Startup.cs
```

### Explicação da Estrutura
- **Controllers**: Contém os controladores da API.
- **Database**: Contém a configuração do banco de dados.
- **middlewares**: Middleware para tratamento de requisições e respostas.
- **Models**: Modelos de dados.
- **Services**: Implementação das regras de negócio.
- **appsettings.json**: Configuração da aplicação.
- **Startup.cs**: Configuração de serviços e middleware.
- **Program.cs**: Ponto de entrada da aplicação.

## Dependências
| Dependência | Versão | Descrição |
|-------------|--------|-------------|
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/3.1.8) | 3.1.8 | ORM para interação com bancos de dados. |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/3.1.8) | 3.1.8 | Ferramentas para desenvolvimento com EF Core. |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/3.1.8) | 3.1.8 | Provedor do EF Core para SQL Server. |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/12.0.2) | 12.0.2 | Biblioteca para manipulação de JSON. |

## Endpoints da API

### `GET /api/v1/robots`
Retorna todos os robôs cadastrados.

#### Resposta de Sucesso
```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  }
]
```

### `GET /api/v1/robots/{id}`
Retorna um robô específico pelo ID.

#### Resposta de Sucesso
```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

#### Resposta de Erro
```json
{
  "message": "Nenhum robo encontrado"
}
```

### `POST /api/v1/robots`
Cria um novo robô.

#### Resposta de Sucesso
```json
{
  "message": "Robô cadastrado com sucesso."
}
```

