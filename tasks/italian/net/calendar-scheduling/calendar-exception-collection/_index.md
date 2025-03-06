---
title: Raccolta di eccezioni del calendario in Aspose.Tasks
linktitle: Raccolta di eccezioni del calendario in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente le eccezioni del calendario nei tuoi progetti .NET utilizzando Aspose.Tasks, garantendo una pianificazione accurata e una gestione delle risorse.
type: docs
weight: 13
url: /it/net/calendar-scheduling/calendar-exception-collection/
---
## introduzione

Nella gestione dei progetti, una pianificazione precisa è vitale per il successo. Tuttavia, gli scenari del mondo reale spesso richiedono deviazioni dai programmi standard a causa di festività, eventi speciali o altri fattori. Aspose.Tasks per .NET fornisce una soluzione solida per la gestione di tali eccezioni attraverso la sua funzionalità di raccolta delle eccezioni del calendario. Questo tutorial ti guiderà passo dopo passo attraverso il processo di utilizzo di questa funzionalità.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:

1.  Aspose.Tasks per .NET: assicurati di avere la libreria installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
2. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile per comprendere gli esempi.
3. Ambiente di sviluppo: configura il tuo ambiente di sviluppo preferito, come Visual Studio o JetBrains Rider.

## Importa spazi dei nomi

Prima di iniziare a lavorare con Aspose.Tasks per .NET, è necessario importare gli spazi dei nomi richiesti nel progetto. Questo passaggio consente di accedere alle classi e ai metodi necessari per la gestione delle eccezioni del calendario.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Ora suddividiamo l'esempio fornito in più passaggi:

## Passaggio 1: carica il progetto e recupera il calendario

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

In questo passaggio carichiamo un file di progetto e recuperiamo il calendario desiderato tramite il suo UID.

## Passaggio 2: cancella le eccezioni esistenti e imposta il calendario standard

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Questo passaggio cancella eventuali eccezioni esistenti dal calendario e lo imposta su una configurazione standard.

## Passaggio 3: definire e aggiungere un'eccezione all'orario di lavoro

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

Questo passaggio definisce un'eccezione all'orario di lavoro con date di inizio e fine specifiche, insieme agli orari di lavoro all'interno di tali date, e la aggiunge al calendario.

## Passaggio 4: definire e aggiungere eccezioni all'orario non lavorativo

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Aggiungi altre eccezioni se necessario

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Questo passaggio definisce le eccezioni relative agli orari non lavorativi, come le festività, e le aggiunge al calendario.

## Passaggio 5: Visualizza le eccezioni del calendario

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

Questo passaggio visualizza le eccezioni del calendario aggiunte insieme ai relativi dettagli.

## Passaggio 6: rimuovere tutte le eccezioni

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Infine, questo passaggio rimuove tutte le eccezioni dal calendario.

## Conclusione

La gestione delle eccezioni del calendario è fondamentale per una pianificazione accurata del progetto. Aspose.Tasks per .NET semplifica questa attività fornendo un set completo di funzionalità, inclusa la raccolta delle eccezioni del calendario. Seguendo i passaggi descritti in questo tutorial, puoi gestire in modo efficiente vari scenari di pianificazione all'interno dei tuoi progetti.

## Domande frequenti

### Q1: Posso aggiungere più eccezioni a un singolo calendario?

 R1: Sì, puoi aggiungere più eccezioni a un calendario utilizzando`AddRange` metodo.

### Q2: Come posso gestire le eccezioni ricorrenti, ad esempio le festività settimanali?

A2: è possibile calcolare a livello di codice le eccezioni ricorrenti e aggiungerle al calendario utilizzando la logica personalizzata.

### Q3: È possibile importare eccezioni di calendario da origini esterne?

R3: Sì, puoi leggere le eccezioni del calendario da fonti esterne come database o file CSV e integrarle nel tuo progetto.

### D4: Cosa succede se nel calendario sono presenti eccezioni sovrapposte?

A4: Aspose.Tasks per .NET consente di gestire eccezioni sovrapposte definendo priorità o risolvendo conflitti in base ai requisiti del progetto.

### Q5: Posso personalizzare gli orari di lavoro per ogni giorno all'interno di un'eccezione?

R5: Sì, è possibile specificare orari di lavoro personalizzati per singoli giorni all'interno di un'eccezione per soddisfare esigenze di pianificazione specifiche.