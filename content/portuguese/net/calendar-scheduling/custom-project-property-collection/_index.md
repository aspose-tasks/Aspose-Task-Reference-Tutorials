---
title: Gerenciando coleção de propriedades de projeto personalizado em Aspose.Tasks
linktitle: Gerenciando coleção de propriedades de projeto personalizado em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar com eficácia propriedades personalizadas do projeto no Aspose.Tasks for .NET, aprimorando sua experiência de gerenciamento de projetos.
type: docs
weight: 24
url: /pt/net/calendar-scheduling/custom-project-property-collection/
---
## Introdução

Você está pronto para aprimorar sua experiência de gerenciamento de projetos com Aspose.Tasks for .NET? O gerenciamento de propriedades personalizadas do projeto é um aspecto crucial do gerenciamento de projetos, permitindo adicionar metadados específicos adaptados aos requisitos do seu projeto. Neste tutorial, veremos como você pode trabalhar efetivamente com coleções de propriedades de projetos personalizados usando Aspose.Tasks for .NET.

## Pré-requisitos

Antes de prosseguirmos, certifique-se de ter os seguintes pré-requisitos configurados:

1. Ambiente Visual Studio: Tenha o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale Aspose.Tasks for .NET do[Link para Download](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.

## Importar namespaces

Comece importando os namespaces necessários para trabalhar com Aspose.Tasks for .NET:

```csharp
using Aspose.Tasks;
using System;


```

Vamos dividir o código de exemplo em várias etapas para uma compreensão abrangente:

## Etapa 1: inicializar o projeto

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Esta etapa inicializa um novo projeto usando Aspose.Tasks.

## Etapa 2: verificar a prontidão da coleta de propriedades personalizadas

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Este código verifica se a coleção de propriedades customizadas é somente leitura.

## Etapa 3: adicionar propriedades personalizadas

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Aqui, adicionamos propriedades personalizadas ao projeto, suportando os tipos Boolean, DateTime, Double e String.

## Etapa 4: acessar propriedades personalizadas

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Este loop nos permite iterar através de propriedades personalizadas e exibir seu tipo, nome e valor.

## Etapa 5: recuperar um valor de propriedade personalizada

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Este código recupera o valor de uma propriedade customizada específica chamada "Nome Personalizado".

## Etapa 6: Iterar sobre nomes de propriedades personalizadas

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Aqui, iteramos os nomes das propriedades personalizadas e as exibimos.

## Etapa 7: remover ou limpar propriedades personalizadas

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Você pode remover uma propriedade customizada específica por seu nome ou limpar toda a coleção.

## Conclusão

Dominar coleções de propriedades de projeto personalizadas em Aspose.Tasks for .NET permite que você gerencie metadados de projeto com eficiência. Seguindo este guia passo a passo, você pode integrar perfeitamente propriedades personalizadas ao seu fluxo de trabalho de gerenciamento de projetos, melhorando a organização e a eficiência.

## Perguntas frequentes

### Q1: Posso adicionar propriedades personalizadas de qualquer tipo de dados ao meu projeto usando Aspose.Tasks for .NET?

A1: Sim, você pode adicionar propriedades personalizadas com suporte aos tipos Boolean, DateTime, Double e String.

### Q2: É possível iterar nomes de propriedades personalizadas em Aspose.Tasks for .NET?

 A2: Com certeza, você pode iterar nomes de propriedades personalizadas usando o`Names` propriedade.

### P3: Como posso remover uma propriedade personalizada específica do meu projeto?

 A3: Você pode remover uma propriedade personalizada pelo seu nome usando o`Remove` método.

### P4: O Aspose.Tasks for .NET fornece suporte para licenças temporárias?

A4: Sim, você pode obter uma licença temporária no site Aspose para fins de avaliação.

### P5: Onde posso encontrar suporte ou assistência adicional em relação ao Aspose.Tasks for .NET?

 A5: Você pode visitar o fórum Aspose.Tasks[aqui](https://forum.aspose.com/c/tasks/15) para qualquer dúvida ou assistência.