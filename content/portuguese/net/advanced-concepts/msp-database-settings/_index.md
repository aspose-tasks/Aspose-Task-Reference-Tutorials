---
title: Configurações para banco de dados do Microsoft Project em Aspose.Tasks
linktitle: Configurações para banco de dados do Microsoft Project em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como definir as configurações do banco de dados do Microsoft Project usando Aspose.Tasks para integração perfeita em aplicativos .NET.
type: docs
weight: 19
url: /pt/net/advanced-concepts/msp-database-settings/
---
## Introdução

Se estiver trabalhando com bancos de dados do Microsoft Project em seus aplicativos .NET usando Aspose.Tasks, você precisará definir as configurações necessárias para importar os dados do projeto sem problemas. Este tutorial irá guiá-lo através do processo passo a passo.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1.  Aspose.Tasks para .NET: Baixe e instale a biblioteca Aspose.Tasks em[aqui](https://releases.aspose.com/tasks/net/).
2. Acesso a um banco de dados do Microsoft Project: você deve ter acesso a um banco de dados do Microsoft Project para importar dados.

## Importar namespaces

Primeiro, certifique-se de importar os namespaces necessários para o seu projeto:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Etapa 1: criar string de conexão

Construa a cadeia de conexão para o banco de dados do Microsoft Project. Aqui está um exemplo:

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

Certifique-se de substituir os valores do espaço reservado pelas credenciais reais do banco de dados.

## Etapa 2: configurar MspDbSettings

 Crie uma instância de`MspDbSettings` e especifique a string de conexão junto com o GUID do projeto:

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

## Etapa 3: carregar os dados do projeto

 Instanciar um`Project` objeto usando as configurações definidas:

```csharp
var project = new Project(settings);
```

## Etapa 4: salvar os dados do projeto

Salve os dados do projeto carregado em um arquivo:

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

## Conclusão

Neste tutorial, você aprendeu como definir configurações para acessar bancos de dados do Microsoft Project usando Aspose.Tasks for .NET. Seguindo essas etapas, você pode importar dados do projeto de maneira transparente para seus aplicativos, facilitando o gerenciamento eficiente do projeto.

## Perguntas frequentes

### Q1: Posso usar Aspose.Tasks com diferentes versões de bancos de dados do Microsoft Project?

A1: Sim, Aspose.Tasks oferece suporte a várias versões de bancos de dados do Microsoft Project, permitindo flexibilidade na integração.

### P2: Como posso solucionar problemas de conexão com o banco de dados?

A2: Certifique-se de que sua cadeia de conexão esteja configurada corretamente com as credenciais e detalhes do banco de dados apropriados. Você também pode consultar a documentação ou buscar suporte do[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q3: Existe uma versão de teste disponível para Aspose.Tasks?

 A3: Sim, você pode acessar uma versão de avaliação gratuita em[aqui](https://releases.aspose.com/).

### P4: Posso personalizar o esquema para interação com o banco de dados?

 A4: Sim, você pode especificar o esquema para o`MspDbSettings` objeto de acordo com a estrutura do seu banco de dados.

### Q5: Onde posso encontrar documentação mais detalhada sobre o uso do Aspose.Tasks?

 A5: Você pode explorar a documentação abrangente[aqui](https://reference.aspose.com/tasks/net/) para obter informações detalhadas sobre as funcionalidades do Aspose.Tasks.