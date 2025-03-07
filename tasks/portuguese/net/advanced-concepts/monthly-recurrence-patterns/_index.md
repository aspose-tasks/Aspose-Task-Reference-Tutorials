---
title: Lidando com padrões de recorrência mensal em Aspose.Tasks
linktitle: Lidando com padrões de recorrência mensal em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com padrões de recorrência mensal em Aspose.Tasks for .NET com este tutorial passo a passo.
weight: 18
url: /pt/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lidando com padrões de recorrência mensal em Aspose.Tasks

## Introdução

Aspose.Tasks for .NET é uma API poderosa que permite aos desenvolvedores manipular arquivos do Microsoft Project programaticamente. Uma das funcionalidades essenciais que oferece é a capacidade de lidar com tarefas recorrentes de forma eficiente. Neste tutorial, vamos nos aprofundar em como trabalhar com padrões de recorrência mensal usando Aspose.Tasks, passo a passo.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos instalados:

## Importar namespaces

Primeiro, certifique-se de ter importado os namespaces necessários em seu projeto .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Agora, vamos dividir o processo de tratamento dos padrões de recorrência mensal em várias etapas:

## Etapa 1: inicializar o projeto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Etapa 2: definir parâmetros de tarefas recorrentes

Defina os parâmetros da tarefa recorrente, incluindo o nome da tarefa, a duração e o padrão de recorrência:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Etapa 3: adicionar parâmetros ao projeto

```csharp
project.RootTask.Children.Add(parameters);
```

## Etapa 4: salve o projeto

Salve o projeto modificado com a tarefa recorrente:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Conclusão

Lidar com padrões de recorrência mensal no Aspose.Tasks for .NET é simples e eficiente. Seguindo as etapas descritas neste tutorial, você pode criar facilmente tarefas recorrentes com intervalos mensais e intervalos de recorrência específicos.

## Perguntas frequentes

### Q1: O Aspose.Tasks é compatível com todas as versões de arquivos do Microsoft Project?

A1: Aspose.Tasks oferece suporte a várias versões de arquivos do Microsoft Project, incluindo MPP, MPT, XML e MPX.

### P2: Posso personalizar ainda mais o padrão de recorrência?

A2: Sim, Aspose.Tasks oferece amplas opções para personalizar padrões de recorrência, incluindo diário, semanal, mensal e anual.

### Q3: Existe uma avaliação gratuita disponível para Aspose.Tasks?

 A3: Sim, você pode obter uma avaliação gratuita do Aspose.Tasks no site[aqui](https://releases.aspose.com/).

### Q4: Como posso obter suporte para Aspose.Tasks?

 A4: Você pode procurar assistência e participar de discussões sobre o[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Onde posso comprar uma licença para Aspose.Tasks?

 A5: Você pode adquirir uma licença para Aspose.Tasks no site[aqui](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
