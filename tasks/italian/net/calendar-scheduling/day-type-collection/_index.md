---
title: Gestione della raccolta dei tipi di giorni in Aspose.Tasks
linktitle: Gestione della raccolta dei tipi di giorni in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente le raccolte di tipi giornalieri in Aspose.Tasks per .NET. Crea, modifica e manipola facilmente le eccezioni del calendario.
type: docs
weight: 28
url: /it/net/calendar-scheduling/day-type-collection/
---
## introduzione

 Aspose.Tasks per .NET fornisce funzionalità robuste per la gestione delle raccolte di tipi di giorni, fondamentali per definire le eccezioni del calendario settimanale nelle applicazioni di gestione dei progetti. In questo tutorial esploreremo come utilizzare il file`DayTypeCollection` classe in modo efficiente. 

## Prerequisiti

Prima di procedere con il tutorial, assicurati di avere i seguenti prerequisiti:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarità con il linguaggio di programmazione C# e i concetti di .NET framework.

## Importa spazi dei nomi

Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.Tasks;
using System;


```

Ora suddividiamo l'esempio fornito in più passaggi:

## Passaggio 1: carica il progetto e accedi al calendario

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Questo passaggio inizializza una nuova istanza del progetto e recupera il calendario tramite il relativo UID.

## Passaggio 2: scorrere le eccezioni del calendario

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

Qui, iteriamo attraverso ciascuna eccezione del calendario e stampiamo il suo nome e i tipi di giorno associati.

## Passaggio 3: modifica le eccezioni del calendario

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

Questo passaggio dimostra come modificare le eccezioni del calendario aggiungendo, rimuovendo o aggiornando i tipi di giorno.

## Passaggio 4: crea e manipola nuove eccezioni del calendario

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

In questo passaggio finale creiamo nuove eccezioni di calendario e le manipoliamo aggiungendo e copiando i tipi di giorno.

## Conclusione

 In conclusione, la gestione delle raccolte di tipi di giorni in Aspose.Tasks per .NET è essenziale per definire e modificare le eccezioni del calendario settimanale nelle applicazioni di gestione dei progetti. Seguendo la guida passo passo fornita in questo tutorial, puoi utilizzare in modo efficace il`DayTypeCollection` classe per gestire varie operazioni di calendario.

## Domande frequenti

### Q1: Aspose.Tasks per .NET può essere utilizzato per creare diagrammi di Gantt a livello di codice?

A1: Sì, Aspose.Tasks per .NET fornisce API per creare e manipolare diagrammi di Gantt nelle applicazioni .NET.

### Q2: Aspose.Tasks per .NET è compatibile sia con .NET Core che con .NET Framework?

A2: Sì, Aspose.Tasks per .NET supporta sia .NET Core che .NET Framework.

### Q3: Come posso ottenere supporto per Aspose.Tasks per .NET?

 R3: Puoi ottenere supporto visitando il sito[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) dove puoi porre domande e interagire con altri utenti.

### Q4: Aspose.Tasks per .NET offre una prova gratuita?

 A4: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/).

### Q5: Posso acquistare una licenza temporanea per Aspose.Tasks per .NET?

 R5: Sì, è possibile acquistare licenze temporanee da[Sito web Aspose](https://purchase.aspose.com/temporary-license/).