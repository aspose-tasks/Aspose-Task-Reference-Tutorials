---
title: Ripetizione del lavoro quotidiano in Aspose.Tasks
linktitle: Ripetizione del lavoro quotidiano in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come creare attività ricorrenti quotidiane nei file Microsoft Project utilizzando Aspose.Tasks per .NET. Aumenta la produttività e l'organizzazione senza sforzo.
type: docs
weight: 26
url: /it/net/calendar-scheduling/daily-work-repetition/
---
## introduzione

Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di manipolare facilmente i file di Microsoft Project. Tra le sue miriadi di funzionalità c'è la capacità di gestire attività ricorrenti in modo efficiente. In questo tutorial approfondiremo la funzionalità Ripetizione giornaliera del lavoro, che consente la creazione di attività che si ripetono quotidianamente all'interno di un progetto.

## Prerequisiti

Prima di immergerti in questo tutorial, assicurati di avere quanto segue:

- Conoscenza base di C# e framework .NET.
- Visual Studio installato nel sistema.
-  Aspose.Tasks per la libreria .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
- Familiarità con i file Microsoft Project (.mpp).

## Importa spazi dei nomi

Prima di iniziare, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Suddividiamo l'esempio fornito in più passaggi:

## Passaggio 1: caricare il file di progetto

 Innanzitutto, carica il file di progetto utilizzando il file`Project` classe:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Passaggio 2: definire i parametri delle attività ricorrenti

Definire i parametri per l'attività ricorrente:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Passaggio 3: imposta il calendario e la data di inizio dell'attività

Imposta il calendario e la data di inizio dell'attività:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Conclusione

In questo tutorial, abbiamo esplorato come utilizzare Aspose.Tasks per .NET per creare attività ricorrenti con ripetizione del lavoro quotidiano. Seguendo questi passaggi, puoi gestire in modo efficiente le attività all'interno dei tuoi progetti, garantendo un flusso di lavoro e un'organizzazione fluidi.

## Domande frequenti

### Q1: posso personalizzare ulteriormente il modello di ricorrenza?

R1: Sì, puoi regolare parametri quali data di inizio, numero di occorrenze e intervallo di ripetizione per personalizzare lo schema di ricorrenza in base alle tue esigenze.

### Q2: Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?

A2: Sì, Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo compatibilità e integrazione perfetta.

### Q3: Come posso gestire eccezioni o modifiche alle attività ricorrenti?

A3: Aspose.Tasks fornisce funzionalità robuste per gestire eccezioni e modifiche all'interno di attività ricorrenti, consentendo flessibilità e personalizzazione.

### Q4: Posso esportare il progetto in formati diversi?

A4: Assolutamente, Aspose.Tasks offre supporto per l'esportazione di progetti in vari formati tra cui PDF, HTML, XML e altro, facilitando una facile condivisione e collaborazione.

### Q5: Aspose.Tasks offre supporto tecnico?

R5: Sì, Aspose.Tasks fornisce supporto tecnico completo attraverso il suo forum, dove puoi chiedere assistenza, condividere esperienze e interagire con altri utenti.