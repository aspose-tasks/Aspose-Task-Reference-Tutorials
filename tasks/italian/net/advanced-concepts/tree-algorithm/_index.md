---
title: Utilizzo dell'algoritmo dell'albero in Aspose.Tasks
linktitle: Utilizzo dell'algoritmo dell'albero in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come manipolare in modo efficace le gerarchie delle attività nei tuoi progetti .NET utilizzando l'algoritmo dell'albero di Aspose.Tasks.
weight: 13
url: /it/net/advanced-concepts/tree-algorithm/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utilizzo dell'algoritmo dell'albero in Aspose.Tasks

## introduzione

Aspose.Tasks per .NET fornisce potenti funzionalità per lavorare con attività, risorse e pianificazioni di gestione dei progetti. Una di queste funzionalità è l'algoritmo ad albero, che consente agli utenti di manipolare le gerarchie delle attività in modo efficiente. In questo tutorial esploreremo come utilizzare l'algoritmo dell'albero in Aspose.Tasks per .NET per raccogliere lavoro comune e aggiornare i valori di lavoro all'interno di un progetto.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: è necessaria la familiarità con il linguaggio di programmazione C# per seguire gli esempi.

## Importa spazi dei nomi

Nel tuo progetto C#, importa gli spazi dei nomi necessari per lavorare con le funzionalità Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Ora suddividiamo ciascun esempio in più passaggi:

## Passaggio 1: caricare il file di progetto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Caricare il file di progetto in memoria utilizzando il file`Project` classe.

## Passaggio 2: definire la gerarchia delle attività

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definire la gerarchia delle attività aggiungendo attività padre e figlio.

## Passaggio 3: impostare le proprietà dell'attività

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Imposta proprietà quali data di inizio, durata e data di fine per le attività.

## Passaggio 4: aggiungi risorsa

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Aggiungi risorse al progetto e assegnale alle attività secondo necessità.

## Passaggio 5: applicare l'algoritmo dell'albero

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Inizializza il`WorkAccumulator` classe e applicare l'algoritmo dell'albero per raccogliere il lavoro comune.

## Passaggio 6: aggiornare il lavoro dell'attività

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aggiorna i valori del lavoro per le attività in base alle informazioni raccolte.

## Conclusione

In questo tutorial, abbiamo imparato come utilizzare l'algoritmo dell'albero in Aspose.Tasks per .NET per manipolare le gerarchie delle attività in modo efficace. Seguendo la guida passo passo, puoi gestire in modo efficiente attività e risorse all'interno dei tuoi progetti.

## Domande frequenti

### Q1: Cos'è Aspose.Tasks per .NET?

A1: Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice utilizzando C#.

### Q2: Posso scaricare una versione di prova gratuita di Aspose.Tasks per .NET?

 A2: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.Tasks per .NET?

 A3: È possibile trovare la documentazione per Aspose.Tasks per .NET[Qui](https://reference.aspose.com/tasks/net/).

### Q4: Come posso ottenere supporto per Aspose.Tasks per .NET?

 R4: Per il supporto relativo ad Aspose.Tasks per .NET, è possibile visitare il sito[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: È disponibile una licenza temporanea a scopo di test?

 R5: Sì, puoi ottenere una licenza temporanea a scopo di test da[Qui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
