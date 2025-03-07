---
title: Ripetizione per giorno dell'anno in Aspose.Tasks
linktitle: Ripetizione per giorno dell'anno in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le ripetizioni dei giorni dell'anno in Aspose.Tasks per .NET per semplificare in modo efficiente la gestione delle attività ricorrenti.
weight: 27
url: /it/net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ripetizione per giorno dell'anno in Aspose.Tasks

## introduzione

Nell'ambito della gestione dei progetti, la pianificazione efficiente delle attività e la ricorrenza svolgono un ruolo fondamentale nel garantire un'esecuzione tempestiva e un flusso di lavoro regolare. Aspose.Tasks per .NET offre una soluzione solida per gli sviluppatori per gestire attività ricorrenti senza sforzo all'interno delle loro applicazioni. In questo tutorial, approfondiamo le complessità del lavoro con le ripetizioni dei giorni dell'anno utilizzando Aspose.Tasks, fornendo una guida completa per la creazione di attività ricorrenti basate su modelli annuali.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Tasks for .NET Library: Scarica e installa la libreria Aspose.Tasks for .NET dal[sito web](https://releases.aspose.com/tasks/net/).
   
2. Ambiente di sviluppo: configura un ambiente di sviluppo adatto con Visual Studio o qualsiasi altro IDE preferito per lo sviluppo .NET.

3. Conoscenza di base di C#: acquisisci familiarità con i fondamenti del linguaggio di programmazione C# da seguire insieme agli esempi di codice.

4. Concetti di gestione del progetto: la comprensione dei concetti di gestione del progetto e della pianificazione delle attività aiuterà a comprendere in modo efficace i concetti del tutorial.

## Importa spazi dei nomi

Prima di iniziare a scrivere codice, importiamo gli spazi dei nomi necessari per facilitare la manipolazione delle attività utilizzando Aspose.Tasks per .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Ora suddividiamo l'esempio fornito in più passaggi e chiariamo ogni passaggio in dettaglio.

## Passaggio 1: caricare il file di progetto

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Qui inizializziamo un nuovo file`Project` oggetto e caricare un file di progetto esistente denominato "Project1.mpp".

## Passaggio 2: definire i parametri delle attività ricorrenti

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

 In questo passaggio definiamo i parametri per la nostra attività ricorrente. Specifichiamo il nome dell'attività, la durata e il modello di ricorrenza. Per la ricorrenza annuale, utilizziamo il file`YearlyRecurrencePattern` e impostare la ripetizione in modo che avvenga il 1° giorno di luglio utilizzando`ByYearDayRepetition`. Inoltre, definiamo l'intervallo di ricorrenza dal 1 luglio 2018 al 1 luglio 2019.

## Passaggio 3: aggiungi attività al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

Qui aggiungiamo i parametri dell'attività ricorrente definiti all'attività root del progetto.

## Passaggio 4: salva il progetto

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Infine, salviamo il file di progetto modificato con l'attività ricorrente aggiunta.

## Conclusione

In questo tutorial, abbiamo esplorato il processo di utilizzo delle ripetizioni dei giorni dell'anno in Aspose.Tasks per .NET. Seguendo i passaggi forniti, gli sviluppatori possono integrare perfettamente le funzionalità delle attività ricorrenti nelle loro applicazioni, migliorando le capacità di gestione dei progetti.

## Domande frequenti

### Q1: Aspose.Tasks può gestire modelli di ricorrenza complessi?

A1: Sì, Aspose.Tasks fornisce un supporto completo per vari modelli di ricorrenza, compresi quelli complessi come ripetizioni annuali, mensili, settimanali e giornaliere.

### Q2: Aspose.Tasks è compatibile con diversi formati di file di progetto?

A2: Assolutamente, Aspose.Tasks supporta i formati di file di progetto più diffusi come MPP, XML e CSV, garantendo la compatibilità tra diversi strumenti di gestione dei progetti.

### Q3: Aspose.Tasks offre documentazione e supporto per gli sviluppatori?

R3: Sì, gli sviluppatori possono accedere a un'ampia documentazione e chiedere assistenza ai forum della community Aspose.Tasks per qualsiasi domanda o problema riscontrato.

### Q4: posso personalizzare le proprietà dell'attività come la durata e la data di inizio utilizzando Aspose.Tasks?

A4: Certamente, Aspose.Tasks fornisce API robuste per manipolare dinamicamente le proprietà delle attività, consentendo agli sviluppatori di personalizzare durate, date di inizio, dipendenze e altro.

### Q5: Aspose.Tasks è adatto sia a progetti su piccola scala che a livello aziendale?

A5: In effetti, Aspose.Tasks è progettato per soddisfare le esigenze degli sviluppatori che lavorano su progetti di tutte le scale, dalle attività individuali ai progetti aziendali su larga scala.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
