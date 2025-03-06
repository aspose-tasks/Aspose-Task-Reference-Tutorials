---
title: Personalizza le settimane lavorative in Aspose.Tasks
linktitle: Raccolta di settimane lavorative in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come personalizzare le settimane lavorative in Aspose.Tasks per .NET. Guida passo passo per creare calendari di progetto personalizzati. Scarica ora!
weight: 17
url: /it/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalizza le settimane lavorative in Aspose.Tasks

## introduzione
Benvenuti nel nostro tutorial sulla creazione di una settimana lavorativa personalizzata utilizzando Aspose.Tasks per .NET! In questa guida passo passo ti guideremo attraverso il processo di definizione di una settimana lavorativa personalizzata per un calendario nel tuo progetto. Aspose.Tasks è una potente libreria che consente agli sviluppatori di lavorare in modo efficiente con i documenti di Microsoft Project nelle loro applicazioni .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Visual Studio: assicurati di avere Visual Studio installato sul tuo computer.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarizza con le nozioni di base del linguaggio di programmazione C#.
## Importa spazi dei nomi
Nel tuo progetto C#, assicurati di importare gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Passaggio 1: crea un progetto e un calendario
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Passaggio 2: definire una settimana lavorativa personalizzata
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Passaggio 3: imposta i giorni lavorativi
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
## Passaggio 4: visualizzare le informazioni sulle settimane lavorative
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
Questa guida completa ti consente di creare e gestire in modo efficiente settimane lavorative personalizzate utilizzando Aspose.Tasks per .NET.
## Conclusione
In conclusione, Aspose.Tasks per .NET fornisce una soluzione solida per la gestione dei calendari di progetto con settimane lavorative personalizzate. Seguendo questo tutorial, hai imparato come creare e visualizzare informazioni sulle settimane lavorative personalizzate nel tuo progetto.
## Domande frequenti
### Posso avere più settimane di lavoro personalizzate in un singolo progetto?
Sì, puoi aggiungere più settimane lavorative personalizzate al calendario di un progetto.
### Come posso modificare le settimane lavorative esistenti?
 Utilizzare quello fornito`WorkWeek`proprietà e metodi per modificare le settimane lavorative esistenti.
### Aspose.Tasks è compatibile con .NET Core?
Sì, Aspose.Tasks supporta .NET Core.
### Posso esportare il progetto con settimane lavorative personalizzate nel formato file Microsoft Project?
Assolutamente sì, Aspose.Tasks ti consente di salvare il tuo progetto in vari formati, incluso Microsoft Project.
### Dove posso chiedere supporto per le domande relative ad Aspose.Tasks?
 Visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi supporto o assistenza.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
