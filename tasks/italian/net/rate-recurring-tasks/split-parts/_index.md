---
title: Gestione delle parti divise di MS Project in Aspose.Tasks
linktitle: Gestione delle parti divise in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le parti divise di MS Project in modo efficiente con Aspose.Tasks per .NET. Migliora il flusso di lavoro della gestione dei progetti.
weight: 18
url: /it/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione delle parti divise di MS Project in Aspose.Tasks


## introduzione
La gestione delle parti divise di MS Project può essere un aspetto cruciale della gestione del progetto quando si utilizza Aspose.Tasks per .NET. In questo tutorial esploreremo come gestire in modo efficace le parti divise utilizzando una guida passo passo.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1.  Installazione di Aspose.Tasks per .NET: scaricare e installare Aspose.Tasks per .NET dal[sito web](https://releases.aspose.com/tasks/net/).
   
2. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi
Nel codice C#, assicurati di importare gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Passaggio 1: creazione di un'istanza del progetto
```csharp
var project = new Project();
```
 Crea una nuova istanza di`Project` classe.
## Passaggio 2: impostazione delle date di inizio e fine del progetto
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Imposta le date di inizio e fine del progetto.
## Passaggio 3: aggiunta di un'attività
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Aggiungi una nuova attività al progetto.
## Passaggio 4: impostazione delle proprietà dell'attività
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Imposta proprietà come lo stato manuale, la data di inizio e la durata dell'attività.
## Passaggio 5: aggiunta di assegnazioni di risorse
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Aggiungi assegnazioni di risorse all'attività.
## Passaggio 6: impostazione delle proprietà dell'assegnazione
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Imposta proprietà come data di inizio, lavoro e data di fine per l'assegnazione.
## Passaggio 7: generazione di dati rapportati alla scala cronologica
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Genera dati rapportati alla scala cronologica per l'assegnazione in base al calendario del progetto.
## Passaggio 8: suddivisione del compito
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Suddividi l'attività in più parti entro l'intervallo di tempo specificato.
## Passaggio 9: iterazione su parti divise
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Itera sulle parti divise dell'attività e stampa le date di inizio e fine.

## Conclusione
Gestire in modo efficace le parti divise di MS Project in Aspose.Tasks per .NET è fondamentale per l'efficienza della gestione del progetto. Seguendo i passaggi descritti in questo tutorial, puoi gestire senza problemi le attività suddivise e migliorare il flusso di lavoro di gestione dei progetti.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri framework .NET?
R: Sì, Aspose.Tasks per .NET è compatibile con vari framework .NET tra cui .NET Core e .NET Standard.
### D: È disponibile una prova gratuita per Aspose.Tasks per .NET?
 R: Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### D: Aspose.Tasks per .NET supporta la gestione delle risorse?
R: Sì, Aspose.Tasks per .NET ti consente di gestire le risorse del progetto in modo efficiente.
### D: Posso personalizzare i calendari di progetto utilizzando Aspose.Tasks per .NET?
R: Assolutamente, puoi personalizzare i calendari di progetto in base ai requisiti del tuo progetto.
### D: Dove posso trovare supporto per Aspose.Tasks per .NET?
 R: Puoi trovare supporto e assistenza su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
