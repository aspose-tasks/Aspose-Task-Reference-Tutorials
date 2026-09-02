---
date: 2026-04-03
description: Impara a usare Aspose.Tasks per aggiungere un progetto con attività ricorrenti
  e salvare il progetto come MPP. Questa guida mostra passo passo la funzionalità
  Ripetizione per Anno Settimana Giorno.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Ripetizione per Anno Settimana Giorno in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come usare Aspose.Tasks – Ripetizione per anno, settimana, giorno
url: /it/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ripetizione per Anno Settimana Giorno in Aspose.Tasks

## Introduzione

Quando hai bisogno di **how to use Aspose.Tasks** per gestire programmi ricorrenti complessi, la libreria ti offre un controllo dettagliato sui modelli annuali. In questo tutorial vedremo come creare un'attività che si ripete in un giorno della settimana specifico di un determinato mese, estendendosi su più anni. Alla fine sarai in grado di **add recurring task project** e **save project as MPP** con poche righe di C#.

## Risposte Rapide
- **Che cosa significa “Repetition by Year Week Day”?** Ripete un'attività in un giorno della settimana scelto (ad es., la prima domenica) di un determinato mese ogni anno.  
- **Quali versioni .NET sono supportate?** Tutte le versioni moderne di .NET Framework e .NET Core/5/6.  
- **È necessaria una licenza per eseguire il codice?** Una prova gratuita funziona per lo sviluppo; è richiesta una licenza commerciale per la produzione.  
- **Posso modificare l'intervallo di ricorrenza?** Sì – puoi impostare una data di inizio, una data di fine o un numero fisso di occorrenze.  
- **L'output è un file MPP?** Assolutamente – il progetto viene salvato come file MPP pronto per Microsoft Project.

## Che cos'è la funzionalità “Repetition by Year Week Day”?

La funzionalità consente di definire una ricorrenza annuale che mira a un particolare **giorno della settimana** (ad es., domenica) e a una **posizione** all'interno del mese (prima, seconda, ultima, ecc.). È ideale per attività come revisioni trimestrali, audit annuali o qualsiasi evento che segue un ritmo basato sul calendario.

## Perché usare Aspose.Tasks per attività ricorrenti?

- **Precision** – Controllo completo su mesi, giorni della settimana e posizioni ordinali.  
- **Compatibility** – Genera file MPP nativi che si aprono perfettamente in Microsoft Project.  
- **No COM interop** – API .NET pura, senza necessità di installazioni Office.  
- **Scalability** – Funziona per piccoli progetti e per pianificazioni a livello aziendale allo stesso modo.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. **Basic .NET knowledge** – Familiarità con C# e concetti di programmazione orientata agli oggetti.  
2. **Aspose.Tasks for .NET** – Scaricalo dal [download link](https://releases.aspose.com/tasks/net/) e aggiungi il DLL al tuo progetto.  
3. **Access to the official docs** – La [documentation](https://reference.aspose.com/tasks/net/) contiene dettagli esaustivi su tutte le classi.  
4. **A development IDE** – Visual Studio, Rider o qualsiasi editor .NET compatibile.

Ora che sei pronto, vediamo l'implementazione.

## Come usare Aspose.Tasks per attività ricorrenti

### Importazione dei namespace necessari

Prima, importa i namespace richiesti nello scope così da poter lavorare con progetti, attività e opzioni di salvataggio.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Passo 1: Inizializzare il progetto e i parametri dell'attività

Crea una nuova istanza `Project`, quindi definisci un oggetto `RecurringTaskParameters` che descrive il modello di ricorrenza.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Regola `Month`, `WeekDay` e `Position` per corrispondere al tuo calendario reale.

### Passo 2: Aggiungere i parametri al progetto

Inserisci la definizione dell'attività ricorrente nella radice del progetto.

```csharp
project.RootTask.Children.Add(parameters);
```

### Passo 3: Salvare il progetto come MPP

Infine, persisti il progetto in un file MPP così che possa essere aperto in Microsoft Project o in qualsiasi visualizzatore compatibile.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Questo dimostra **save project as mpp** in una singola riga di codice.

## Problemi comuni e soluzioni

| Sintomo | Probabile causa | Risoluzione |
|---------|-----------------|-------------|
| Nessuna attività appare dopo l'apertura del file MPP | Le date dell'intervallo di ricorrenza sono al di fuori del calendario del progetto | Verifica che le date `Start` e `Finish` rientrino nell'orario di lavoro del progetto |
| Eccezione `ArgumentNullException` su `Add` | `parameters` è null o non completamente inizializzato | Assicurati che tutte le proprietà richieste (TaskName, Duration, RecurrencePattern) siano impostate |
| Giorno della settimana errato selezionato | Valore dell'enum `WeekDay` non corrispondente | Usa `DayOfWeek.Monday` … `DayOfWeek.Sunday` secondo necessità |

## Domande frequenti

**Q: Posso personalizzare il modello di ricorrenza oltre l'esempio fornito?**  
A: Sì, Aspose.Tasks ti consente di combinare `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` o anche oggetti personalizzati `RecurrenceRange` per adattarli a qualsiasi calendario.

**Q: Aspose.Tasks per .NET è compatibile con altri software di gestione progetti?**  
A: Assolutamente – la libreria legge e scrive formati MPP, XML e Primavera, facilitando lo scambio di dati.

**Q: Come posso gestire eccezioni o modifiche alle attività ricorrenti?**  
A: Usa la classe `ExceptionTask` per creare sovrascritture per occorrenze specifiche, oppure modifica i `RecurringTaskParameters` e salva nuovamente il progetto.

**Q: Aspose.Tasks supporta soluzioni basate sul cloud?**  
A: Sì, puoi eseguire l'API in Azure Functions, AWS Lambda o in qualsiasi servizio cloud compatibile con .NET.

**Q: È disponibile una versione di prova per Aspose.Tasks per .NET?**  
A: Sì, puoi accedere a una prova gratuita di Aspose.Tasks per .NET dal [website](https://releases.aspose.com/), permettendoti di esplorare le funzionalità prima di decidere un acquisto.

**Q: Come aggiungo un'attività ricorrente a un progetto esistente senza sovrascrivere altri dati?**  
A: Carica il progetto esistente con `new Project("Existing.mpp")`, aggiungi i `RecurringTaskParameters` a `RootTask.Children` e poi `Save` il file.

## Conclusione

Padroneggiando **how to use Aspose.Tasks** per lo scenario **Repetition by Year Week Day**, ottieni la capacità di **add recurring task project** che si allineano perfettamente ai calendari reali e **save project as MPP** per una collaborazione senza interruzioni. Integra questi snippet nelle tue soluzioni per migliorare la precisione della pianificazione e ridurre lo sforzo manuale.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}