---
title: Padroneggiare le maschere di codice WBS con Aspose.Tasks per .NET
linktitle: Raccolta di maschere di codice WBS in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Migliora la gestione dei progetti con Aspose.Tasks per .NET. Impara a creare, gestire e trasferire facilmente le maschere codice WBS in questo tutorial completo.
type: docs
weight: 15
url: /it/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## introduzione
Nel mondo dinamico della gestione dei progetti, organizzare le attività in modo efficiente è fondamentale. Aspose.Tasks per .NET fornisce una potente soluzione per gestire facilmente i codici della struttura di ripartizione del lavoro del progetto (WBS). In questo tutorial, approfondiremo la raccolta di maschere di codice WBS, esplorando come implementarle e manipolarle utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di intraprendere questo viaggio di codifica, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza pratica del linguaggio di programmazione C#.
-  Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. In caso contrario, scaricalo[Qui](https://releases.aspose.com/tasks/net/).
- Un editor di codice come Visual Studio per un'esperienza di codifica fluida.
## Importa spazi dei nomi
Per iniziare, importiamo gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Inizializzare la definizione del codice del progetto e della WBS
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definire le maschere del codice WBS
Cancella eventuali maschere codice esistenti e aggiungine di nuove:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Visualizza le informazioni sulle maschere del codice
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Aggiungi attività al progetto
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Recupera informazioni sull'attività
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipolare le maschere del codice
Rimuovi una maschera di codice e assicurati che venga rimossa:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Copia le maschere del codice in un altro progetto
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Visualizza le maschere del codice in un altro progetto
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Aggiungi attività all'altro progetto
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Visualizza i codici WBS nell'altro progetto
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusione
Con Aspose.Tasks per .NET, la gestione dei codici WBS diventa un compito semplice. Questo tutorial ha trattato la creazione, la manipolazione e il trasferimento delle maschere di codice WBS, fornendoti una guida completa per migliorare la tua esperienza di gestione dei progetti.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri linguaggi di programmazione?
R: Aspose.Tasks supporta principalmente i linguaggi .NET, ma puoi esplorare le opzioni di interoperabilità con altri linguaggi.
### D: È disponibile una versione di prova per Aspose.Tasks per .NET?
 R: Sì, puoi scaricare la versione di prova.[Qui](https://releases.aspose.com/).
### D: Come posso chiedere aiuto o segnalare problemi con Aspose.Tasks per .NET?
 R: Visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto e discussioni.
### D: Qual è lo scopo dei codici WBS nella gestione dei progetti?
R: I codici WBS aiutano a organizzare e strutturare le attività del progetto in modo gerarchico, fornendo un approccio sistematico alla pianificazione del progetto.
### D: Posso personalizzare il formato dei codici WBS in Aspose.Tasks per .NET?
R: Assolutamente, hai il pieno controllo sul formato e sulla struttura dei codici WBS utilizzando Aspose.Tasks per .NET.