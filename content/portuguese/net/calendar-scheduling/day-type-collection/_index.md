---
title: Gerenciando coleção de tipo de dia em Aspose.Tasks
linktitle: Gerenciando coleção de tipo de dia em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar coleções de tipos de dia com eficiência em Aspose.Tasks for .NET. Crie, modifique e manipule exceções de calendário com facilidade.
type: docs
weight: 28
url: /pt/net/calendar-scheduling/day-type-collection/
---
## Introdução

 Aspose.Tasks for .NET fornece funcionalidade robusta para gerenciar coleções de tipos de dias, cruciais para definir exceções de calendário semanais em aplicativos de gerenciamento de projetos. Neste tutorial, exploraremos como utilizar o`DayTypeCollection` aula de forma eficiente. 

## Pré-requisitos

Antes de prosseguirmos com o tutorial, certifique-se de ter os seguintes pré-requisitos:

1. Visual Studio: certifique-se de ter o Visual Studio instalado em seu sistema.
2.  Aspose.Tasks for .NET: Baixe e instale a biblioteca Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# e conceitos do .NET framework.

## Importar namespaces

Para começar, você precisa importar os namespaces necessários para o seu projeto C#:

```csharp
using Aspose.Tasks;
using System;


```

Agora, vamos dividir o exemplo fornecido em várias etapas:

## Etapa 1: carregar o projeto e acessar o calendário

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Esta etapa inicializa uma nova instância de projeto e recupera o calendário por seu UID.

## Etapa 2: iterar por meio de exceções de calendário

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Aqui, iteramos cada exceção de calendário e imprimimos seu nome e tipos de dias associados.

## Etapa 3: modificar exceções de calendário

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Esta etapa demonstra como modificar exceções de calendário adicionando, removendo ou atualizando tipos de dias.

## Etapa 4: criar e manipular novas exceções de calendário

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

Nesta etapa final, criamos novas exceções de calendário e as manipulamos adicionando e copiando tipos de dias.

## Conclusão

 Concluindo, o gerenciamento de coleções de tipos de dias no Aspose.Tasks for .NET é essencial para definir e modificar exceções de calendário semanais em aplicativos de gerenciamento de projetos. Seguindo o guia passo a passo fornecido neste tutorial, você pode utilizar efetivamente o`DayTypeCollection` classe para lidar com várias operações de calendário.

## Perguntas frequentes

### Q1: O Aspose.Tasks for .NET pode ser usado para criar gráficos de Gantt programaticamente?

A1: Sim, Aspose.Tasks for .NET fornece APIs para criar e manipular gráficos de Gantt em aplicativos .NET.

### P2: O Aspose.Tasks for .NET é compatível com .NET Core e .NET Framework?

A2: Sim, Aspose.Tasks for .NET oferece suporte a .NET Core e .NET Framework.

### Q3: Como posso obter suporte para Aspose.Tasks for .NET?

 A3: Você pode obter suporte visitando o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) onde você pode fazer perguntas e interagir com outros usuários.

### Q4: O Aspose.Tasks for .NET oferece uma avaliação gratuita?

 A4: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks for .NET em[aqui](https://releases.aspose.com/).

### Q5: Posso adquirir uma licença temporária para Aspose.Tasks for .NET?

 R5: Sim, licenças temporárias estão disponíveis para compra no[Aspor site](https://purchase.aspose.com/temporary-license/).