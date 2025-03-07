---
title: Ripetizione del calendario giornaliero in Aspose.Tasks
linktitle: Ripetizione del calendario giornaliero in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come creare attività ricorrenti con ripetizioni giornaliere del calendario in Aspose.Tasks per .NET. Migliora l'efficienza della gestione dei progetti senza sforzo.
weight: 25
url: /it/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ripetizione del calendario giornaliero in Aspose.Tasks

## introduzione

 Aspose.Tasks per .NET fornisce un potente set di strumenti per la gestione di attività e progetti a livello di codice. Una delle sue caratteristiche degne di nota è la capacità di gestire in modo efficiente le ripetizioni giornaliere del calendario. In questo tutorial esploreremo come utilizzare il file`DailyCalendarRepetition` classe insieme ad altre classi pertinenti per creare attività ricorrenti con ripetizioni giornaliere basate su un calendario specificato.

## Prerequisiti

Prima di iniziare, assicurati di avere la seguente configurazione:

1.  Installazione: assicurati di avere Aspose.Tasks per .NET installato. In caso contrario, puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).

2. Importazione dello spazio dei nomi: importa gli spazi dei nomi necessari nel tuo progetto:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Passaggio 1: inizializzare il progetto

Innanzitutto, dobbiamo caricare un progetto esistente o crearne uno nuovo con cui lavorare:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Passaggio 2: definire il calendario

Successivamente, creiamo un calendario con una durata di 24 ore e lo associamo al progetto:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Passaggio 3: impostare i parametri delle attività ricorrenti

Ora impostiamo i parametri per la nostra attività ricorrente. Ne definiamo il nome, la durata, il modello di ricorrenza e l'intervallo:

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

## Passaggio 4: imposta il calendario per l'attività

Associa il calendario definito all'attività:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Passaggio 5: aggiungi attività al progetto

Aggiungi l'attività con parametri definiti al progetto:

```csharp
project.RootTask.Children.Add(parameters);
```

## Passaggio 6: salva il progetto

Infine, salva il progetto con l'attività ricorrente aggiunta:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Ora hai creato con successo un progetto con un'attività ricorrente impostata per ripetersi quotidianamente in base a un calendario di 24 ore utilizzando Aspose.Tasks per .NET!

## Conclusione

In questo tutorial, abbiamo dimostrato come utilizzare Aspose.Tasks per .NET per gestire in modo efficiente le ripetizioni del calendario giornaliero. Seguendo questi passaggi, puoi integrare perfettamente le attività ricorrenti nei tuoi progetti, migliorando la produttività e l'organizzazione.

## Domande frequenti

### Q1: Posso personalizzare la durata di ogni ripetizione?

R1: Sì, puoi regolare la durata di ogni ripetizione in base alle tue esigenze modificando i parametri nel codice.

### Q2: È possibile impostare calendari diversi per attività diverse all'interno dello stesso progetto?

A2: Assolutamente, Aspose.Tasks ti consente di assegnare calendari specifici a singole attività, offrendo flessibilità nella pianificazione.

### Q3: Aspose.Tasks supporta altri modelli di ricorrenza oltre a quelli giornalieri?

A3: Sì, Aspose.Tasks fornisce un'ampia gamma di modelli di ricorrenza come settimanale, mensile, annuale, ecc., soddisfacendo le diverse esigenze del progetto.

### Q4: posso visualizzare le attività ricorrenti create utilizzando Aspose.Tasks?

A4: Certamente, Aspose.Tasks offre opzioni di visualizzazione per aiutarti ad analizzare e tenere traccia delle attività ricorrenti in modo efficace.

### Q5: È disponibile una versione di prova per Aspose.Tasks?

 A5: Sì, puoi usufruire di una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/) per esplorarne le funzionalità prima di effettuare un acquisto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
