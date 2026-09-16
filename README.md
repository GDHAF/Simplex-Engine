# Simplex Engine

Projeto desenvolvido com **ASP.NET Core MVC** utilizando **.NET 8**.

Atualmente, o repositório contém a estrutura inicial de uma aplicação web MVC, incluindo controlador, modelo de tratamento de erros, views Razor, arquivos de configuração e recursos estáticos.

## 🛠️ Tecnologias utilizadas

* **C#**
* **.NET 8**
* **ASP.NET Core MVC**
* **Razor**
* **HTML**
* **CSS**
* **JavaScript**
* **Bootstrap**

## 📂 Estrutura do projeto

```text
Simplex-Engine/
│
├── Controllers/
│   └── HomeController.cs
│
├── Models/
│   └── ErrorViewModel.cs
│
├── Properties/
│   └── launchSettings.json
│
├── Views/
│   ├── Home/
│   │   ├── Index.cshtml
│   │   └── Privacy.cshtml
│   │
│   ├── Shared/
│   │   ├── Error.cshtml
│   │   ├── _Layout.cshtml
│   │   ├── _Layout.cshtml.css
│   │   └── _ValidationScriptsPartial.cshtml
│   │
│   ├── _ViewImports.cshtml
│   └── _ViewStart.cshtml
│
├── wwwroot/
│   ├── css/
│   │   └── site.css
│   │
│   ├── js/
│   │   └── site.js
│   │
│   ├── lib/
│   │   └── bootstrap/
│   │
│   └── favicon.ico
│
├── appsettings.json
├── appsettings.Development.json
└── Simplex-Engine.csproj
```

Na raiz do repositório também estão presentes:

```text
.gitattributes
.gitignore
LICENSE.txt
README.md
Simplex-Engine.slnx
```

## 🏗️ Arquitetura atual

O projeto utiliza o padrão **MVC (Model-View-Controller)** disponibilizado pelo ASP.NET Core.

A estrutura atual pode ser representada da seguinte forma:

```text
                    Aplicação ASP.NET Core
                             │
                             ▼
                        Roteamento
                             │
                             ▼
                        Controller
                             │
                    ┌────────┴────────┐
                    ▼                 ▼
                  Model              View
                    │                 │
                    └────────┬────────┘
                             ▼
                          Resposta
```

### Controllers

O projeto possui atualmente o `HomeController`, responsável pelas ações principais da aplicação:

* `Index()`
* `Privacy()`
* `Error()`

O controlador também utiliza `ILogger<HomeController>` para registro de logs.

### Models

Existe atualmente o modelo `ErrorViewModel`, utilizado pela página de erro.

Ele contém:

* `RequestId`, utilizado para identificar a requisição;
* `ShowRequestId`, que determina se o identificador deve ser apresentado.

### Views

As páginas da aplicação são implementadas utilizando **Razor** (`.cshtml`).

Atualmente existem views para:

* Página inicial;
* Página de privacidade;
* Página de erro;
* Layout compartilhado;
* Scripts de validação.

A página inicial atualmente utiliza a estrutura padrão do template MVC do ASP.NET Core.

## ⚙️ Configuração da aplicação

O ponto de entrada da aplicação está localizado em:

```text
Simplex-Engine/Program.cs
```

A aplicação atualmente:

* registra os Controllers com Views;
* configura o pipeline HTTP;
* utiliza tratamento de exceções em ambiente de produção;
* utiliza HSTS fora do ambiente de desenvolvimento;
* redireciona requisições HTTP para HTTPS;
* disponibiliza arquivos estáticos;
* configura o roteamento;
* habilita autorização;
* utiliza roteamento convencional de Controllers.

A rota padrão configurada é:

```text
{controller=Home}/{action=Index}/{id?}
```

Portanto, quando nenhuma rota específica é informada, a aplicação utiliza:

```text
HomeController
    └── Index()
```

## 📦 Configuração do projeto

O projeto utiliza o SDK web do .NET:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
```

O framework utilizado é:

```xml
<TargetFramework>net8.0</TargetFramework>
```

Também estão habilitados:

```xml
<Nullable>enable</Nullable>
<ImplicitUsings>enable</ImplicitUsings>
```

O namespace raiz configurado é:

```text
Simplex_Engine
```

## 🚀 Como executar

### Pré-requisitos

Para executar o projeto, é necessário possuir o **.NET 8 SDK** instalado.

### Clonar o repositório

```bash
git clone https://github.com/GDHAF/Simplex-Engine.git
```

Entrar no diretório:

```bash
cd Simplex-Engine
```

### Restaurar o projeto

```bash
dotnet restore
```

### Compilar

```bash
dotnet build
```

### Executar

```bash
dotnet run
```

Após iniciar a aplicação, o ASP.NET Core exibirá no terminal os endereços configurados para acesso à aplicação.

## ⚙️ Configurações

As configurações da aplicação estão armazenadas nos arquivos:

```text
appsettings.json
appsettings.Development.json
```

A configuração principal de logging atualmente define:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

## 🔒 Segurança

A configuração atual da aplicação inclui alguns mecanismos fornecidos pelo ASP.NET Core:

* Redirecionamento para HTTPS;
* HSTS em ambiente diferente de desenvolvimento;
* Tratamento de exceções em produção;
* Configuração de autorização no pipeline HTTP.

Esses recursos fazem parte da configuração atual da aplicação e não representam, por si só, um sistema completo de autenticação ou gerenciamento de usuários.

## 📋 Estado atual

O projeto atualmente contém a estrutura inicial de uma aplicação ASP.NET Core MVC.

Entre os componentes presentes estão:

* Configuração de uma aplicação web ASP.NET Core;
* `HomeController`;
* `ErrorViewModel`;
* Views Razor;
* Layout compartilhado;
* Página inicial;
* Página de privacidade;
* Página de erro;
* Arquivos CSS;
* Arquivos JavaScript;
* Bootstrap;
* Configurações de aplicação;
* Configuração de HTTPS;
* Configuração de HSTS;
* Roteamento MVC convencional.

