---
title: Gestire i dati in modalità timephased con Aspose.Tasks per .NET
linktitle: Gestione dei dati rapportati alla scala cronologica in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora Aspose.Tasks per .NET per gestire facilmente dati rapportati alla scala cronologica, migliorare la pianificazione dei progetti e ottimizzare la gestione delle risorse. #Aspose #Tasks #Progetto MS
weight: 14
url: /it/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestire i dati in modalità timephased con Aspose.Tasks per .NET

## introduzione
Nel mondo della gestione dei progetti, la gestione efficace dei dati temporali è fondamentale per l'allocazione delle risorse, la stima dei costi e la pianificazione complessiva del progetto. Aspose.Tasks per .NET fornisce una potente soluzione per lavorare senza problemi con dati personalizzati rapportati alla scala cronologica. Questo tutorial ti guiderà attraverso il processo di gestione dei dati rapportati alla scala cronologica utilizzando Aspose.Tasks, consentendoti di ottimizzare la gestione delle risorse nei tuoi progetti.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
- Una conoscenza di base dei concetti di gestione del progetto.
-  Aspose.Tasks installato per .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
- Un editor di codice, come Visual Studio, per implementare gli esempi forniti.
## Importa spazi dei nomi
Nel tuo progetto .NET, assicurati di importare gli spazi dei nomi necessari per sfruttare le funzionalità Aspose.Tasks. Aggiungi le seguenti righe all'inizio del file di codice:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Ora, suddividiamo l'esempio fornito in più passaggi per guidarti nella gestione dei dati rapportati alla scala cronologica utilizzando Aspose.Tasks:
## Passaggio 1: impostare il progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Qui inizializziamo un nuovo progetto e impostiamo la sua modalità di calcolo.
## Passaggio 2: definire risorse e attività
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Creare risorse di lavoro e costi, nonché un'attività, per simulare una struttura di progetto.
## Passaggio 3: assegnare le risorse all'attività
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Assegnare risorse di lavoro e costi all'attività.
## Passaggio 4: aggiungi dati personalizzati rapportati alla scala cronologica
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Passaggi simili per costAssignment
costAssignment.TimephasedData.Clear();
```
Aggiungi dati personalizzati rapportati alla scala cronologica per le assegnazioni di lavoro e di costo.
## Passaggio 5: visualizzare i dati rapportati alla scala cronologica
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Visualizza informazioni rilevanti su ciascuna voce di dati rapportata alla scala cronologica
    }
}
```
Infine, visualizza i dati rapportati alla scala cronologica per ciascun compito.
#
## Conclusione
La gestione efficace dei dati temporali in Aspose.Tasks apre nuove possibilità per la pianificazione dettagliata dei progetti e la gestione delle risorse. Seguendo questa guida passo passo, hai imparato come manipolare i dati rapportati alla scala cronologica per soddisfare le esigenze specifiche dei tuoi progetti.
## Domande frequenti
### Posso utilizzare Aspose.Tasks per .NET con altri strumenti di gestione dei progetti?
Aspose.Tasks è progettato principalmente per lo sviluppo .NET. Tuttavia, le sue funzionalità possono integrare vari strumenti di gestione dei progetti.
### È disponibile una prova gratuita per Aspose.Tasks per .NET?
 Sì, puoi esplorare una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Tasks per .NET?
 Visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il sostegno della comunità.
### Che cos'è una licenza temporanea e come posso ottenerne una?
 Ulteriori informazioni sulle licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare la documentazione per Aspose.Tasks per .NET?
 Fare riferimento al completo[documentazione](https://reference.aspose.com/tasks/net/) per informazioni dettagliate.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
