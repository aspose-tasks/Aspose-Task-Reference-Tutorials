---
date: 2026-03-14
description: Aprenda a especificar o esquema de banco de dados para um banco de dados
  Microsoft Project usando Aspose.Tasks e como importar dados de projetos para aplicações
  .NET.
linktitle: Specify database schema for Project DB with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Especifique o esquema de banco de dados para o Project DB com Aspose.Tasks
url: /pt/net/advanced-concepts/msp-database-settings/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurações para Banco de Dados do Microsoft Project no Aspose.Tasks

## Introdução

Se você está trabalhando com bancos de dados do Microsoft Project em suas aplicações .NET usando Aspose.Tasks, precisará **especificar o esquema do banco de dados** e configurar as definições necessárias para **importar o projeto** de forma contínua. Este tutorial guiará você passo a passo, mostrando **como configurar os detalhes da conexão**, **criar a string de conexão .NET** e, finalmente, **salvar o projeto como MPP**.

## Respostas Rápidas
- **Qual é o objetivo principal?** Especificar o esquema do banco de dados e importar um banco de dados Project para um aplicativo .NET.  
- **Qual biblioteca é necessária?** Aspose.Tasks para .NET.  
- **Como me conecto ao Project Server?** Construindo uma string de conexão SQL adequada e usando `MspDbSettings`.  
- **Qual formato de arquivo é gerado?** Um arquivo MPP salvo com `SaveFileFormat.Mpp`.  
- **Posso alterar o nome do esquema?** Sim, defina a propriedade `Schema` em `MspDbSettings`.

## Como especificar o esquema de banco de dados para o Project DB

Entender por que você pode precisar **especificar o esquema do banco de dados** é essencial. Em muitos ambientes corporativos, o banco de dados do Project Server reside sob um esquema personalizado (por exemplo, `dbo`, `psdata`). Ao definir explicitamente o esquema, você garante que o Aspose.Tasks consulte as tabelas corretas, evitando erros em tempo de execução e assegurando a importação precisa dos dados.

## Pré-requisitos

Antes de começar, certifique‑se de que você possui o seguinte:

1. Aspose.Tasks para .NET: Baixe e instale a biblioteca Aspose.Tasks a partir de [aqui](https://releases.aspose.com/tasks/net/).  
2. Acesso a um Banco de Dados Microsoft Project: Você deve ter acesso a um banco de dados Microsoft Project para importar os dados.

## Importar Namespaces

Primeiro, assegure‑se de importar os namespaces necessários ao seu projeto:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Etapa 1: Criar String de Conexão

Construa a string de conexão para o seu banco de dados Microsoft Project. É aqui que você **cria a string de conexão .NET** e também define como **conectar ao Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Dica:** Verifique novamente os valores de `DataSource` e `InitialCatalog`; eles devem corresponder ao endereço do seu servidor e ao nome do banco de dados publicado.

## Etapa 2: Configurar MspDbSettings

Crie uma instância de `MspDbSettings`, passe a string de conexão e **especifique o esquema do banco de dados** definindo a propriedade `Schema`. Isso informa ao Aspose.Tasks qual esquema consultar.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Aqui também fornecemos o GUID do projeto que identifica o projeto específico que você deseja carregar.

## Etapa 3: Carregar Dados do Projeto

Instancie um objeto `Project` usando as configurações configuradas. Esta etapa efetivamente **importa os dados do projeto** do banco de dados para um objeto .NET.

```csharp
var project = new Project(settings);
```

## Etapa 4: Salvar Dados do Projeto

Por fim, persista o projeto carregado em um arquivo MPP no disco. Isso demonstra **salvar o projeto como MPP** usando a API Aspose.Tasks.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

Após executar o código, você encontrará o arquivo `ImportProjectDataFromDatabase_out.mpp` no diretório de saída, pronto para ser aberto no Microsoft Project.

## Conclusão

Neste tutorial, você aprendeu como **especificar o esquema do banco de dados** para um banco de dados Microsoft Project, **configurar a conexão**, **importar o projeto** e **salvar o projeto como MPP** usando Aspose.Tasks para .NET. Essas etapas permitem a integração contínua dos dados do Project Server em suas aplicações personalizadas, ajudando a construir soluções robustas de gerenciamento de projetos.

## Perguntas Frequentes

### Q1: Posso usar Aspose.Tasks com diferentes versões de bancos de dados Microsoft Project?
A1: Sim, o Aspose.Tasks suporta várias versões de bancos de dados Microsoft Project, oferecendo flexibilidade na integração.

### Q2: Como posso solucionar problemas de conexão com o banco de dados?
A2: Certifique‑se de que sua string de conexão está configurada corretamente com as credenciais e detalhes do banco de dados apropriados. Você também pode consultar a documentação ou buscar suporte no [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: Existe uma versão de avaliação disponível para Aspose.Tasks?
A3: Sim, você pode acessar uma versão de avaliação gratuita a partir de [aqui](https://releases.aspose.com/).

### Q4: Posso personalizar o esquema para a interação com o banco de dados?
A4: Sim, você pode especificar o esquema para o objeto `MspDbSettings` de acordo com a estrutura do seu banco de dados.

### Q5: Onde encontro documentação mais detalhada sobre o uso do Aspose.Tasks?
A5: Você pode explorar a documentação completa [aqui](https://reference.aspose.com/tasks/net/) para obter insights detalhados sobre as funcionalidades do Aspose.Tasks.

**Q: Essa abordagem funciona com bancos de dados Azure SQL?**  
A: Absolutamente. Basta ajustar o `DataSource` para o nome do seu servidor Azure e garantir que as configurações TLS/SSL estejam habilitadas.

**Q: Como lidar com bancos de dados Project grandes sem timeout?**  
A: Aumente o valor de `ConnectTimeout` na string de conexão e considere carregar os projetos em lotes, se necessário.

---

**Última atualização:** 2026-03-14  
**Testado com:** Aspose.Tasks 24.12 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}