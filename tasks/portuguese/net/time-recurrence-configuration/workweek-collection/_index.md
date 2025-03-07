---
title: Personalize semanas de trabalho em Aspose.Tasks
linktitle: Coleção de semanas de trabalho em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Aprenda como personalizar semanas de trabalho em Aspose.Tasks for .NET. Guia passo a passo para criar calendários de projetos personalizados. Baixe Agora!
weight: 17
url: /pt/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalize semanas de trabalho em Aspose.Tasks

## Introdução
Bem-vindo ao nosso tutorial sobre como criar uma semana de trabalho personalizada usando Aspose.Tasks for .NET! Neste guia passo a passo, orientaremos você no processo de definição de uma semana de trabalho personalizada para um calendário em seu projeto. Aspose.Tasks é uma biblioteca poderosa que permite aos desenvolvedores trabalhar de forma eficiente com documentos do Microsoft Project em seus aplicativos .NET.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
1. Visual Studio: certifique-se de ter o Visual Studio instalado em sua máquina.
2.  Aspose.Tasks para .NET: Baixe e instale a biblioteca Aspose.Tasks. Você pode encontrar o link para download[aqui](https://releases.aspose.com/tasks/net/).
3. Conhecimento básico de C#: Familiarize-se com os fundamentos da linguagem de programação C#.
## Importar namespaces
No seu projeto C#, certifique-se de importar os namespaces necessários:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Etapa 1: crie um projeto e um calendário
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Etapa 2: definir uma semana de trabalho personalizada
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Etapa 3: definir dias úteis
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Etapa 4: exibir informações sobre semanas de trabalho
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Este guia abrangente permite que você crie e gerencie com eficiência semanas de trabalho personalizadas usando Aspose.Tasks for .NET.
## Conclusão
Concluindo, Aspose.Tasks for .NET fornece uma solução robusta para lidar com calendários de projetos com semanas de trabalho personalizadas. Seguindo este tutorial, você aprendeu como criar e exibir informações sobre semanas de trabalho personalizadas em seu projeto.
## Perguntas frequentes
### Posso ter várias semanas de trabalho personalizadas em um único projeto?
Sim, você pode adicionar várias semanas de trabalho personalizadas a um calendário de projeto.
### Como posso modificar semanas de trabalho existentes?
 Use o fornecido`WorkWeek`propriedades e métodos para modificar semanas de trabalho existentes.
### O Aspose.Tasks é compatível com .NET Core?
Sim, Aspose.Tasks suporta .NET Core.
### Posso exportar o projeto com semanas de trabalho personalizadas para o formato de arquivo do Microsoft Project?
Com certeza, Aspose.Tasks permite salvar seu projeto em vários formatos, incluindo Microsoft Project.
### Onde posso buscar suporte para consultas relacionadas ao Aspose.Tasks?
 Visite a[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) para qualquer apoio ou assistência.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
