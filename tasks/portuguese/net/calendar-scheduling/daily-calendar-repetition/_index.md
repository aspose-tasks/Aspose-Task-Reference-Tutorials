---
title: Repetição diária do calendário em Aspose.Tasks
linktitle: Repetição diária do calendário em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como criar tarefas recorrentes com repetições diárias de calendário em Aspose.Tasks for .NET. Aumente a eficiência do gerenciamento de projetos sem esforço.
weight: 25
url: /pt/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetição diária do calendário em Aspose.Tasks

## Introdução

 Aspose.Tasks for .NET fornece um poderoso conjunto de ferramentas para gerenciar tarefas e projetos de forma programática. Uma de suas características notáveis é a capacidade de lidar com repetições diárias do calendário com eficiência. Neste tutorial, exploraremos como utilizar o`DailyCalendarRepetition` classe junto com outras classes relevantes para criar tarefas recorrentes com repetições diárias baseadas em um calendário especificado.

## Pré-requisitos

Antes de começarmos, certifique-se de ter a seguinte configuração:

1.  Instalação: Certifique-se de ter o Aspose.Tasks for .NET instalado. Caso contrário, você pode baixá-lo em[aqui](https://releases.aspose.com/tasks/net/).

2. Importação de namespace: importe os namespaces necessários para o seu projeto:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Etapa 1: inicializar o projeto

Primeiramente, precisamos carregar um projeto existente ou criar um novo para trabalhar:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Passo 2: Defina o calendário

A seguir, criamos um calendário com duração de 24 horas e o associamos ao projeto:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Etapa 3: definir parâmetros de tarefas recorrentes

Agora, vamos definir os parâmetros para nossa tarefa recorrente. Definimos seu nome, duração, padrão de recorrência e intervalo:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Etapa 4: definir calendário para tarefas

Associe o calendário definido à tarefa:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Etapa 5: adicionar tarefa ao projeto

Adicione a tarefa com parâmetros definidos ao projeto:

```csharp
project.RootTask.Children.Add(parameters);
```

## Etapa 6: salve o projeto

Finalmente, salve o projeto com a tarefa recorrente adicionada:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Agora você criou com sucesso um projeto com uma tarefa recorrente definida para ser repetida diariamente com base em um calendário de 24 horas usando Aspose.Tasks for .NET!

## Conclusão

Neste tutorial, demonstramos como utilizar Aspose.Tasks for .NET para lidar com repetições diárias do calendário com eficiência. Seguindo essas etapas, você pode integrar perfeitamente tarefas recorrentes aos seus projetos, aumentando a produtividade e a organização.

## Perguntas frequentes

### Q1: Posso personalizar a duração de cada repetição?

A1: Sim, você pode ajustar a duração de cada repetição de acordo com suas necessidades, modificando os parâmetros no código.

### P2: É possível definir calendários diferentes para tarefas diferentes dentro do mesmo projeto?

A2: Com certeza, Aspose.Tasks permite atribuir calendários específicos a tarefas individuais, oferecendo flexibilidade no agendamento.

### Q3: O Aspose.Tasks oferece suporte a outros padrões de recorrência além dos diários?

A3: Sim, Aspose.Tasks fornece uma ampla gama de padrões de recorrência, como semanal, mensal, anual, etc., atendendo a diversas necessidades do projeto.

### Q4: Posso visualizar as tarefas recorrentes criadas usando Aspose.Tasks?

A4: Certamente, Aspose.Tasks oferece opções de visualização para ajudá-lo a analisar e rastrear tarefas recorrentes de forma eficaz.

### Q5: Existe uma versão de teste disponível para Aspose.Tasks?

 A5: Sim, você pode aproveitar uma avaliação gratuita do Aspose.Tasks em[aqui](https://releases.aspose.com/) para explorar seus recursos antes de fazer uma compra.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
