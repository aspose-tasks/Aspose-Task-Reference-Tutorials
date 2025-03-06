---
title: Trabalhando com períodos de disponibilidade em Aspose.Tasks
linktitle: Trabalhando com períodos de disponibilidade em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar com eficiência os períodos de disponibilidade de recursos usando Aspose.Tasks for .NET. Este tutorial fornece um guia passo a passo para trabalhar com períodos de disponibilidade em seus projetos .NET.
type: docs
weight: 17
url: /pt/net/advanced-features/working-with-availability-periods/
---
## Introdução

Neste tutorial, exploraremos como trabalhar com períodos de disponibilidade no Aspose.Tasks for .NET. Os períodos de disponibilidade são cruciais para gerenciar recursos de forma eficiente em cenários de gerenciamento de projetos. Iremos guiá-lo através do processo passo a passo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:

1. Visual Studio: Instale o Visual Studio ou qualquer outro IDE preferido para desenvolvimento .NET.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Compreensão básica da programação C#: A familiaridade com os fundamentos da linguagem de programação C# será útil.

## Importar namespaces

Antes de mergulhar no código, importe os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Vamos dividir o código de exemplo em várias etapas:

## Etapa 1: criar uma nova instância do projeto

```csharp
var project = new Project();
```

Esta linha inicializa uma nova instância da classe Project, que representa um projeto em Aspose.Tasks.

## Etapa 2: adicionar um recurso

```csharp
var resource = project.Resources.Add("Work Resource");
```

Aqui, adicionamos um novo recurso ao projeto com o nome “Recurso de Trabalho”.

## Passo 3: Definir Períodos de Disponibilidade

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Chamamos o`GetPeriods()` método para recuperar uma coleção de períodos de disponibilidade.

## Etapa 4: adicionar períodos de disponibilidade ao recurso

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Iteramos pela coleção de períodos de disponibilidade obtidos na etapa anterior e os adicionamos ao recurso.

## Etapa 5: exibir detalhes do período de disponibilidade

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Por fim, percorremos os períodos de disponibilidade associados ao recurso e imprimimos seus detalhes, incluindo data de início, data de término e unidades disponíveis.

## Conclusão

Neste tutorial, aprendemos como trabalhar com períodos de disponibilidade no Aspose.Tasks for .NET. Seguindo o guia passo a passo, você pode gerenciar com eficiência a disponibilidade de recursos em seus aplicativos de gerenciamento de projetos.

## Perguntas frequentes

### Q1: Posso usar Aspose.Tasks for .NET em projetos comerciais?

 A1: Sim, Aspose.Tasks for .NET pode ser usado em projetos comerciais. Você pode comprar uma licença[aqui](https://purchase.aspose.com/buy).

### Q2: Existe uma avaliação gratuita disponível para Aspose.Tasks for .NET?

A2: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET[aqui](https://releases.aspose.com/).

### Q3: Onde posso encontrar documentação para Aspose.Tasks for .NET?

 A3: Você pode encontrar a documentação[aqui](https://reference.aspose.com/tasks/net/).

### Q4: Como posso obter suporte para Aspose.Tasks for .NET?

 A4: Você pode obter suporte no fórum da comunidade[aqui](https://forum.aspose.com/c/tasks/15).

### Q5: Vocês oferecem licenças temporárias para Aspose.Tasks for .NET?

 A5: Sim, licenças temporárias estão disponíveis[aqui](https://purchase.aspose.com/temporary-license/).