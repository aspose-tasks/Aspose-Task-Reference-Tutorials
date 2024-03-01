---
title: Raccolta di assegnazioni di risorse in Aspose.Tasks
linktitle: Raccolta di assegnazioni di risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le assegnazioni di risorse in Microsoft Project utilizzando Aspose.Tasks per .NET. Tutorial passo passo con esempi di codice.
type: docs
weight: 12
url: /it/net/resource-risk-analysis/resource-assignment-collection/
---
## introduzione
Benvenuti in questo tutorial completo sulla gestione delle assegnazioni di risorse in Microsoft Project utilizzando Aspose.Tasks per .NET. In questo tutorial, approfondiremo il processo passo dopo passo, assicurandoci di avere una solida conoscenza di come gestire le assegnazioni delle risorse in modo efficiente. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti guiderà attraverso tutto ciò che devi sapere.
## Prerequisiti
Prima di immergerci nel codice, assicurati di avere la seguente configurazione:
1.  Aspose.Tasks per .NET installato: assicurati di avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. In caso contrario, puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. Conoscenza di base di C#: questo tutorial presuppone che tu abbia una conoscenza di base del linguaggio di programmazione C#.
3. File Microsoft Project: tenere pronto un file Microsoft Project a scopo di test. Se non ne hai uno, puoi creare un file di esempio.

## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Passaggio 1: caricare il file di progetto
Inizia caricando il file Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Passaggio 2: aggiungi attività e risorsa
Ora aggiungiamo un'attività e una risorsa al progetto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Passaggio 3: assegnare la risorsa all'attività
Successivamente, assegneremo la risorsa all'attività:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Passaggio 4: lavorare con diversi tipi di assegnazione
Puoi anche lavorare con incarichi che coinvolgono unità o costi:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Imposta le proprietà per le assegnazioni con unità e costi in modo simile come mostrato nel passaggio 3
```
## Passaggio 5: stampa i compiti
Stampa i compiti per il progetto:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Stampa i dettagli del compito
}
```
## Passaggio 6: recuperare l'assegnazione tramite UID
Puoi recuperare le assegnazioni in base all'UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Passaggio 7: controlla lo stato di sola lettura
Verifica se la raccolta di assegnazioni di risorse è di sola lettura:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Passaggio 8: converti la raccolta in elenco e ripeti
Converti la raccolta in un elenco e ripeti su di esso:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusione
Congratulazioni! Hai imparato come gestire le assegnazioni di risorse in Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi manipolare in modo efficiente attività e risorse, rendendo la gestione del progetto un gioco da ragazzi.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con diverse versioni di file Microsoft Project?
R: Sì, Aspose.Tasks per .NET supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### D: È disponibile una versione di prova prima di acquistare Aspose.Tasks per .NET?
 R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto se riscontro problemi durante l'utilizzo di Aspose.Tasks per .NET?
 R: Puoi chiedere supporto al forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### D: Posso utilizzare licenze temporanee per Aspose.Tasks per .NET?
 R: Sì, sono disponibili licenze temporanee a scopo di valutazione. Puoi prenderne uno da[Qui](https://purchase.aspose.com/temporary-license/).
### D: Dove posso acquistare una licenza completa per Aspose.Tasks per .NET?
 R: Puoi acquistare una licenza completa dal negozio online Aspose[Qui](https://purchase.aspose.com/buy).