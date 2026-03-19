---
date: 2026-03-19
description: Scopri come aggiungere risorse al progetto, calcolare la durata delle
  attività con l'algoritmo ad albero di Aspose.Tasks e assegnare le risorse alle attività
  in .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aggiungi risorsa al progetto con algoritmo ad albero in Aspose.Tasks
url: /it/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere una Risorsa al Progetto con l'Algoritmo ad Albero in Aspose.Tasks

## Introduzione

In questo tutorial scoprirai **come aggiungere una risorsa al progetto** sfruttando il potente Algoritmo ad Albero fornito da Aspose.Tasks per .NET. Ti guideremo nella creazione di una gerarchia di attività, nel calcolo della durata delle attività e nell'assegnazione delle risorse alle attività—tutto in modo chiaro, passo dopo passo, che potrai copiare nella tua soluzione.

## Risposte Rapide
- **Cosa fa l'Algoritmo ad Albero?** Attraversa una gerarchia di attività per aggregare i valori di lavoro in modo efficiente.  
- **Quale operazione principale copre questa guida?** Aggiungere una risorsa a un progetto e aggiornare i totali del lavoro.  
- **Ho bisogno di una licenza?** È necessaria una licenza temporanea o completa per l'uso in produzione.  
- **Posso usarlo con .NET Core?** Sì, Aspose.Tasks supporta .NET Framework e .NET Core.  
- **Quanto tempo richiede l'implementazione?** Circa 10‑15 minuti per un file di progetto di base.

## Cos'è “add resource to project” in Aspose.Tasks?

Aggiungere una risorsa a un progetto significa creare un oggetto `Resource`, definire il suo tipo (ad es., work), e collegarlo a una o più attività tramite `ResourceAssignments`. Questo consente al pianificatore di calcolare lo sforzo, il costo e la durata complessiva del progetto.

## Perché usare l'Algoritmo ad Albero per i calcoli del lavoro delle risorse?

L'Algoritmo ad Albero percorre l'albero delle attività una sola volta, accumulando il lavoro dalle attività foglia fino alle loro attività riepilogo. Questo approccio è molto più efficiente rispetto all'iterazione su ogni attività individualmente, soprattutto in progetti grandi con gerarchie profonde. Garantisce inoltre che i valori di lavoro riepilogativi rimangano sincronizzati con i loro figli.

## Prerequisiti

1. **Visual Studio** – qualsiasi edizione recente (2019, 2022 o successiva).  
2. **Aspose.Tasks for .NET** – scaricalo da [qui](https://releases.aspose.com/tasks/net/).  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio con classi, oggetti e LINQ semplice.

## Importare gli Spazi dei Nomi

Nel tuo progetto C#, importa gli spazi dei nomi necessari per lavorare con le funzionalità di Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Ora, suddividiamo ogni esempio in più passaggi:

## Passo 1: Caricare il File di Progetto

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Carica il file di progetto in memoria usando la classe `Project`.

## Passo 2: Definire la Gerarchia delle Attività

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definisci la gerarchia delle attività aggiungendo attività padre e figlia.

## Passo 3: Impostare le Proprietà delle Attività (incluso **calcolare la durata dell'attività**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Qui **calcoliamo la durata dell'attività** convertendo le ore di lavoro in un oggetto `Duration` e poi derivando la data di fine.

## Passo 4: Aggiungere una Risorsa (**assegnare risorse alle attività**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Questo frammento **aggiunge una risorsa al progetto** e **assegna risorse alle attività** così il pianificatore sa chi è responsabile del lavoro.

## Passo 5: Applicare l'Algoritmo ad Albero

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inizializza la classe `WorkAccumulator` e applica l'Algoritmo ad Albero per raccogliere il lavoro comune attraverso la gerarchia.

## Passo 6: Aggiornare il Lavoro delle Attività

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aggiorna i valori di lavoro per le attività basandoti sulle informazioni raccolte.

## Problemi Comuni e Suggerimenti

- **Impostazioni del calendario mancanti:** Se la data di fine sembra errata, assicurati che il calendario del progetto sia configurato correttamente prima di chiamare `GetFinishDateByStartAndWork`.  
- **Tipo di risorsa non corrispondente:** Imposta sempre `Rsc.Type` su `ResourceType.Work` per le risorse basate sullo sforzo; altrimenti, l'accumulazione del lavoro potrebbe restituire zero.  
- **Suggerimento professionale:** Dopo aver aggiornato il lavoro, chiama `project.Save("UpdatedProject.mpp")` per salvare le modifiche.

## Conclusione

Seguendo questi passaggi ora sai come **aggiungere una risorsa al progetto**, **calcolare la durata dell'attività** e **assegnare risorse alle attività** usando l'Algoritmo ad Albero di Aspose.Tasks. Questo metodo semplifica la gestione della gerarchia e mantiene i valori di lavoro riepilogativi accurati con un codice minimo.

## FAQ's

### Q1: Cos'è Aspose.Tasks per .NET?

A1: Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di manipolare i file Microsoft Project programmaticamente usando C#.

### Q2: Posso scaricare una versione di prova gratuita di Aspose.Tasks per .NET?

A2: Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per .NET da [qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.Tasks per .NET?

A3: Puoi trovare la documentazione per Aspose.Tasks per .NET [qui](https://reference.aspose.com/tasks/net/).

### Q4: Come posso ottenere supporto per Aspose.Tasks per .NET?

A4: Per il supporto relativo a Aspose.Tasks per .NET, puoi visitare il [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: È disponibile una licenza temporanea per scopi di test?

A5: Sì, puoi ottenere una licenza temporanea per scopi di test da [qui](https://purchase.aspose.com/temporary-license/).

## Domande Frequenti

**Q: Posso usare questo approccio con un file di progetto grande esistente?**  
A: Assolutamente. L'Algoritmo ad Albero funziona su qualsiasi istanza di `Project`, indipendentemente dalle dimensioni.

**Q: L'algoritmo aggiorna anche i valori di costo?**  
A: L'esempio si concentra sul lavoro, ma puoi estenderlo al costo accumulando `Tsk.Cost` in modo simile.

**Q: Quali versioni di .NET sono supportate?**  
A: Aspose.Tasks supporta .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

**Q: Come gestire più risorse per attività?**  
A: Aggiungi ogni risorsa con `project.ResourceAssignments.Add(task, resource)`; l'accumulatore sommerà automaticamente il loro lavoro.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}