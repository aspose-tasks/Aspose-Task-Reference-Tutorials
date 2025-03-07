---
title: Tratamento de exceções de calendário em Aspose.Tasks
linktitle: Tratamento de exceções de calendário em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como gerenciar exceções de calendário em Aspose.Tasks for .NET com tutoriais e exemplos passo a passo.
weight: 12
url: /pt/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tratamento de exceções de calendário em Aspose.Tasks

## Introdução

Neste tutorial, exploraremos como gerenciar exceções de calendário em Aspose.Tasks usando o .NET framework. As exceções de calendário permitem-nos definir datas ou períodos especiais no calendário de um projeto onde o horário normal de trabalho é alterado, como feriados ou encerramentos temporários. Abordaremos vários métodos para lidar com exceções de calendário passo a passo, usando Aspose.Tasks for .NET.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico da linguagem de programação C#.
- Visual Studio instalado em seu sistema.
- Biblioteca Aspose.Tasks for .NET adicionada ao seu projeto.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários para nosso projeto:

```csharp
using Aspose.Tasks;
using System;


```

## Etapa 1: excluir uma exceção de calendário

Para excluir uma exceção de calendário, siga estas etapas:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Exibir informações do calendário
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remova a primeira exceção
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Etapa 2: Obtendo o horário de trabalho de uma exceção de calendário

Para recuperar o horário de trabalho de uma exceção de calendário, siga estas etapas:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Exibir informações de calendário e exceções
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Obtenha o horário de trabalho e exiba detalhes
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Etapa 3: definindo exceções de calendário

Para adicionar ou remover exceções de calendário, siga estas etapas:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Crie uma nova exceção de calendário
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Definir detalhes da exceção
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Verifique se uma data é uma exceção
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Adicione a exceção ao calendário
    calendar.Exceptions.Add(exception);

    // Remova uma exceção, se existir
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Adicione uma nova exceção
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Imprimir exceções
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Conclusão

Neste artigo, cobrimos vários aspectos do tratamento de exceções de calendário no Aspose.Tasks for .NET. Seguindo as etapas fornecidas, você pode gerenciar com eficácia exceções nos cronogramas do projeto, garantindo uma representação precisa das horas de trabalho e eventos especiais.

## Perguntas frequentes

### P1: Posso adicionar várias exceções a um único calendário?

R1: Sim, você pode adicionar diversas exceções a um calendário para acomodar diversas datas ou períodos especiais.

### Q2: Como posso verificar se uma data específica é uma exceção?

 A2: Você pode usar o`CheckException()` método para verificar se uma data específica se enquadra em uma exceção.

### Q3: É possível remover uma exceção existente de um calendário?

 A3: Sim, você pode remover exceções acessando o`Exceptions` coleta do calendário e usando o`Remove()` método.

### P4: Que tipos de exceções de calendário são suportadas?

A4: Aspose.Tasks oferece suporte a vários tipos de exceções, incluindo exceções diárias, semanais, mensais e anuais, proporcionando flexibilidade na definição de regras de exceção.

### P5: Posso personalizar o horário de trabalho para datas de exceção específicas?

A5: Sim, você pode definir horários de trabalho personalizados para datas de exceção individuais usando os métodos apropriados fornecidos por Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
