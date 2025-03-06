---
title: Ripetizione per mese giorno in Aspose.Tasks
linktitle: Ripetizione per mese giorno in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le attività ricorrenti nei progetti .NET con Aspose.Tasks. Guida passo passo per gestire la ripetizione per mese e giorno.
weight: 25
url: /it/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ripetizione per mese giorno in Aspose.Tasks

## introduzione

Nel regno dello sviluppo .NET, Aspose.Tasks rappresenta un potente strumento per la gestione delle attività e delle pianificazioni del progetto. Offre una vasta gamma di funzionalità per semplificare i flussi di lavoro di gestione dei progetti, inclusa la gestione delle attività ricorrenti. La ripetizione per mese e giorno è un requisito comune nella pianificazione del progetto e Aspose.Tasks fornisce un solido supporto per questo scenario.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:

1. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# è necessaria per comprendere i concetti discussi in questo tutorial.
2. Installazione di Aspose.Tasks per .NET: assicurati di aver installato Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
3. Ambiente di sviluppo integrato (IDE): avere un IDE come Visual Studio installato sul sistema per comodità di codifica.

## Importa spazi dei nomi

Nel tuo progetto C#, importa gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Analizziamo l'esempio di codice fornito in un formato di guida passo passo:

## Passaggio 1: caricare il file di progetto

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Questa riga di codice inizializza una nuova istanza di`Project` class, caricando il file di progetto denominato "Project1.mpp".

## Passaggio 2: definire i parametri delle attività ricorrenti

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

Questa sezione definisce i parametri per l'attività ricorrente, inclusi nome, durata, modello di ripetizione e intervallo di ricorrenza.

## Passaggio 3: aggiungi attività al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

Qui aggiungiamo i parametri dell'attività ricorrente al progetto.

## Passaggio 4: salva il file di progetto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Infine, il progetto modificato viene salvato con l'attività ricorrente aggiunta.

## Conclusione

In questo tutorial, abbiamo esplorato come gestire la ripetizione per mese e giorno in Aspose.Tasks per .NET. Seguendo i passaggi forniti, puoi gestire in modo efficiente le attività ricorrenti all'interno delle pianificazioni del tuo progetto.

## Domande frequenti

### Q1: Aspose.Tasks è compatibile con tutte le versioni di .NET?

A1: Aspose.Tasks supporta varie versioni del framework .NET, garantendo la compatibilità tra ambienti diversi.

### Q2: Posso personalizzare ulteriormente il modello di ricorrenza?

A2: Sì, Aspose.Tasks offre ampie opzioni di personalizzazione per definire modelli di ricorrenza in base ai requisiti specifici del progetto.

### Q3: Aspose.Tasks fornisce supporto per altre funzionalità di gestione del progetto?

A3: Assolutamente, Aspose.Tasks offre un'ampia gamma di funzionalità per la gestione dei progetti, tra cui il monitoraggio delle attività, l'allocazione delle risorse e la generazione di diagrammi di Gantt.

### Q4: È disponibile una versione di prova per Aspose.Tasks?

 R4: Sì, puoi usufruire di una prova gratuita da[Qui](https://releases.aspose.com/) per esplorare le capacità di Aspose.Tasks prima di prendere una decisione di acquisto.

### Q5: Dove posso chiedere assistenza se riscontro problemi o ho domande?

 A5: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per cercare supporto dalla comunità o dal team Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
