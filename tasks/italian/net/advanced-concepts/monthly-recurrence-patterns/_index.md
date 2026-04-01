---
date: 2026-03-08
description: Scopri come creare un'attività ricorrente mensile in Aspose.Tasks per
  .NET con questo tutorial passo‑passo.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come creare un'attività ricorrente mensile in Aspose.Tasks
url: /it/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crea attività ricorrente mensile usando Aspose.Tasks

## Introduzione

Aspose.Tasks per .NET ti consente di manipolare programmaticamente i file Microsoft Project, e una delle esigenze più comuni nel mondo reale è **creare attività ricorrenti mensili**. Che tu stia costruendo uno strumento di monitoraggio dei progetti, automatizzando l'allocazione delle risorse o generando voci di lavoro di manutenzione ricorrenti, questo tutorial ti guida passo passo nell'aggiungere un modello di ricorrenza mensile a un'attività.

Nelle sezioni successive vedrai come configurare il progetto, definire i parametri di ricorrenza e infine salvare il file aggiornato — il tutto con spiegazioni chiare e consigli pratici.

## Risposte rapide
- **Cosa significa “attività ricorrente mensile”?** Un'attività che si ripete secondo un modello giorno‑o‑settimana definito ogni mese.  
- **Quale classe API gestisce la ricorrenza?** `RecurringTaskParameters` insieme a `MonthlyRecurrencePattern`.  
- **È necessaria una licenza per eseguire il campione?** Una versione di prova gratuita è sufficiente per la valutazione; è richiesta una licenza per la produzione.  
- **Posso modificare l'intervallo?** Sì – imposta `RepetitionInterval` al numero di mesi tra le occorrenze.  
- **Quali formati di file sono supportati?** Sia i file Project `.mpp` che `.xml` possono essere caricati e salvati.

## Cos'è un modello di ricorrenza mensile?

Un modello di ricorrenza mensile indica a Microsoft Project (e ad Aspose.Tasks) con quale frequenza un'attività deve ripetersi ogni mese. Puoi specificare un giorno fisso del mese (ad esempio, il 1°) o una posizione relativa (ad esempio, l'ultimo venerdì). L'API traduce queste regole nella struttura sottostante del file Project.

## Perché usare Aspose.Tasks per questo?

- **Controllo totale** – Nessuna limitazione dell'interfaccia; definisci ogni aspetto del modello nel codice.  
- **Cross‑platform** – Funziona su .NET Framework, .NET Core e .NET 5/6+.  
- **Nessun Microsoft Project richiesto** – Genera o modifica file su un server o in una pipeline CI.  

## Prerequisiti

Prima di iniziare, assicurati di avere:

- .NET 6 (o .NET 5/Framework 4.7+) installato.  
- Pacchetto NuGet Aspose.Tasks per .NET aggiunto al tuo progetto.  
- Un file Project di esempio (`Project1.mpp`) posizionato in una cartella nota (`DataDir`).  

## Importa gli spazi dei nomi

Per prima cosa, importa gli spazi dei nomi necessari per lavorare con le attività e salvare i progetti:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Passo 1: Inizializza il progetto

Crea un'istanza `Project` che punti al tuo file `.mpp` esistente. Questo carica il file in memoria così da poterlo modificare.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Suggerimento:** Se il file non esiste, Aspose.Tasks creerà automaticamente un nuovo progetto vuoto.

## Passo 2: Imposta i parametri dell'attività ricorrente

Definisci i dettagli dell'attività ricorrente, includendo nome, durata e il modello mensile da applicare.

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

- `DayPosition = 1` indica che l'attività si verifica il **primo giorno** del mese.  
- `RepetitionInterval = 2` fa sì che l'attività si ripeta **ogni due mesi**.  
- `Start` e `Finish` definiscono la finestra complessiva durante la quale la ricorrenza è attiva.

## Passo 3: Aggiungi i parametri al progetto

Allega l'oggetto `RecurringTaskParameters` alla collezione dei figli del task radice. Questo crea effettivamente l'attività ricorrente nella gerarchia del progetto.

```csharp
project.RootTask.Children.Add(parameters);
```

## Passo 4: Salva il progetto

Persisti le modifiche salvando il progetto in un nuovo file. Puoi scegliere qualsiasi formato supportato; qui utilizziamo il formato nativo `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Dopo aver eseguito il codice, apri il file risultante in Microsoft Project per vedere l'attività ricorrente mensile appena creata.

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| L'attività non appare dopo il salvataggio | Progetto non aggiornato nell'interfaccia | Ri‑apri il file o chiama `project.UpdateTaskLinks()` prima di salvare. |
| Data di inizio errata | `Start` impostato a un fine settimana | Usa un `DateTime` che cada in un giorno lavorativo o regola il calendario. |
| Intervallo di ricorrenza ignorato | Uso di `ByMonthDayRepetition` con `DayPosition` = 0 | Assicurati che `DayPosition` sia compreso tra 1‑31. |

## Conclusione

Seguendo questi passaggi ora sai come **creare attività ricorrenti mensili** con Aspose.Tasks per .NET. L'API ti offre un controllo granulare sugli intervalli di ricorrenza, sui range di inizio/fine e sul modello di giorno specifico, consentendoti di automatizzare scenari complessi di pianificazione dei progetti.

## FAQ

### Q1: Aspose.Tasks è compatibile con tutte le versioni dei file Microsoft Project?

A1: Aspose.Tasks supporta varie versioni dei file Microsoft Project, inclusi MPP, MPT, XML e MPX.

### Q2: Posso personalizzare ulteriormente il modello di ricorrenza?

A2: Sì, Aspose.Tasks fornisce ampie opzioni per personalizzare i modelli di ricorrenza, inclusi giornalieri, settimanali, mensili e annuali.

### Q3: È disponibile una versione di prova gratuita per Aspose.Tasks?

A3: Sì, puoi ottenere una versione di prova gratuita di Aspose.Tasks dal sito web [qui](https://releases.aspose.com/).

### Q4: Come posso ottenere supporto per Aspose.Tasks?

A4: Puoi richiedere assistenza e partecipare alle discussioni sul [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Dove posso acquistare una licenza per Aspose.Tasks?

A5: Puoi acquistare una licenza per Aspose.Tasks dal sito web [qui](https://purchase.aspose.com/buy)

## Domande frequenti

**D: Posso usare questo codice in un'applicazione .NET Core?**  
R: Assolutamente. Aspose.Tasks per .NET supporta pienamente .NET Core 3.1 e versioni successive.

**D: Come modifico la ricorrenza in “ultimo giorno lavorativo del mese”?**  
R: Usa `ByMonthDayRepetition` con `DayPosition = -1` (i valori negativi contano dal fine mese) e imposta `WeekDay` di conseguenza.

**D: Cosa succede se l'intervallo di ricorrenza supera il calendario del progetto?**  
R: L'API rispetta il calendario del progetto; le occorrenze che cadono in giorni non lavorativi vengono saltate o spostate in base alle impostazioni del calendario.

**D: È possibile eliminare una specifica occorrenza di un'attività ricorrente?**  
R: Sì. Dopo aver aggiunto l'attività ricorrente, puoi recuperare le singole occorrenze tramite `Task.GetOccurrences()` ed eliminare quelle non necessarie.

**D: Aspose.Tasks gestisce automaticamente le differenze di fuso orario?**  
R: La libreria memorizza le date in UTC; puoi convertire in ora locale usando i metodi standard `DateTime` di .NET, se necessario.

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}