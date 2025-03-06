---
title: Configurações de banco de dados em Aspose.Tasks
linktitle: Configurações de banco de dados em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como importar projetos de um banco de dados Primavera usando Aspose.Tasks for .NET. Obtenha orientação passo a passo neste tutorial abrangente.
weight: 29
url: /pt/net/calendar-scheduling/database-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurações de banco de dados em Aspose.Tasks

## Introdução

Aspose.Tasks for .NET é uma biblioteca poderosa que permite aos desenvolvedores trabalhar com arquivos do Microsoft Project em seus aplicativos .NET. Neste tutorial, focaremos na importação de projetos de um banco de dados Primavera usando Aspose.Tasks.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

- Conhecimento básico da linguagem de programação C#.
- Visual Studio instalado em seu sistema.
-  Biblioteca Aspose.Tasks para .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).
- Acesso a um banco de dados Primavera, juntamente com as permissões necessárias.

## Importar namespaces

Primeiro, você precisa importar os namespaces necessários para o seu projeto C#. Esses namespaces fornecem acesso às classes e métodos necessários para trabalhar com Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Agora, vamos dividir o código de exemplo fornecido em várias etapas:

## Etapa 1: definir string de conexão

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

 Nesta etapa, definimos a string de conexão para conectar-se ao banco de dados Primavera. Certifique-se de substituir`DataDir` com o diretório onde seu arquivo de banco de dados está localizado.

## Etapa 2: criar configurações de banco de dados

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

 Aqui, criamos uma instância de`PrimaveraDbSettings` class, passando a string de conexão e o ID do projeto como parâmetros. Ajuste o ID do projeto conforme sua necessidade.

## Etapa 3: definir o nome invariável do provedor

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Especifique o nome invariável do provedor. Neste exemplo, estamos usando SQLite, mas você pode alterá-lo com base no seu provedor de banco de dados.

## Etapa 4: carregar projeto

```csharp
var project = new Project(settings);
```

 Crie um novo`Project` objeto, passando as configurações do banco de dados como parâmetro.

## Etapa 5: Salvar Projeto

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Por fim, salve o projeto no local desejado com o formato de arquivo especificado.

## Conclusão

Neste tutorial, aprendemos como importar projetos de um banco de dados Primavera usando Aspose.Tasks for .NET. Seguindo as etapas fornecidas, você pode integrar perfeitamente a funcionalidade de importação de projetos em seus aplicativos .NET.

## Perguntas frequentes

### Q1: Posso importar projetos de diferentes provedores de banco de dados usando Aspose.Tasks for .NET?

A1: Sim, você pode importar projetos de vários provedores de banco de dados ajustando a cadeia de conexão e o nome invariável do provedor de acordo.

### Q2: Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?

 A2: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar documentação para Aspose.Tasks for .NET?

 A3: Você pode encontrar a documentação[aqui](https://reference.aspose.com/tasks/net/).

### Q4: Como posso obter suporte para Aspose.Tasks for .NET?

 A4: Você pode obter suporte no fórum da comunidade Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15).

### Q5: Preciso de uma licença temporária para usar o Aspose.Tasks for .NET?

 R5: Se quiser avaliar a funcionalidade completa da biblioteca, você pode obter uma licença temporária em[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
