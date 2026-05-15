---
date: 2026-04-13
description: Scopri come impostare le ore lavorative e gestire le raccolte di calendari
  in Aspose.Tasks per .NET. Importa i calendari di Microsoft Project, rimuovi il calendario
  del progetto e ottieni il calendario per nome facilmente.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Gestione della collezione di calendari in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Imposta le ore lavorative nella raccolta di calendari di Aspose.Tasks
url: /it/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imposta le ore lavorative nella raccolta di calendari Aspose.Tasks

In questo tutorial imparerai come **impostare le ore lavorative** e gestire le raccolte di calendari usando Aspose.Tasks per .NET. I calendari definiscono i giorni lavorativi, le festività e le eccezioni, quindi padroneggiarli ti consente di controllare i programmi di progetto con precisione. Ti mostreremo anche come importare i calendari da Microsoft Project, rimuovere un calendario da un progetto e ottenere un calendario per nome.

## Risposte rapide
- **Qual è la classe principale per i calendari?** `Project.Calendars` collection.
- **Come impostare le ore lavorative?** Create or modify a `Calendar` object and define its `WorkingTime`.
- **Posso importare i calendari da Microsoft Project?** Yes – load an MPP file and access its calendars.
- **Come rimuovere un calendario da un progetto?** Use `Project.Calendars.Remove(calendar)`.
- **Come recuperare un calendario per nome?** Call `Project.Calendars.GetByName("YourCalendar")`.

## Prerequisiti

1. Visual Studio: Installa Visual Studio o qualsiasi altro IDE compatibile per lo sviluppo .NET.  
2. Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da [here](https://releases.aspose.com/tasks/net/).  
3. Conoscenza di base di C#: Familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi

Per prima cosa, importiamo gli spazi dei nomi necessari per lavorare con Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Creazione di un nuovo calendario

### Passo 1: Inizializza un nuovo oggetto `Project`.
```csharp
var project = new Project();
```

### Passo 2: Aggiungi calendari alla raccolta di calendari del progetto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Passo 3: Itera attraverso i calendari e mostra i loro nomi.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Come impostare le ore lavorative per un calendario?

Per **impostare le ore lavorative**, modifichi la collezione `WorkingTime` di un `Calendar`.  
Ad esempio, puoi definire una giornata lavorativa standard dalle 9:00 alle 17:00 o aggiungere eccezioni personalizzate.  
Il codice per questo è identico agli esempi mostrati più avanti quando creiamo un calendario standard.

## Sostituire un calendario con un nuovo calendario

### Passo 1: Carica un progetto esistente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passo 2: Rimuovi il calendario esistente (se esiste).  
Questo dimostra lo scenario di **rimozione del calendario dal progetto**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Passo 3: Aggiungi un nuovo calendario.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Recuperare un calendario per nome o ID

### Passo 1: Carica il progetto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passo 2: Recupera i calendari per nome o UID.  
Questo illustra l'operazione di **recupero del calendario per nome**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Passo 3: Mostra i dettagli del calendario.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterare sui calendari

### Passo 1: Carica il progetto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passo 2: Recupera il conteggio dei calendari.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Passo 3: Itera sulla collezione di calendari e mostra i nomi.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Creare un calendario standard

### Passo 1: Inizializza un nuovo progetto.
```csharp
var project = new Project();
```

### Passo 2: Definisci un nuovo calendario e rendilo standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Passo 3: Salva il progetto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Problemi comuni e soluzioni

- **Calendario non trovato quando si utilizza `GetByName`** – Assicurati che il nome esatto corrisponda al caso usato quando il calendario è stato aggiunto.  
- **Ore lavorative non applicate** – Dopo aver impostato `WorkingTime`, ricorda di salvare il progetto; altrimenti le modifiche rimangono solo in memoria.  
- **Importazione dei calendari da un file MPP fallita** – Verifica che il file di origine sia un file Microsoft Project valido e che tu abbia i permessi di lettura.

## FAQ

### Q1: Posso creare giorni lavorativi personalizzati in Aspose.Tasks?
A1: Sì, è possibile creare giorni lavorativi personalizzati aggiungendo eccezioni ai calendari.

### Q2: È possibile importare i calendari da file Microsoft Project?
A2: Assolutamente, Aspose.Tasks supporta l'importazione dei calendari da file Microsoft Project.

### Q3: Come posso rimuovere un calendario specifico da un progetto?
A3: Puoi rimuovere un calendario prelevandolo dalla collezione e poi chiamando il metodo `Remove`.

### Q4: Aspose.Tasks supporta l'esportazione dei calendari in formati diversi?
A4: Sì, Aspose.Tasks consente di esportare i calendari in vari formati come XML, MPP, ecc.

### Q5: Posso personalizzare le ore lavorative per giorni specifici in un calendario?
A5: Certamente, puoi definire le ore lavorative per giorni individuali usando le eccezioni nel calendario.

## Domande frequenti

**Q: Qual è il modo migliore per impostare un calendario a turno di 24 ore?**  
A: Crea un nuovo calendario, cancella le voci `WorkingTime` esistenti e aggiungi un unico intervallo `WorkingTime` dalle 00:00 alle 24:00 per ogni giorno della settimana.

**Q: Posso copiare un calendario da un progetto a un altro?**  
A: Sì—esporta il calendario in XML usando `project.Save` e poi importalo in un altro progetto con `new Project(xmlPath)`.

**Q: Come importare programmaticamente i calendari da Microsoft Project?**  
A: Carica il file MPP con `new Project("source.mpp")`; i calendari diventano disponibili tramite `project.Calendars`.

**Q: Esiste un limite al numero di calendari in un progetto?**  
A: Praticamente no; la collezione può contenere quanti calendari la memoria consente, ma è consigliabile mantenere l'elenco gestibile per le prestazioni.

**Q: Le modifiche a un calendario aggiornano automaticamente le attività che lo utilizzano?**  
A: Sì—le attività collegate a un calendario riflettono i tempi di lavoro aggiornati dopo aver salvato il progetto.

---

**Ultimo aggiornamento:** 2026-04-13  
**Testato con:** Aspose.Tasks 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}