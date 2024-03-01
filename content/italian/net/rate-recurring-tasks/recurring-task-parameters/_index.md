---
title: Impostazione dei parametri delle attività ricorrenti in Aspose.Tasks
linktitle: Impostazione dei parametri delle attività ricorrenti in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come impostare i parametri delle attività ricorrenti in Microsoft Project utilizzando Aspose.Tasks per .NET. Tutorial completo con guida passo passo.
type: docs
weight: 14
url: /it/net/rate-recurring-tasks/recurring-task-parameters/
---
## introduzione
In questo tutorial ti guideremo attraverso il processo di impostazione dei parametri delle attività ricorrenti di Microsoft Project utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Conoscenza base del linguaggio di programmazione C#.
2. Visual Studio installato o qualsiasi altro IDE C#.
3. Aspose.Tasks per la libreria .NET installata e referenziata nel tuo progetto.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo codice C#:
```csharp
using Aspose.Tasks;
using System;

```
## Passaggio 1: definire la directory dei documenti
```csharp
String DataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso della directory dei documenti.
## Passaggio 2: caricare il file di progetto
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Questa riga di codice carica il file Microsoft Project nel file`project` variabile.
## Passaggio 3: definire i parametri delle attività ricorrenti
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Qui puoi definire i parametri per l'attività ricorrente come nome dell'attività, durata, modello di ricorrenza, intervallo di ricorrenza e se ignorare il calendario delle risorse.
## Passaggio 4: imposta il calendario per le attività ricorrenti
```csharp
parameters.SetCalendar(project, "Standard");
```
Questo passaggio imposta il calendario per l'attività ricorrente. In questo esempio imposta il calendario su "Standard".
## Passaggio 5: aggiungere parametri al progetto
```csharp
project.RootTask.Children.Add(parameters);
```
Infine, aggiungi i parametri all'attività root del progetto.

## Conclusione
In questo tutorial, abbiamo dimostrato come impostare i parametri delle attività ricorrenti di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi gestire in modo efficiente le attività ricorrenti nei tuoi progetti.
## Domande frequenti
### Posso personalizzare ulteriormente il modello di ricorrenza?
Sì, Aspose.Tasks fornisce vari modelli di ricorrenza e opzioni da personalizzare in base ai requisiti del progetto.
### È disponibile una versione di prova prima dell'acquisto?
 Sì, puoi scaricare una prova gratuita da Aspose.Tasks[sito web](https://purchase.aspose.com/buy) valutare le caratteristiche della biblioteca.
### Aspose.Tasks supporta altri formati di file di progetto?
Sì, Aspose.Tasks supporta vari formati di file di progetto tra cui MPP, XML, XLSX e altri.
### Posso ottenere supporto se riscontro problemi durante l'implementazione?
Sì, puoi visitare il forum Aspose.Tasks per ricevere assistenza dalla community o contattare l'assistenza per un aiuto diretto.
### Come posso ottenere una licenza temporanea per Aspose.Tasks?
 È possibile ottenere una licenza temporanea da[sito web](https://purchase.aspose.com/temporary-license/) a scopo di test.