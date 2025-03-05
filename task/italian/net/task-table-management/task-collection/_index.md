---
title: Gestione delle raccolte di attività in Aspose.Tasks
linktitle: Gestione delle raccolte di attività in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la gestione efficiente della raccolta di attività in Aspose.Tasks per .NET. Dalla creazione alla modifica, padroneggia facilmente la gestione dei progetti.
type: docs
weight: 18
url: /it/net/task-table-management/task-collection/
---
## introduzione
Se stai addentrandoti nel mondo della gestione dei progetti utilizzando .NET, Aspose.Tasks è la soluzione ideale per la gestione senza interruzioni delle raccolte di attività. Questo tutorial ti guiderà attraverso il processo di gestione efficiente delle raccolte di attività, assicurandoti di ottenere il massimo da questa potente libreria.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato sul tuo computer.
- Aspose.Tasks per la libreria .NET scaricata e referenziata nel progetto.
## Importa spazi dei nomi
Per iniziare, importiamo gli spazi dei nomi necessari nel tuo progetto C#:
```csharp
	using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi essenziali richiesti per una gestione efficace delle attività.
Ora suddividiamo il tutorial in una serie di passaggi, garantendo chiarezza e semplicità.
## Passaggio 1: creazione di un'istanza del progetto
```csharp
var project = new Project();
```
 Crea un'istanza di un nuovo progetto utilizzando il file`Project` classe.
## Passaggio 2: verificare la disponibilità della raccolta attività
```csharp
Console.WriteLine("Is task collection read-only: " + project.RootTask.Children.IsReadOnly);
```
Verifica se la raccolta di attività è di sola lettura.
## Passaggio 3: creazione di attività
```csharp
var task1 = project.RootTask.Children.Add();
task1.Set(Tsk.Name, "Task 1");
// Imposta proprietà aggiuntive dell'attività come inizio, durata e fine
// Passaggi simili per l'Attività 2 e l'Attività 3
```
Crea attività all'interno del progetto e imposta le loro proprietà.
## Passaggio 4: stampa delle attività del progetto
```csharp
foreach (var child in project.RootTask.Children)
{
    // Stampa i dettagli dell'attività
    Console.WriteLine("Task name: " + child.Get(Tsk.Name));
    Console.WriteLine("Task start: " + child.Get(Tsk.Start));
    Console.WriteLine("Task duration: " + child.Get(Tsk.Duration));
    Console.WriteLine("Task finish: " + child.Get(Tsk.Finish));
    Console.WriteLine();
}
```
Stampa i dettagli di ogni attività all'interno del progetto.
## Passaggio 5: modifica delle attività
```csharp
var task1ToEdit = project.RootTask.Children.GetById(1);
task1ToEdit.Set(Tsk.Name, "Task 1 (Edited)");
var taskToEdit2 = project.RootTask.Children.GetByUid(2);
taskToEdit2.Set(Tsk.Name, "Task 2 (Edited)");
```
Modifica le attività utilizzando il loro ID o UID.
## Passaggio 6: aggiunta di un'attività ricorrente
```csharp
var parameters = new RecurringTaskParameters
{
    // Imposta i parametri delle attività ricorrenti
};
var recurring = project.RootTask.Children.Add(parameters);
Console.WriteLine("Task name: " + recurring.Get(Tsk.Name));
```
Aggiungi un'attività ricorrente al progetto.
## Passaggio 7: conversione della raccolta in un elenco
```csharp
List<Task> tasks = project.RootTask.Children.ToList();
foreach (var task in tasks)
{
    task.Delete();
}
```
Converti la raccolta di attività in un elenco ed esegui operazioni su ciascuna attività.
## Conclusione
Gestire le raccolte di attività in Aspose.Tasks per .NET è un gioco da ragazzi con questa guida passo passo. Che tu stia creando, modificando o eliminando attività, Aspose.Tasks ti consente di gestire la gestione dei progetti senza problemi.
## Domande frequenti
### Aspose.Tasks è compatibile con .NET Core?
Sì, Aspose.Tasks supporta .NET Core, consentendoti di utilizzarlo in applicazioni multipiattaforma.
### Posso esportare le attività del progetto in diversi formati di file?
Assolutamente! Aspose.Tasks fornisce opzioni di esportazione versatili, tra cui PDF, XLSX e MPP.
### Come posso gestire le dipendenze tra le attività?
 È possibile impostare le dipendenze delle attività utilizzando il file`TaskLink` classe fornita da Aspose.Tasks.
### Esiste un forum della community per il supporto di Aspose.Tasks?
 Sì, puoi trovare supporto e interagire con la comunità su[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### Posso ottenere una licenza temporanea per Aspose.Tasks?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).