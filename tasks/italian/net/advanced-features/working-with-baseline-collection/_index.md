---
date: 2026-04-06
description: Scopri come eliminare tutte le baseline e gestire le collezioni di baseline
  in Aspose.Tasks per .NET con esempi di codice passo‑passo.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Elimina tutte le baseline con la collezione di baseline di Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Elimina tutte le baseline con la collezione Baseline di Aspose.Tasks
url: /it/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Elimina tutte le baseline con la collezione Baseline di Aspose.Tasks

## Introduzione

Aspose.Tasks per .NET ti consente di manipolare i file Microsoft Project direttamente dalle tue applicazioni .NET. Una delle funzionalità più potenti è la capacità di **delete all baselines** per una risorsa, che è essenziale quando è necessario reimpostare i dati di monitoraggio di un progetto o avviare un nuovo periodo di baseline. In questo tutorial percorreremo l'intero processo—dalla lettura di un file di progetto alla rimozione di ogni baseline associata a una risorsa specifica—utilizzando spiegazioni chiare e conversazionali e codice C# pronto all'uso.

## Risposte rapide
- **What does “delete all baselines” do?** Rimuove ogni record di baseline memorizzato per una risorsa selezionata, cancellando i dati storici di costo e lavoro.  
- **Why would I need this?** Per reimpostare il monitoraggio dopo una modifica importante del progetto o quando le baseline originali non sono più rilevanti.  
- **Which library provides this capability?** Aspose.Tasks per .NET.  
- **Do I need a license?** È necessaria una licenza valida di Aspose.Tasks per l'uso in produzione; è disponibile una versione di prova gratuita.  
- **Is the code compatible with .NET 6+?** Sì, l'API funziona con .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6.

## Cos'è una baseline e perché eliminare tutte le baseline?

Una baseline cattura il piano originale per costo, lavoro e programma in un momento specifico. Nel corso della vita di un progetto potresti creare diverse baseline (Baseline 1, Baseline 2, ecc.) per confrontare l'avanzamento reale con diversi snapshot di pianificazione. Tuttavia, ci sono scenari—come una riorganizzazione del progetto o un nuovo inizio—in cui mantenere quelle baseline storiche diventa confuso. Eliminare tutte le baseline ti offre una base pulita, permettendoti di impostare nuove baseline che riflettano la realtà attuale.

## Prerequisiti

1. **Visual Studio** – qualsiasi edizione recente (Community, Professional o Enterprise).  
2. **Aspose.Tasks for .NET** – scaricalo dal [link di download](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – dovresti sentirti a tuo agio con variabili, cicli e output della console.  
4. **A Microsoft Project file** (`.mpp`) – verrà utilizzato un file di esempio chiamato *WorkWithBaselineCollection.mpp* negli esempi.

## Importa spazi dei nomi

Per prima cosa, importa gli spazi dei nomi necessari in modo che il compilatore sappia dove trovare le classi che utilizzeremo.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Passo 1: Carica il file di progetto

Iniziamo caricando un file Project esistente. Regola `DataDir` per puntare alla cartella che contiene il tuo file `.mpp`.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Passo 2: Ottieni la risorsa target

Per dimostrazione recuperiamo la risorsa con UID = 1. In uno scenario reale individueresti la risorsa per nome o un altro identificatore.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Passo 3: Visualizza le informazioni delle baseline esistenti

Prima di eliminare qualsiasi cosa, è utile vedere quali baseline sono attualmente associate alla risorsa. Questo ti dà la certezza di rimuovere i dati corretti.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Passo 4: Itera attraverso tutte le baseline

Qui iteriamo su ogni baseline, stampando metriche chiave come costo, lavoro e valore guadagnato (BCWP/BCWS). Questo passaggio è opzionale ma utile per scopi di logging o audit.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Elimina tutte le baseline

Ora eseguiamo l'azione principale: **delete all baselines** per la risorsa selezionata. Prima copiamo la collezione in una lista per evitare di modificare la collezione durante l'iterazione, quindi rimuoviamo ogni baseline una alla volta.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Dopo l'esecuzione di questo blocco, `resource.Baselines.Count` sarà `0`, confermando che tutti i record delle baseline sono stati cancellati.

## Problemi comuni e suggerimenti

- **NullReferenceException** – Assicurati che il file di progetto contenga effettivamente la risorsa che stai puntando; altrimenti `GetByUid` restituirà `null`.  
- **Licensing** – Senza una licenza valida di Aspose.Tasks vedrai una filigrana nell'output e funzionalità limitate.  
- **Performance** – Per progetti molto grandi, considera di iterare con `Parallel.ForEach` per accelerare il processo di rimozione, ma ricorda che la collezione sottostante non è thread‑safe.

## Domande frequenti

**Q: Aspose.Tasks può gestire file di progetto di grandi dimensioni?**  
A: Sì, Aspose.Tasks è ottimizzato per le prestazioni e può elaborare file `.mpp` multi‑gigabyte in modo efficiente.

**Q: La libreria è compatibile con tutte le versioni di Microsoft Project?**  
A: Aspose.Tasks supporta Project 2000 fino a Project 2024, coprendo sia i formati `.mpp` più vecchi sia i nuovi file basati su XML.

**Q: Posso personalizzare le baseline prima di eliminarle?**  
A: Assolutamente. Puoi leggere o modificare qualsiasi proprietà della baseline (costo, lavoro, date) prima di decidere di rimuoverla.

**Q: Aspose.Tasks funziona su piattaforme cloud?**  
A: Sì, l'API funziona su qualsiasi ambiente compatibile con .NET, inclusi Azure App Service, AWS Lambda (via .NET Core) e container Docker.

**Q: Dove posso chiedere aiuto alla community?**  
A: Visita il [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per entrare in contatto con altri sviluppatori e lo staff di Aspose.

## Conclusione

In questa guida abbiamo dimostrato come **delete all baselines** da una risorsa usando Aspose.Tasks per .NET. Seguendo il codice passo‑passo, puoi reimpostare i dati delle baseline, mantenere pulito il monitoraggio del progetto e preparare il tuo programma per un nuovo ciclo di pianificazione. Sentiti libero di sperimentare creando nuove baseline dopo l'eliminazione per vedere come la libreria aggiorna il file di progetto.

---

**Ultimo aggiornamento:** 2026-04-06  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}