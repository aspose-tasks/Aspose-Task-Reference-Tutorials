---
title: Utilizzo dell'assegnazione in Aspose.Tasks
linktitle: Utilizzo dell'assegnazione in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le assegnazioni di progetti in .NET utilizzando Aspose.Tasks. Esplora diversi contorni per la pianificazione delle risorse.
type: docs
weight: 13
url: /it/net/advanced-features/working-with-assignment/
---
## introduzione

In questo tutorial esploreremo come lavorare con le assegnazioni in Aspose.Tasks per .NET. Le assegnazioni sono cruciali nella gestione dei progetti poiché assegnano risorse alle attività, aiutando nella pianificazione e nel monitoraggio dei progressi. Ci concentreremo sulla generazione di dati di assegnazione delle risorse rapportati alla scala cronologica con vari contorni utilizzando Aspose.Tasks.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

1.  Installazione di Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
2. Comprensione di base di C# e .NET Framework: è necessaria la familiarità con il linguaggio di programmazione C# e i concetti di .NET Framework.

## Importa spazi dei nomi

Assicurati di importare gli spazi dei nomi necessari nel tuo progetto C#:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Passaggio 1: crea un progetto e un'attività

Iniziamo creando un nuovo progetto e aggiungendovi un'attività. Imposta la data di inizio, la durata e la data di fine dell'attività:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Passaggio 2: aggiungi una risorsa e assegnala all'attività

Successivamente, aggiungi una risorsa al progetto e assegnala all'attività creata in precedenza:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Passaggio 3: generazione di dati rapportati alla scala cronologica con contorni diversi

Ora generiamo dati rapportati alla scala cronologica con contorni diversi per l'assegnazione delle risorse:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Passaggio 4: modificare i contorni e generare dati

Possiamo modificare il tipo di contorno e generare di conseguenza dati temporali. Ecco alcuni esempi:

```csharp
// Cambia contorno
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Genera dati cronometrati e stampa
// Ripetere questo passaggio per altri tipi di contorno
```

## Conclusione

In questo tutorial, abbiamo imparato come lavorare con le assegnazioni in Aspose.Tasks per .NET. Abbiamo esplorato la generazione di dati di assegnazione delle risorse rapportati alla scala cronologica con vari contorni. Questa conoscenza può essere immensamente utile negli scenari di gestione dei progetti.

## Domande frequenti

### Q1: posso utilizzare Aspose.Tasks per pianificare le attività nella mia applicazione .NET?

A1: Sì, Aspose.Tasks fornisce API complete per la pianificazione e la gestione delle attività nelle applicazioni .NET.

### Q2: È disponibile una prova gratuita per Aspose.Tasks?

 A2: Sì, puoi usufruire di una prova gratuita da[Qui](https://releases.aspose.com/).

### Q3: Esistono limitazioni al numero di attività o risorse in Aspose.Tasks?

A3: Aspose.Tasks non impone alcuna limitazione al numero di attività o risorse che puoi gestire nei tuoi progetti.

### Q4: posso personalizzare i contorni per le assegnazioni di risorse in Aspose.Tasks?

R4: Sì, come dimostrato in questo tutorial, puoi impostare vari contorni come tartaruga, campana, picco, ecc., in base ai requisiti del tuo progetto.

### Q5: dove posso trovare supporto per le query relative ad Aspose.Tasks?

 R5: Puoi trovare supporto su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) dove esperti e membri della comunità si impegnano attivamente nelle discussioni.