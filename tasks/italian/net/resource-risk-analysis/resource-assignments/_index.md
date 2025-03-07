---
title: Gestione delle assegnazioni di risorse di MS Project in Aspose.Tasks
linktitle: Gestione delle assegnazioni di risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le assegnazioni di risorse di MS Project in modo efficiente utilizzando Aspose.Tasks per .NET. Questo documento completo fornisce una guida passo passo per gli sviluppatori.
weight: 11
url: /it/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione delle assegnazioni di risorse di MS Project in Aspose.Tasks

## introduzione
In questo tutorial, approfondiremo come gestire le assegnazioni di risorse di Microsoft Project in modo efficiente utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente API che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice. Seguendo questi passaggi imparerai come gestire in modo efficace le assegnazioni delle risorse all'interno delle tue applicazioni .NET.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Tasks nel tuo progetto .NET. Ciò comprende:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Ora suddividiamo l'esempio fornito in più passaggi per una comprensione completa di come gestire le assegnazioni di risorse di MS Project utilizzando Aspose.Tasks.
## Passaggio 1: configura le impostazioni del progetto e del calendario
Per iniziare, crea una nuova istanza del progetto e configura le impostazioni del calendario del progetto:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Passaggio 2: aggiungi un'attività al progetto
Successivamente, aggiungi una nuova attività all'attività root del progetto:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Passaggio 3: creare un'assegnazione di risorse e generare dati rapportati alla scala cronologica
Ora crea una nuova assegnazione di risorse per l'attività e genera dati rapportati alla scala cronologica:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Passaggio 4: suddividere l'attività
Suddividi l'attività in più parti fornendo le date di inizio e fine:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Passaggio 5: impostare il contorno del lavoro
Imposta il tipo di distribuzione del lavoro per l'assegnazione:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Passaggio 6: salva il progetto
Infine, salva il file di progetto con le modifiche apportate:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusione
In conclusione, gestire le assegnazioni di risorse di Microsoft Project utilizzando Aspose.Tasks per .NET è un processo semplice. Seguendo i passaggi descritti in questa esercitazione è possibile gestire in modo efficiente le assegnazioni delle risorse all'interno delle applicazioni .NET.
## Domande frequenti
### Aspose.Tasks può gestire strutture di progetto complesse?
Sì, Aspose.Tasks fornisce funzionalità complete per gestire in modo efficiente strutture di progetti complessi.
### Aspose.Tasks è compatibile con diverse versioni di Microsoft Project?
Sì, Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo la compatibilità tra diversi ambienti.
### Posso personalizzare le assegnazioni delle risorse in base a requisiti specifici?
Assolutamente, Aspose.Tasks offre ampie opzioni di personalizzazione per l'assegnazione delle risorse per soddisfare esigenze specifiche del progetto.
### Aspose.Tasks supporta l'esportazione dei dati del progetto in altri formati?
Sì, Aspose.Tasks consente di esportare i dati del progetto in vari formati come XML, PDF e HTML, tra gli altri.
### Il supporto tecnico è disponibile per gli utenti Aspose.Tasks?
Sì, Aspose fornisce supporto tecnico dedicato attraverso il suo forum e altri canali per assistere gli utenti con qualsiasi domanda o problema.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
