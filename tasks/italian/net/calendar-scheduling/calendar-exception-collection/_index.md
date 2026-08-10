---
date: 2026-04-09
description: Scopri come impostare il calendario standard e gestire le festività del
  progetto nei tuoi progetti .NET usando Aspose.Tasks per una pianificazione accurata.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Imposta il calendario standard e gestisci le eccezioni in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Imposta il calendario standard e gestisci le eccezioni in Aspose.Tasks
url: /it/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta Calendario Standard e Gestisci le Eccezioni in Aspose.Tasks

## Introduzione

La programmazione accurata è la spina dorsale di qualsiasi progetto di successo, e i piani del mondo reale spesso devono discostarsi dal calendario di lavoro predefinito a causa di festività, eventi speciali o interruzioni impreviste. Aspose.Tasks per .NET rende semplice **impostare un calendario standard** e poi sovrapporre eccezioni personalizzate. In questo tutorial imparerai a caricare un calendario di progetto, impostare un calendario standard e gestire le festività del progetto tramite la funzionalità Calendar Exception Collection.

## Risposte Rapide
- **Cosa fa “set standard calendar”?** Reimposta un calendario all'orario di lavoro predefinito (9 AM‑5 PM, lunedì‑venerdì) prima di aggiungere eccezioni personalizzate.  
- **Quale metodo cancella le eccezioni esistenti?** `Calendar.Exceptions.Clear()` rimuove tutte le eccezioni precedentemente definite.  
- **Come posso aggiungere una festività?** Crea un `CalendarException` con `DayWorking = false` e aggiungilo alla collezione.  
- **Devo ricaricare il progetto dopo le modifiche?** No, le modifiche vengono applicate direttamente all'oggetto `Project` in memoria.  
- **Quali librerie sono necessarie?** Aspose.Tasks per .NET (qualsiasi versione .NET supportata) e gli spazi dei nomi `System`.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. **Aspose.Tasks per .NET** – scaricalo [qui](https://releases.aspose.com/tasks/net/).  
2. Conoscenza di base di **C#** – scriverai alcuni brevi snippet.  
3. Un ambiente di sviluppo come **Visual Studio** o **JetBrains Rider**.

## Importa Namespace

Queste direttive `using` ti danno accesso alle classi necessarie per la manipolazione del calendario.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Cos'è un'eccezione di calendario?

Un'*eccezione di calendario* rappresenta un periodo in cui il normale orario di lavoro viene modificato – ad esempio, una festività aziendale o un programma temporaneo di straordinario. Aggiungendo eccezioni a un calendario è possibile modellare vincoli reali senza modificare il calendario di base.

## Come impostare il calendario standard in Aspose.Tasks

Il primo passo è caricare il file di progetto e recuperare il calendario con cui vuoi lavorare.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Passo 1: Cancella le eccezioni esistenti e ripristina un calendario standard

Prima di aggiungere nuove regole, è buona pratica cancellare eventuali vecchie eccezioni e impostare le impostazioni del **calendario standard**. Questo garantisce una base pulita.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Passo 2: Definisci un'eccezione di orario di lavoro

A volte è necessario creare un programma temporaneo (ad esempio, ore prolungate per il lancio di un prodotto). Il frammento seguente definisce un'eccezione di orario di lavoro che si estende per diversi giorni e include due periodi di lavoro giornalieri.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Passo 3: Aggiungi eccezioni di tempo non lavorativo (Festività)

Per **gestire le festività del progetto**, crea eccezioni dove `DayWorking` è `false`. L'esempio sotto aggiunge un blocco di festività di due giorni.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Passo 4: Visualizza le eccezioni del calendario (Verifica)

Dopo aver aggiunto le eccezioni, spesso si desidera verificare che siano state registrate correttamente. Il ciclo seguente stampa i dettagli di ogni eccezione sulla console.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Passo 5: Rimuovi tutte le eccezioni (Pulizia)

Se è necessario ripristinare il calendario al suo stato originale, è possibile rimuovere ogni eccezione programmaticamente.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Problemi comuni e soluzioni

| Problema | Motivo | Correzione |
|----------|--------|------------|
| Le eccezioni non compaiono dopo il salvataggio | Progetto non salvato dopo le modifiche | Chiama `project.Save("output.mpp")` dopo aver apportato le modifiche. |
| Le eccezioni sovrapposte causano ore di lavoro inattese | Aspose.Tasks utilizza l'ultima eccezione aggiunta per i periodi sovrapposti | Ordina le chiamate `Add` con attenzione o regola manualmente le priorità. |
| `MakeStandardCalendar` reimposta gli orari di lavoro personalizzati | Cancella intenzionalmente gli orari personalizzati; riaggiungili dopo la chiamata se necessario. | Aggiungi i tuoi oggetti `WorkingTime` personalizzati dopo aver invocato `MakeStandardCalendar`. |

## Domande frequenti

**Q: Posso aggiungere più eccezioni a un singolo calendario?**  
A: Sì, è possibile aggiungere più eccezioni a un calendario usando il metodo `AddRange`.

**Q: Come gestisco le eccezioni ricorrenti, come le festività settimanali?**  
A: È possibile calcolare programmaticamente le eccezioni ricorrenti e aggiungerle al calendario usando una logica personalizzata.

**Q: È possibile importare le eccezioni del calendario da fonti esterne?**  
A: Sì, è possibile leggere le eccezioni del calendario da fonti esterne come database o file CSV e integrarle nel tuo progetto.

**Q: Cosa succede se ci sono eccezioni sovrapposte nel calendario?**  
A: Aspose.Tasks per .NET consente di gestire le eccezioni sovrapposte definendo priorità o risolvendo i conflitti in base ai requisiti del tuo progetto.

**Q: Posso personalizzare gli orari di lavoro per ogni giorno all'interno di un'eccezione?**  
A: Sì, è possibile specificare orari di lavoro personalizzati per i singoli giorni all'interno di un'eccezione per soddisfare esigenze di programmazione specifiche.

## Conclusione

Impostando prima un **calendario standard** e poi aggiungendo eccezioni personalizzate, ottieni il pieno controllo sulla programmazione del progetto, facilitando la **gestione delle festività del progetto** e di qualsiasi altra tempistica speciale. La Calendar Exception Collection in Aspose.Tasks fornisce un modo pulito e programmatico per modellare calendari reali direttamente nelle tue applicazioni .NET.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}