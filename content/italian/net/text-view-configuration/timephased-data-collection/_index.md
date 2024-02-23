---
title: Padroneggiare la raccolta dati temporale in Aspose.Tasks
linktitle: Raccolta di dati rapportati alla scala cronologica in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la raccolta dati rapportata alla scala cronologica in Aspose.Tasks per .NET. Guida passo passo, domande frequenti e altro ancora. Migliora le tue capacità di gestione dei progetti oggi stesso!
type: docs
weight: 15
url: /it/net/text-view-configuration/timephased-data-collection/
---
## introduzione
Stai cercando di sfruttare la potenza dei dati timephased nelle tue applicazioni .NET utilizzando Aspose.Tasks? Non guardare oltre! Questa guida completa ti guiderà attraverso il processo di raccolta dei dati in scala cronologica con Aspose.Tasks per .NET, assicurandoti di ottenere il massimo da questa potente libreria.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1.  Aspose.Tasks per .NET Library: scarica e installa la libreria da[Aspose.Tasks Documentazione .NET](https://reference.aspose.com/tasks/net/).
2. Ambiente di sviluppo .NET: assicurati di avere configurato un ambiente di sviluppo .NET funzionante.
3. La tua directory dei documenti: sostituisci il segnaposto "La tua directory dei documenti" negli snippet di codice con il percorso della directory dei tuoi documenti.
## Importa spazi dei nomi
Nel tuo progetto .NET, inizia importando gli spazi dei nomi necessari per sfruttare le funzionalità Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Crea un progetto e risorse
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Aggiungi attività al progetto
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Imposta le proprietà dell'attività...
var task2 = project.RootTask.Children.Add("Task 2");
// Imposta le proprietà dell'attività2...
```
## 3. Assegnare risorse alle attività
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Imposta proprietà dell'assegnazione...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Imposta proprietà assegnazione2...
```
## 4. Lavorare con dati rapportati alla scala cronologica
```csharp
// Imposta il contorno del lavoro sagomato
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Controlla se la raccolta dati rapportata alla scala cronologica è di sola lettura
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Cancella i dati generati rapportati alla scala cronologica
assignment.TimephasedData.Clear();
// Creare e aggiungere dati rapportati alla scala cronologica
var td = new TimephasedData
{
    // Imposta proprietà dei dati rapportati alla scala cronologica...
};
assignment.TimephasedData.Add(td);
// Aggiungi un elenco di dati rapportati alla scala cronologica
var list = new List<TimephasedData>();
// Aggiungi altri elementi di dati rapportati alla scala cronologica all'elenco...
assignment.TimephasedData.AddRange(list);
// Filtra i dati rapportati alla scala cronologica per tipo e intervallo di date
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Stampa dati filtrati rapportati alla scala cronologica...
```
## 5. Manipolare i dati rapportati alla scala cronologica
```csharp
//Aggiungere un elemento dati rapportato alla scala cronologica errato ed eliminarlo
var td4 = new TimephasedData
{
    // Imposta proprietà dei dati rapportati alla scala cronologica errati...
};
assignment.TimephasedData.Add(td4);
// Eliminare l'elemento dati rapportato alla scala cronologica errato
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iterare su tutti gli elementi rapportati alla scala cronologica
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Stampa i dettagli dell'articolo rapportati alla scala cronologica...
}
```
## 6. Copiare i dati rapportati alla scala cronologica in un'altra assegnazione
```csharp
// Copiare i dati rapportati alla scala cronologica in un'altra assegnazione
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Converti la raccolta in un semplice elenco
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Rimuovere gli elementi di dati rapportati alla scala cronologica uno per uno
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusione
In conclusione, questo tutorial ha fornito una procedura dettagliata dettagliata sulla raccolta di dati rapportati alla scala cronologica utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi integrare perfettamente questa funzionalità nei tuoi progetti, consentendo un monitoraggio efficace del tempo e una gestione delle risorse.
## Domande frequenti
### Posso utilizzare Aspose.Tasks per .NET con altri strumenti di gestione dei progetti?
Sì, Aspose.Tasks per .NET è progettato per funzionare con i più diffusi strumenti di gestione dei progetti e supporta vari formati di file.
### Esiste un limite al numero di risorse e attività che posso gestire con Aspose.Tasks?
Aspose.Tasks gestisce progetti di varie dimensioni e non esiste un limite rigido al numero di risorse e attività.
### Come posso ottenere supporto per eventuali problemi o domande relative a Aspose.Tasks per .NET?
 Per supporto, visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per connettersi con la comunità e ottenere assistenza.
### Posso provare Aspose.Tasks per .NET prima di acquistarlo?
 Sì, puoi esplorare le funzionalità di Aspose.Tasks per .NET accedendo a[prova gratuita](https://releases.aspose.com/).
### Dove posso acquistare una licenza per Aspose.Tasks per .NET?
 È possibile acquistare una licenza per Aspose.Tasks per .NET[Qui](https://purchase.aspose.com/buy).