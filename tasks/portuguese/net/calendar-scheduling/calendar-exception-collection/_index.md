---
title: Coleção de exceções de calendário em Aspose.Tasks
linktitle: Coleção de exceções de calendário em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como lidar com exceções de calendário com eficiência em seus projetos .NET usando Aspose.Tasks, garantindo agendamento preciso e gerenciamento de recursos.
weight: 13
url: /pt/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Coleção de exceções de calendário em Aspose.Tasks

## Introdução

No gerenciamento de projetos, o agendamento preciso é vital para o sucesso. No entanto, os cenários do mundo real muitas vezes exigem desvios dos horários padrão devido a feriados, eventos especiais ou outros fatores. Aspose.Tasks for .NET fornece uma solução robusta para gerenciar tais exceções por meio de seu recurso Calendar Exception Collection. Este tutorial irá guiá-lo através do processo de utilização desta funcionalidade passo a passo.

## Pré-requisitos

Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:

1.  Aspose.Tasks for .NET: Certifique-se de ter a biblioteca instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/tasks/net/).
2. Conhecimento básico de C#: Familiaridade com a linguagem de programação C# será útil na compreensão dos exemplos.
3. Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento preferido, como Visual Studio ou JetBrains Rider.

## Importar namespaces

Antes de começar a trabalhar com Aspose.Tasks for .NET, você precisa importar os namespaces necessários para o seu projeto. Esta etapa permite acessar as classes e métodos necessários para gerenciar exceções de calendário.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Agora, vamos dividir o exemplo fornecido em várias etapas:

## Etapa 1: carregar o projeto e recuperar o calendário

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Nesta etapa, carregamos um arquivo de projeto e recuperamos o calendário desejado pelo seu UID.

## Etapa 2: limpar as exceções existentes e definir o calendário padrão

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Esta etapa limpa quaisquer exceções existentes do calendário e define-o para uma configuração padrão.

## Etapa 3: definir e adicionar exceção de horário de trabalho

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

Esta etapa define uma exceção de horário de trabalho com datas específicas de início e término, juntamente com horários de trabalho dentro dessas datas, e a adiciona ao calendário.

## Etapa 4: definir e adicionar exceções de horário de folga

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Adicione mais exceções, se necessário

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Esta etapa define exceções de horário não útil, como feriados, e as adiciona ao calendário.

## Etapa 5: exibir exceções de calendário

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

Esta etapa exibe as exceções de calendário adicionadas junto com seus detalhes.

## Etapa 6: remover todas as exceções

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Finalmente, esta etapa remove todas as exceções do calendário.

## Conclusão

Gerenciar exceções de calendário é crucial para um agendamento preciso do projeto. Aspose.Tasks for .NET simplifica essa tarefa, fornecendo um conjunto abrangente de recursos, incluindo a coleção de exceções de calendário. Seguindo as etapas descritas neste tutorial, você pode lidar com eficiência com vários cenários de agendamento em seus projetos.

## Perguntas frequentes

### P1: Posso adicionar várias exceções a um único calendário?

 A1: Sim, você pode adicionar várias exceções a um calendário usando o`AddRange` método.

### P2: Como lidar com exceções recorrentes, como feriados semanais?

A2: Você pode calcular exceções recorrentes programaticamente e adicioná-las ao calendário usando lógica personalizada.

### P3: É possível importar exceções de calendário de fontes externas?

A3: Sim, você pode ler exceções de calendário de fontes externas, como bancos de dados ou arquivos CSV, e integrá-las ao seu projeto.

### P4: O que acontece se houver exceções sobrepostas no calendário?

A4: Aspose.Tasks for .NET permite que você lide com exceções sobrepostas definindo prioridades ou resolvendo conflitos com base nos requisitos do seu projeto.

### P5: Posso personalizar os horários de trabalho de cada dia dentro de uma exceção?

R5: Sim, você pode especificar horários de trabalho personalizados para dias individuais dentro de uma exceção para acomodar necessidades específicas de agendamento.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
