---
title: Ripetizione per mese, settimana, giorno in Aspose.Tasks
linktitle: Ripetizione per mese, settimana, giorno in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come impostare ripetizioni per mese, settimana e giorno in Aspose.Tasks per .NET per automatizzare le attività ricorrenti in modo efficiente.
type: docs
weight: 26
url: /it/net/advanced-features/repetition-by-month-week-day/
---
## introduzione

Nel campo dello sviluppo software, in particolare nelle applicazioni di gestione dei progetti, la capacità di gestire le attività ricorrenti in modo efficiente è fondamentale. Aspose.Tasks per .NET è una potente libreria progettata per semplificare la creazione e la gestione delle attività di progetto, comprese quelle ricorrenti. Una di queste funzionalità fornite da Aspose.Tasks è la possibilità di impostare ripetizioni per mese, settimana e giorno, garantendo che le attività vengano eseguite nei tempi previsti senza intervento manuale.

## Prerequisiti

Prima di immergerti nella complessità dell'impostazione delle ripetizioni per mese, settimana e giorno utilizzando Aspose.Tasks per .NET, assicurati di disporre dei seguenti prerequisiti:

1. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale per comprendere e implementare gli esempi di codice forniti.
   
2.  Installazione di Aspose.Tasks per .NET: assicurarsi di aver scaricato e installato la libreria Aspose.Tasks per .NET. È possibile ottenere la libreria da[pagina di download](https://releases.aspose.com/tasks/net/).

3. Accesso a un file di progetto .mpp: tieni pronto un file Microsoft Project (.mpp), poiché lo utilizzeremo per dimostrare l'implementazione delle ripetizioni per mese, settimana e giorno.

## Importa spazi dei nomi

Per iniziare a utilizzare Aspose.Tasks per .NET nella tua applicazione C#, devi importare gli spazi dei nomi necessari. Ecco come puoi farlo:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Suddividiamo lo snippet di codice fornito in più passaggi per comprendere a fondo ogni parte.

## Passaggio 1: caricare il file di progetto

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Questo passaggio prevede la creazione di una nuova istanza del file`Project` classe e caricando un file Microsoft Project esistente (`Project1.mpp`) dalla directory specificata.

## Passaggio 2: definire i parametri delle attività ricorrenti

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

In questo passaggio definiamo i parametri per un'attività ricorrente. Specifichiamo il nome dell'attività, la durata, lo schema di ripetizione (mensile) e l'intervallo di ricorrenza (termina entro una data specifica).

## Passaggio 3: aggiungi un'attività ricorrente al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

Qui aggiungiamo i parametri dell'attività ricorrente definiti all'attività root del progetto.

## Passaggio 4: salva il file di progetto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Infine, salviamo il file di progetto modificato con l'attività ricorrente aggiunta.

## Conclusione

In conclusione, impostare ripetizioni per mese, settimana e giorno in Aspose.Tasks per .NET è un processo semplice che consente agli sviluppatori di automatizzare in modo efficiente la gestione delle attività ricorrenti all'interno dei loro progetti. Seguendo i passaggi descritti in questo tutorial, puoi integrare perfettamente questa funzionalità nelle tue applicazioni C#, risparmiando tempo e fatica nella gestione dei progetti.

## Domande frequenti

###Q1: posso personalizzare il modello di ricorrenza oltre agli esempi forniti?

A1: Sì, Aspose.Tasks per .NET offre ampie opzioni di personalizzazione per i modelli di ricorrenza, consentendoti di adattarli alle tue esigenze specifiche.

###Q2: È disponibile una versione di prova per Aspose.Tasks per .NET?

 A2: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da[pagina delle uscite](https://releases.aspose.com/).

###Q3: Come posso ottenere supporto per Aspose.Tasks per .NET?

 R3: Puoi cercare assistenza e interagire con la comunità sul[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###Q4: Sono disponibili licenze temporanee per Aspose.Tasks per .NET?

 R4: Sì, puoi acquisire licenze temporanee da[pagina di acquisto](https://purchase.aspose.com/temporary-license/) a scopo di test e valutazione.

###Q5: Dove posso trovare la documentazione completa per Aspose.Tasks per .NET?

 A5: È possibile fare riferimento al dettaglio[documentazione](https://reference.aspose.com/tasks/net/) disponibile sul sito Web Aspose per una guida approfondita sull'utilizzo della libreria.