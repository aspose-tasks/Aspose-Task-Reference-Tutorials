---
title: Trabalhando com calendário em Aspose.Tasks
linktitle: Trabalhando com calendário em Aspose.Tasks
second_title: API Aspose.Tasks .NET
description: Gerencie calendários de projetos, calcule durações e lide com exceções com facilidade usando Aspose.Tasks for .NET.
weight: 10
url: /pt/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trabalhando com calendário em Aspose.Tasks

## Introdução

Aspose.Tasks for .NET fornece recursos poderosos para trabalhar com calendários, permitindo que os desenvolvedores gerenciem com eficiência cronogramas de projetos e alocações de recursos. Neste tutorial, exploraremos como utilizar Aspose.Tasks para interagir com calendários, cobrindo operações essenciais como recuperação de informações de calendário, definição de semanas de trabalho, cálculo de horas de trabalho e muito mais.

## Pré-requisitos

Antes de começarmos, certifique-se de ter os seguintes pré-requisitos configurados:

- Compreensão básica da linguagem de programação C#.
-  Instalação do Aspose.Tasks para .NET. Se não estiver instalado, baixe-o em[aqui](https://releases.aspose.com/tasks/net/).
- Familiaridade com Visual Studio ou qualquer outro ambiente de desenvolvimento .NET preferido.

## Importar namespaces

Antes de começar a codificar, importe os namespaces necessários:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Agora, vamos dividir cada exemplo em várias etapas em um formato de guia passo a passo:

## Etapa 1: recuperar informações do calendário

Para recuperar informações de calendário de um projeto, siga estas etapas:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Recuperar informações de calendários
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Itere em cada calendário do projeto.
- Imprima o UID e o nome de cada calendário.

## Etapa 2: leia as informações das semanas de trabalho

Para ler as informações das semanas de trabalho em um calendário, siga estas etapas:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Itere em cada semana de trabalho no calendário.
- Imprima o nome, a data de início e a data de término de cada semana de trabalho.
- Percorra os dias e horários de trabalho de cada semana.

## Etapa 3: leia as propriedades do calendário

Para ler as propriedades dos calendários do projeto, siga estas etapas:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Itere em cada calendário do projeto.
- Imprima UID, nome e se é um calendário base.
- Imprima o horário de trabalho para cada tipo de dia.

## Etapa 4: calcular horas de trabalho

Para calcular as horas de trabalho para uma tarefa, siga estas etapas:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha detalhes da tarefa, como calendário, data de início e data de término.
- Calcule as horas de trabalho iterando cada dia e verificando se é um dia útil.
- Some a duração total em minutos.

## Etapa 5: definir dias da semana para o calendário

Para definir dias da semana para um calendário, siga estas etapas:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Explicação:
- Crie um novo projeto e calendário.
- Adicione dias úteis padrão (de segunda a quinta) e horários de trabalho personalizados para sexta-feira.
- Defina sábado e domingo como dias não úteis.

## Etapa 6: gravar dados atualizados do calendário no MPP

Para gravar dados de calendário atualizados em um arquivo MPP, siga estas etapas:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://buy.aspose.com/temporary-license/).");
    }
}
```

Explicação:
- Carregue o arquivo do projeto e recupere o calendário padrão.
- Modifique dados do calendário, como exceções e horários de trabalho.
- Salve o projeto atualizado com os dados do calendário modificados.

## Etapa 7: calcular a data de término da tarefa dividida

Para calcular a data de término de uma tarefa dividida, siga estas etapas:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Explicação:
- Carregue o arquivo do projeto e recupere a tarefa dividida.
- Obtenha o calendário do projeto.
- Calcule a data de término com base em uma duração personalizada.

## Etapa 8: recuperar exceções de calendário

Para recuperar informações sobre exceções de calendário, siga estas etapas:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Itere em cada calendário e suas exceções.
- Imprima as datas de início e término de cada exceção.

## Etapa 9: Obtenha o calendário de recursos básicos

Para trabalhar com o calendário base do calendário de um recurso, siga estas etapas:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Adicione um recurso e seu calendário.
- Imprima o nome do calendário base para todos os recursos.

## Etapa 10: excluir calendário

Para excluir um calendário de um projeto, siga estas etapas:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por nome.
- Exclua o calendário.

## Etapa 11: Obtenha a data de término por início e trabalho

Para calcular uma data de término por data de início e trabalho, siga estas etapas:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário padrão.
- Defina uma data de início e duração do trabalho.
- Calcule a data de término com base na data de início e no trabalho.

## Etapa 12: comece no próximo dia útil

Para começar o próximo dia útil usando um calendário, siga estas etapas:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Obtenha o horário de início do próximo dia útil.

## Etapa 13: obter o final do dia útil anterior

Para obter o final do dia útil anterior usando um calendário, siga estas etapas:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Obtenha o horário de término do dia útil anterior.

## Etapa 14: Obtenha a data de início, término e duração

Para obter uma data de início por data de término e duração, siga estas etapas:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Calcule a data de início a partir da data de término e duração.

## Etapa 15: Obtenha o horário de trabalho

Para obter o horário de trabalho para uma data específica, siga estas etapas:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Obtenha o horário de trabalho para a data especificada.

## Etapa 16: obtenha horários de trabalho

Para obter os horários de trabalho para uma data específica, siga estas etapas:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Explicação:
- Carregue o arquivo do projeto.
- Obtenha o calendário por UID.
- Obtenha os horários de trabalho para a data especificada.

## Conclusão

Trabalhar com calendários no Aspose.Tasks for .NET é crucial para gerenciar cronogramas de projetos de maneira eficaz. Com os exemplos fornecidos e guias passo a passo, você pode manipular facilmente os dados do calendário, calcular durações de tarefas e lidar com exceções com eficiência. Ao integrar essas funcionalidades em seus aplicativos, você pode agilizar os processos de gerenciamento de projetos e garantir um agendamento preciso.

## Perguntas frequentes

### Q1: Preciso de uma licença para usar Aspose.Tasks for .NET?

 A1: Sim, você precisa de uma licença válida para utilizar Aspose.Tasks for .NET em seus aplicativos. Você pode comprar uma licença completa ou obter uma licença temporária de 30 dias em[aqui](https://purchase.aspose.com/temporary-license/).

### P2: Posso modificar exceções de calendário programaticamente?

A2: Sim, você pode adicionar, atualizar ou excluir programaticamente exceções de calendário usando Aspose.Tasks para APIs .NET.

### P3: Como posso calcular as datas de término das tarefas com durações personalizadas?

 A3: Aspose.Tasks for .NET fornece métodos como`GetTaskFinishDateFromDuration()` para calcular datas de término de tarefas com base em durações personalizadas.

### Q4: É possível criar calendários personalizados, como calendários noturnos?

A4: Sim, você pode criar calendários personalizados, como calendários do turno da noite, usando Aspose.Tasks para APIs .NET.

### P5: Posso recuperar informações sobre exceções de calendário de arquivos de projeto?

A5: Sim, você pode recuperar facilmente informações sobre exceções de calendário de arquivos de projeto usando Aspose.Tasks for .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
