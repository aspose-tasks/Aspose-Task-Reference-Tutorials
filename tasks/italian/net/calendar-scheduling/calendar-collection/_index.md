---
title: Gestione della raccolta di calendari in Aspose.Tasks
linktitle: Gestione della raccolta di calendari in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente le raccolte di calendari in Aspose.Tasks per .NET. Crea, modifica e manipola i calendari con facilità.
type: docs
weight: 11
url: /it/net/calendar-scheduling/calendar-collection/
---
## introduzione

In questo tutorial esploreremo come gestire le raccolte di calendari in Aspose.Tasks per .NET. I calendari svolgono un ruolo cruciale nella gestione dei progetti, definendo giorni lavorativi, festivi ed eccezioni. Aspose.Tasks fornisce funzionalità robuste per manipolare i calendari all'interno dei tuoi progetti.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio: installa Visual Studio o qualsiasi altro IDE compatibile per lo sviluppo .NET.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per lavorare con Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Creazione di un nuovo calendario

###  Passaggio 1: inizializzare un nuovo file`Project` object.
```csharp
var project = new Project();
```

### Passaggio 2: aggiungi calendari alla raccolta di calendari del progetto.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Passaggio 3: scorrere i calendari e visualizzare i loro nomi.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Sostituzione di un calendario con un nuovo calendario

### Passaggio 1: carica un progetto esistente.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passaggio 2: rimuovi il calendario esistente (se esiste).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Passaggio 3: aggiungi un nuovo calendario.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Ottenere il calendario per nome o ID

### Passaggio 1: caricare il progetto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passaggio 2: recupera i calendari per nome o UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Passaggio 3: visualizza i dettagli del calendario.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterazione sui calendari

### Passaggio 1: caricare il progetto.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Passaggio 2: recupera il conteggio dei calendari.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Passaggio 3: scorre la raccolta del calendario e visualizza i nomi.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Creare un calendario standard

### Passaggio 1: inizializzare un nuovo progetto.
```csharp
var project = new Project();
```

### Passaggio 2: definire un nuovo calendario e renderlo standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Passaggio 3: salva il progetto.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Conclusione

La gestione delle raccolte di calendari in Aspose.Tasks per .NET è essenziale per una gestione efficace del progetto. Con le funzionalità fornite, puoi creare, modificare e manipolare in modo efficiente i calendari in base ai requisiti del tuo progetto.

## Domande frequenti

### Q1: posso creare giorni lavorativi personalizzati in Aspose.Tasks?

R1: Sì, puoi creare giorni lavorativi personalizzati aggiungendo eccezioni ai calendari.

### Q2: È possibile importare calendari da file Microsoft Project?

A2: Assolutamente, Aspose.Tasks supporta l'importazione di calendari da file Microsoft Project.

### Q3: Come posso rimuovere un calendario specifico da un progetto?

 R3: Puoi rimuovere un calendario recuperandolo dalla raccolta e quindi chiamando il`Remove` metodo.

### Q4: Aspose.Tasks supporta l'esportazione di calendari in diversi formati?

A4: Sì, Aspose.Tasks consente di esportare calendari in vari formati come XML, MPP, ecc.

### Q5: Posso personalizzare l'orario di lavoro per giorni specifici in un calendario?

R5: Certamente è possibile definire l'orario di lavoro per i singoli giorni utilizzando le eccezioni nel calendario.