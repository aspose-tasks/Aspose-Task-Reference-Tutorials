---
title: Gestione dei modelli di ricorrenza mensile in Aspose.Tasks
linktitle: Gestione dei modelli di ricorrenza mensile in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire i modelli di ricorrenza mensile in Aspose.Tasks per .NET con questo tutorial passo passo.
type: docs
weight: 18
url: /it/net/advanced-concepts/monthly-recurrence-patterns/
---
## introduzione

Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice. Una delle funzionalità essenziali che offre è la capacità di gestire le attività ricorrenti in modo efficiente. In questo tutorial, approfondiremo come lavorare con modelli di ricorrenza mensile utilizzando Aspose.Tasks, passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere installati i seguenti prerequisiti:

## Importa spazi dei nomi

Innanzitutto, assicurati di aver importato gli spazi dei nomi necessari nel tuo progetto .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Ora suddividiamo il processo di gestione dei modelli di ricorrenza mensile in più passaggi:

## Passaggio 1: inizializzare il progetto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Passaggio 2: impostare i parametri delle attività ricorrenti

Definire i parametri per l'attività ricorrente, inclusi il nome dell'attività, la durata e il modello di ricorrenza:

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

## Passaggio 3: aggiungere parametri al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

## Passaggio 4: salva il progetto

Salva il progetto modificato con l'attività ricorrente:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Conclusione

La gestione dei modelli di ricorrenza mensile in Aspose.Tasks per .NET è semplice ed efficiente. Seguendo i passaggi descritti in questo tutorial, puoi creare facilmente attività ricorrenti con intervalli mensili e intervalli di ricorrenza specifici.

## Domande frequenti

### Q1: Aspose.Tasks è compatibile con tutte le versioni dei file Microsoft Project?

R1: Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi MPP, MPT, XML e MPX.

### Q2: Posso personalizzare ulteriormente il modello di ricorrenza?

A2: Sì, Aspose.Tasks offre ampie opzioni per personalizzare i modelli di ricorrenza, inclusi giornalieri, settimanali, mensili e annuali.

### Q3: È disponibile una prova gratuita per Aspose.Tasks?

 R3: Sì, puoi ottenere una prova gratuita di Aspose.Tasks dal sito web[Qui](https://releases.aspose.com/).

### Q4: Come posso ottenere supporto per Aspose.Tasks?

 R4: Puoi chiedere assistenza e partecipare alle discussioni su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Dove posso acquistare una licenza per Aspose.Tasks?

 R5: È possibile acquistare una licenza per Aspose.Tasks dal sito Web[Qui](https://purchase.aspose.com/buy)