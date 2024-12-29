<h1 align="center">
   Projeto MVC - Agenda de Contatos
</h1>

Este projeto é uma aplicação web desenvolvida com **ASP.NET Core** utilizando **MVC** (Model-View-Controller) para a gestão de uma agenda de contatos. O sistema permite adicionar, editar, excluir e listar contatos, armazenando as informações no banco de dados **SQL Server**.   

## Tecnologias Utilizadas   

- **ASP.NET Core** (versão 7.0)
- **Entity Framework Core** (para integração com o banco de dados)
- **SQL Server** (para armazenamento de dados)
- **Bootstrap** (para design responsivo)
- **jQuery Validation** (para validação de formulários)

## Diagrama de Estrutura   

O diagrama abaixo ilustra a estrutura do projeto, mostrando a relação entre os componentes principais:   

```   
+------------------+     +---------------------+
|    Controllers   |     |       Models        |
|------------------|     |---------------------|
| HomeController   |     | Contato (Classe)    |
| ContatoController| <--> | AgendaContext       |
+------------------+     |---------------------|
        |                |  +-----------------+ |
        |                |  | Id              | |
        |                |  | Nome            | |
        |                |  | Telefone        | |
        |                |  | Ativo           | |
        |                |  +-----------------+ |
        |                |     +-------------+  |
        |                |     | ConexaoPadrao|  |
+---------------+       +---------------------+
|   Views       |
|---------------|
| Index.cshtml  |
| Editar.cshtml |
| Deletar.cshtml|
+---------------+
``` 

## Estrutura do Projeto   

O projeto segue a seguinte estrutura de pastas:   

```   
ProjetoMVC/
│
├── Controllers/           # Contém os controladores para gerenciar a lógica da aplicação.
│   ├── HomeController.cs
│   └── ContatoController.cs
│
├── Models/                # Contém os modelos de dados e contexto do banco de dados.
│   ├── Contato.cs
│   └── AgendaContext.cs
│
├── Views/                 # Contém as views que representam a interface com o usuário.
│   ├── Home/
│   │   └── Index.cshtml
│   ├── Contato/
│   │   ├── Index.cshtml
│   │   ├── Editar.cshtml
│   │   └── Deletar.cshtml
│   ├── _Layout.cshtml      # Layout padrão da aplicação
│   └── _ViewImports.cshtml
│
├── wwwroot/               # Contém arquivos estáticos como CSS, JavaScript, imagens.
│   ├── css/
│   ├── js/
│   └── lib/
│
├── appsettings.json       # Configurações gerais do aplicativo.
├── appsettings.Development.json # Configurações para desenvolvimento.
├── Program.cs             # Arquivo de inicialização da aplicação.
└── ProjetoMVC.csproj      # Arquivo de projeto contendo as dependências.
```   

## Configuração e Execução   

### Pré-requisitos   

- **.NET SDK 7.0**
- **SQL Server** ou **SQL Server Express**
- **Visual Studio** ou **Visual Studio Code** com suporte para ASP.NET Core   

### Passos para Instalação:   

1. Clone o repositório:   

```   
git clone https://github.com/Gilvan-R-A/contacts-api.git
cd contacts-api
```   

2. Restaurar pacotes NuGet:   

```   
dotnet restore
```   

3. Configuração do Banco de Dados: Certifique-se de que o banco de dados está configurado corretamente no **appsettings.Development.json**:   

```   
"ConnectionStrings": {
  "ConexaoPadrao": "Server=localhost\\sqlexpress; Initial Catalog=AgendaMvc; Integrated Security=True;TrustServerCertificate=True"
}
```   

4. Criar a base de dados: Se estiver usando **Entity Framework Core**, execute as migrações para criar o banco de dados:   

```   
dotnet ef database update
```   

5. Executar o aplicativo: Execute o comando:   

```   
dotnet run
```   

Agora, acesse a aplicação em **https://localhost:5001** no navegador.   

## Funcionalidades   

- **Home Page**: Página inicial com informações sobre a aplicação.
- **Cadastro de Contatos**: Permite adicionar, editar, visualizar e excluir contatos.
- **Listagem de Contatos**: Exibe uma lista de contatos com informações como nome, telefone e status (ativo).
- **Validação de Formulários**: Validação de entrada utilizando jQuery Validation.   

## Considerações Finais   

- O projeto foi desenvolvido utilizando práticas comuns de desenvolvimento em ASP.NET Core.
- O design da interface é simples, utilizando o **Bootstrap** para garantir que o site seja responsivo.
- O projeto usa o **Entity Framework Core** para acessar o banco de dados SQL Server, com suporte a migrações para atualização do esquema.

