---
title: Gestione delle attività in Aspose.Tasks
linktitle: Gestione delle attività in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la guida completa sulla gestione delle attività con Aspose.Tasks per .NET. Impara ad aggiungere, visualizzare parti divise, spostare, ottenere/impostare proprietà e altro ancora.
type: docs
weight: 15
url: /it/net/task-table-management/managing-tasks/
---
## introduzione
Se sei uno sviluppatore .NET che desidera gestire in modo efficiente le attività all'interno dei tuoi progetti, Aspose.Tasks per .NET fornisce una soluzione solida. Questo tutorial ti guiderà attraverso vari aspetti della gestione delle attività utilizzando Aspose.Tasks, offrendo istruzioni dettagliate ed esempi di codice. Che tu stia aggiungendo attività, visualizzando parti divise, spostando attività sotto lo stesso genitore, ottenendo/impostando proprietà di attività, ripetendo assegnazioni di attività, leggendo linee di base di attività o eliminando attività, questa guida ti copre.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET Library: assicurarsi di avere installato la libreria Aspose.Tasks per .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
2. Directory dei documenti: imposta una directory in cui verranno archiviati i documenti del progetto.
## Importa spazi dei nomi
Nel tuo progetto .NET, includi gli spazi dei nomi necessari per lavorare con Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Aggiunta di un'attività a un progetto
```csharp
// Crea un nuovo progetto
var project = new Project();
// Aggiungi un'attività
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Salva il progetto
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Visualizzazione delle parti divise dell'attività
```csharp
// Carica un progetto con attività divise
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Accedi a un'attività
var task = project.RootTask.Children.GetById(4);
// Visualizza le parti divise
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Spostare un'attività sotto lo stesso genitore
```csharp
try
{
    // Carica un progetto
    var project = new Project(DataDir + "MoveTask.mpp");
    // Sposta le attività con ID 5 prima dell'attività con ID 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Salvare il progetto modificato
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Ottenere/impostare le proprietà dell'attività
```csharp
// Crea un nuovo progetto
var project = new Project();
// Aggiungi un'attività e imposta le proprietà
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Raccogliere e visualizzare le proprietà dell'attività
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterazione delle assegnazioni delle attività
```csharp
// Carica un progetto con compiti
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Raccogli e visualizza le assegnazioni di attività
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Lettura delle linee di base dell'attività
```csharp
// Crea un nuovo progetto
var project = new Project();
// Aggiungi un'attività e imposta una linea di base
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Visualizza la durata prevista dell'attività
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Eliminazione di un'attività
```csharp
// Crea un nuovo progetto
var project = new Project();
// Aggiungi un'attività
var task = project.RootTask.Children.Add("Task");
// Visualizza il numero di attività prima e dopo l'eliminazione
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Elimina l'attività
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusione
La gestione delle attività in Aspose.Tasks per .NET è un processo continuo con gli esempi forniti. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, incorporare queste tecniche migliorerà le tue capacità di gestione dei progetti.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutti i framework .NET?
R: Sì, Aspose.Tasks supporta vari framework .NET, garantendo la compatibilità con il tuo ambiente di sviluppo.
### D: Come posso ottenere una licenza temporanea per Aspose.Tasks?
 R: Puoi ottenere una licenza temporanea di 30 giorni da[Qui](https://purchase.aspose.com/temporary-license/).
### D: Esistono limitazioni quando si lavora con attività divise in Aspose.Tasks?
 R: Le attività divise sono una funzionalità potente ed è possibile trovare una documentazione dettagliata[Qui](https://reference.aspose.com/tasks/net/).
### D: Posso personalizzare le proprietà dell'attività oltre a quanto mostrato negli esempi?
R: Assolutamente! Aspose.Tasks fornisce ampie opzioni di personalizzazione per le proprietà dell'attività. Controlla la documentazione per maggiori dettagli.
### D: Come posso ottenere supporto per Aspose.Tasks?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e le discussioni della comunità.