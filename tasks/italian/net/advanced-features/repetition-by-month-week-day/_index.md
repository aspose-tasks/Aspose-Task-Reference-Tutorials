---
date: 2026-04-01
description: Scopri come impostare la ricorrenza in Aspose.Tasks per .NET, aggiungere
  attività ricorrenti e automatizzare le attività ricorrenti per mese, settimana e
  giorno.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Ripetizione per Mese, Settimana, Giorno in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come impostare la ricorrenza in Aspose.Tasks (Mese, Settimana, Giorno)
url: /it/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la ricorrenza in Aspose.Tasks (Mese, Settimana, Giorno)

## Introduzione

Se hai bisogno di **impostare la ricorrenza** per le attività in un progetto, Aspose.Tasks per .NET ti offre un modo pulito e programmatico per aggiungere definizioni di attività ricorrenti che si eseguono per mese, settimana o giorno. In questo tutorial percorreremo un esempio reale che ti mostra come **aggiungere attività ricorrenti**, **automatizzare le attività ricorrenti** e gestirle direttamente dal codice C#. Alla fine, sarai pronto a integrare questa funzionalità in qualsiasi soluzione di pianificazione o gestione progetti.

## Risposte rapide
- **Cosa significa “recurrence” in Aspose.Tasks?** Definisce un modello (giornaliero, settimanale, mensile) che crea automaticamente istanze di attività su un intervallo di date.  
- **Quale metodo principale crea la ricorrenza?** `RecurringTaskParameters` combinato con un `RecurrencePattern` specifico.  
- **Ho bisogno di una licenza per eseguire questo codice?** Una versione di prova funziona per la valutazione; è necessaria una licenza commerciale per la produzione.  
- **Posso programmare attività settimanali invece di mensili?** Sì – sostituisci `MonthlyRecurrencePattern` con `WeeklyRecurrencePattern`.  
- **Quali versioni di .NET sono supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 e successive.

## Che cos'è la ricorrenza in Aspose.Tasks?

La ricorrenza è un insieme di regole che indica ad Aspose.Tasks di generare istanze di attività a intervalli regolari—giornalieri, settimanali o mensili—senza duplicarle manualmente. Questa funzionalità è essenziale per i progetti che contengono attività di routine come riunioni di stato, ispezioni o lavori di manutenzione.

## Perché utilizzare le funzionalità di ricorrenza?

- **Risparmia tempo:** Nessuna necessità di copiare‑incollare le attività manualmente.  
- **Riduci gli errori:** La libreria garantisce date e durate coerenti.  
- **Flessibilità:** Combina i modelli (ad esempio, “primo domenica di ogni 2 mesi”).  
- **Automazione:** Perfetta per generare pianificazioni in pipeline CI o strumenti di reporting.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Conoscenza di base di C#** – scriverai alcune righe di codice C#.  
2. **Aspose.Tasks per .NET installato** – scaricalo dalla [pagina di download](https://releases.aspose.com/tasks/net/).  
3. **Un file di progetto .mpp** – useremo `Project1.mpp` come file sorgente.

## Importare gli spazi dei nomi

Per iniziare, importa gli spazi dei nomi Aspose.Tasks richiesti:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Passo 1: Caricare il file di progetto

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Creiamo un'istanza `Project` che punta a un file Microsoft Project esistente.

### Passo 2: Definire i parametri dell'attività ricorrente

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

Qui **creiamo i parametri dell'attività ricorrente**:

- **TaskName** – il nome dell'attività generata.  
- **Duration** – la durata di ciascuna occorrenza.  
- **RecurrencePattern** – un modello mensile che si ripete ogni 2 mesi la prima domenica.  
- **RecurrenceRange** – le date di inizio e fine che delimitano la pianificazione.

### Passo 3: Aggiungere l'attività ricorrente al progetto

```csharp
project.RootTask.Children.Add(parameters);
```

Questa riga **aggiunge l'attività ricorrente** alla radice della gerarchia del progetto.

### Passo 4: Salvare il progetto aggiornato

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Il progetto viene salvato come nuovo file `.mpp` che ora contiene la pianificazione automatica.

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Attività non visualizzata** | L'intervallo di ricorrenza è al di fuori delle date del progetto. | Verifica che i valori `Start` e `Finish` siano entro il calendario del progetto. |
| **Giorno della settimana errato** | Incongruenza dell'enum `WeekDay`. | Usa `DayOfWeek.Monday` … `DayOfWeek.Sunday` secondo necessità. |
| **Eccezione di licenza** | Esecuzione senza licenza valida in produzione. | Applica una licenza temporanea o completa prima di salvare. |

## Domande frequenti

### Q1: Posso personalizzare il modello di ricorrenza oltre gli esempi forniti?

Sì, Aspose.Tasks per .NET offre ampie opzioni di personalizzazione per i modelli di ricorrenza, consentendoti di adattarli alle tue esigenze specifiche.

### Q2: È disponibile una versione di prova per Aspose.Tasks per .NET?

Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET dalla [pagina dei rilasci](https://releases.aspose.com/).

### Q3: Come posso ottenere supporto per Aspose.Tasks per .NET?

Puoi cercare assistenza e interagire con la community sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q4: Sono disponibili licenze temporanee per Aspose.Tasks per .NET?

Sì, puoi acquisire licenze temporanee dalla [pagina di acquisto](https://purchase.aspose.com/temporary-license/) per scopi di test e valutazione.

### Q5: Dove posso trovare la documentazione completa per Aspose.Tasks per .NET?

Puoi consultare la dettagliata [documentazione](https://reference.aspose.com/tasks/net/) disponibile sul sito Aspose per una guida approfondita sull'utilizzo della libreria.

---

**Ultimo aggiornamento:** 2026-04-01  
**Testato con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}