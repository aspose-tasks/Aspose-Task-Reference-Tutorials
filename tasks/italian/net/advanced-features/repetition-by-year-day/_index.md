---
date: 2026-04-03
description: Impara la pianificazione delle attività di gestione dei progetti e come
  aggiungere attività ricorrenti usando Aspose.Tasks per .NET, inclusa la possibilità
  di salvare il progetto come MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Ripetizione per giorno dell'anno in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Pianificazione delle attività di gestione progetti con ripetizione giornaliera
  annuale in Aspose.Tasks
url: /it/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pianificazione delle attività di gestione del progetto con ripetizione giorno dell'anno in Aspose.Tasks

## Introduzione

Una **pianificazione delle attività di gestione del progetto** efficace è la spina dorsale di qualsiasi progetto di successo. Quando le attività si ripetono su base annuale — come audit annuali, finestre di manutenzione o revisioni stagionali — gestire manualmente queste ricorrenze può diventare soggetto a errori e richiedere molto tempo. Aspose.Tasks per .NET semplifica questo consentendo di definire programmaticamente i modelli giorno‑anno, così puoi concentrarti su ciò che conta di più: fornire valore. In questo tutorial imparerai **come aggiungere un'attività ricorrente** basata su un giorno specifico dell'anno e vedrai esattamente **come salvare il progetto come MPP** per un'integrazione fluida con Microsoft Project.

## Risposte rapide
- **Cosa significa “ripetizione giorno dell'anno”?** Programma un'attività in un giorno specifico di un mese specifico ogni anno.  
- **Quale classe API crea la ricorrenza?** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **Posso impostare una data di inizio e fine?** Yes, using `EndByRecurrenceRange`.  
- **Quale formato file viene prodotto?** The project is saved as an MPP file (`SaveFileFormat.Mpp`).  
- **È necessaria una licenza per la produzione?** A commercial license is required for non‑evaluation use.

## Prerequisiti

Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti in ordine:

1. Libreria Aspose.Tasks per .NET: scarica e installa la libreria Aspose.Tasks per .NET dal [sito web](https://releases.aspose.com/tasks/net/).  
2. Ambiente di sviluppo: configura un ambiente di sviluppo adeguato con Visual Studio o qualsiasi altro IDE preferito per lo sviluppo .NET.  
3. Conoscenza di base di C#: familiarizzati con i fondamenti del linguaggio di programmazione C# per seguire gli esempi di codice.  
4. Concetti di gestione del progetto: la comprensione dei concetti di gestione del progetto e della pianificazione delle attività aiuterà a cogliere efficacemente i concetti del tutorial.

## Importare gli spazi dei nomi

Prima di iniziare a scrivere codice, importiamo gli spazi dei nomi necessari per facilitare la manipolazione delle attività usando Aspose.Tasks per .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Ora, suddividiamo l'esempio fornito in più passaggi e spieghiamo ogni passaggio in dettaglio.

## Come aggiungere un'attività ricorrente con modello giorno dell'anno

### Passo 1: Caricare il file di progetto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Qui, inizializziamo un nuovo oggetto `Project` e carichiamo un file di progetto esistente chiamato **Project1.mpp**.

### Passo 2: Definire i parametri dell'attività ricorrente

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

In questo passaggio, definiamo i parametri per la nostra attività ricorrente. Specifichiamo il nome dell'attività, la durata e il modello di ricorrenza. Per una ricorrenza annuale, utilizziamo `YearlyRecurrencePattern` e impostiamo la ripetizione per il **1° giorno di luglio** usando `ByYearDayRepetition`. Inoltre, definiamo l'intervallo di ricorrenza dal 1 luglio 2018 al 1 luglio 2019.

### Passo 3: Aggiungere l'attività al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

Qui, aggiungiamo i parametri dell'attività ricorrente definiti al task radice del progetto.

### Passo 4: Salvare il progetto come MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Infine, **salviamo il progetto come file MPP**, rendendolo pronto per l'apertura in Microsoft Project o in qualsiasi visualizzatore compatibile.

## Perché è importante

- **Automazione** – Elimina l'inserimento manuale delle attività annuali, riducendo gli errori umani.  
- **Coerenza** – Garantisce che lo stesso modello giorno‑mese sia applicato su più anni.  
- **Integrazione** – Il file MPP risultante può essere condiviso con le parti interessate che si affidano a Microsoft Project.  

## Errori comuni e suggerimenti

- **Precisione di DateTime** – Assicurati che l'ora di inizio sia allineata al calendario del progetto; altrimenti, l'attività potrebbe apparire spostata.  
- **Fusi orari** – L'API lavora con oggetti `DateTime`; considera la conversione in UTC se la tua applicazione copre più regioni.  
- **Applicazione della licenza** – In modalità valutazione, il MPP salvato può contenere una filigrana; utilizza una licenza valida per la produzione.

## Domande frequenti

**Q: Aspose.Tasks può gestire modelli di ricorrenza complessi?**  
A: Sì, Aspose.Tasks fornisce un supporto completo per vari modelli di ricorrenza, inclusi quelli annuali, mensili, settimanali e giornalieri.

**Q: Aspose.Tasks è compatibile con diversi formati di file di progetto?**  
A: Assolutamente, Aspose.Tasks supporta formati di file di progetto popolari come MPP, XML e CSV, garantendo la compatibilità con diversi strumenti di gestione del progetto.

**Q: Aspose.Tasks offre documentazione e supporto per gli sviluppatori?**  
A: Sì, gli sviluppatori possono accedere a una documentazione estesa e richiedere assistenza nei forum della community di Aspose.Tasks per qualsiasi domanda o problema.

**Q: Posso personalizzare le proprietà dell'attività come durata e data di inizio usando Aspose.Tasks?**  
A: Certamente, Aspose.Tasks fornisce API robuste per manipolare dinamicamente le proprietà delle attività, consentendo agli sviluppatori di personalizzare durate, date di inizio, dipendenze e altro.

**Q: Aspose.Tasks è adatto sia per progetti di piccola scala che per progetti a livello aziendale?**  
A: Infatti, Aspose.Tasks è progettato per soddisfare le esigenze degli sviluppatori che lavorano su progetti di qualsiasi dimensione, dalle singole attività a grandi progetti aziendali.

**Ultimo aggiornamento:** 2026-04-03  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}