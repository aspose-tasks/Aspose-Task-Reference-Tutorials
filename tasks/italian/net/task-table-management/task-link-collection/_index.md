---
title: Gestione dei collegamenti alle attività in Aspose.Tasks
linktitle: Gestione dei collegamenti alle attività in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la potenza di Aspose.Tasks per .NET nella gestione efficiente dei collegamenti alle attività del progetto. Segui la nostra guida passo passo per migliorare la tua esperienza di gestione dei progetti.
weight: 19
url: /it/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione dei collegamenti alle attività in Aspose.Tasks

## introduzione
Benvenuti nella guida passo passo sulla gestione dei collegamenti alle attività in Aspose.Tasks per .NET! I collegamenti alle attività svolgono un ruolo cruciale nella gestione dei progetti, consentendo di stabilire relazioni tra attività e creare dipendenze. In questo tutorial ti guideremo attraverso il processo di utilizzo delle raccolte di collegamenti attività utilizzando Aspose.Tasks.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1.  Libreria Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks. Puoi trovare la biblioteca[Qui](https://releases.aspose.com/tasks/net/).
2. File di progetto di esempio: preparare un file di progetto di esempio (ad esempio, "SampleProject.mpp") da seguire insieme agli esempi.
Ora cominciamo!
## Importa spazi dei nomi
Nel tuo progetto .NET, assicurati di importare gli spazi dei nomi necessari per lavorare con Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Passaggio 1: caricare il progetto e accedere alle attività
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
// Carica il progetto
var project = new Project(DataDir + "SampleProject.mpp");
// Accedi alle attività tramite ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Passaggio 2: crea collegamenti alle attività
Collega le attività insieme per stabilire le dipendenze:
```csharp
// Collega le attività utilizzando la dipendenza FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Passaggio 3: stampare i collegamenti alle attività
Stampa i collegamenti alle attività per il progetto:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Scorri i collegamenti alle attività
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Passaggio 4: modifica il collegamento all'attività
Modifica un collegamento all'attività tramite accesso all'indice:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Passaggio 5: rimuovere i collegamenti alle attività
Rimuovi tutti i collegamenti alle attività dal progetto:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Conclusione
Congratulazioni! Hai imparato con successo come gestire i collegamenti alle attività in Aspose.Tasks per .NET. Questa guida completa riguardava il caricamento di un progetto, la creazione di collegamenti alle attività, la stampa di collegamenti, la modifica dei collegamenti e la rimozione dei collegamenti alle attività.
Sentiti libero di esplorare ulteriori caratteristiche e funzionalità offerte da Aspose.Tasks per migliorare la tua esperienza di gestione dei progetti.
## Domande frequenti
### Aspose.Tasks è compatibile con tutte le versioni di .NET?
Sì, Aspose.Tasks è progettato per funzionare perfettamente con tutte le versioni di .NET.
### Posso creare tipi di collegamento attività personalizzati utilizzando Aspose.Tasks?
Attualmente, Aspose.Tasks supporta i tipi di collegamento attività standard e i tipi di collegamento personalizzati non sono disponibili.
### Come posso applicare vincoli alle attività in Aspose.Tasks?
 È possibile applicare vincoli utilizzando il comando`ConstraintType` proprietà del`Task` classe in Aspose.Tasks.
### Ci sono limitazioni sulla dimensione dei file di progetto che Aspose.Tasks può gestire?
Aspose.Tasks può gestire file di progetto di grandi dimensioni in modo efficiente con un impatto minimo sulle prestazioni.
### Esiste un forum della community per il supporto di Aspose.Tasks?
 Sì, puoi trovare supporto e interagire con la community su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
