---
title: Utilizzo della raccolta di base in Aspose.Tasks
linktitle: Utilizzo della raccolta di base in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le linee di base in Aspose.Tasks per .NET in modo efficiente. Segui il nostro tutorial completo per una guida passo passo.
weight: 20
url: /it/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utilizzo della raccolta di base in Aspose.Tasks

## introduzione

Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di lavorare senza problemi con i file di Microsoft Project nelle loro applicazioni .NET. Tra le sue numerose funzionalità, fornisce un solido supporto per la gestione delle linee di base all'interno dei progetti. Le linee di base sono essenziali per la gestione del progetto in quanto consentono di confrontare il piano di progetto originale con lo stato attuale, consentendo un migliore monitoraggio e analisi dello stato di avanzamento del progetto.

## Prerequisiti

Prima di immergerci nel lavoro con le raccolte di base in Aspose.Tasks, assicurati di disporre dei seguenti prerequisiti:

1. Visual Studio: installa l'IDE di Visual Studio sul tuo sistema.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarizzare con il linguaggio di programmazione C#.
4. File Microsoft Project: tenere pronto un file Microsoft Project (.mpp) a scopo di test.

## Importa spazi dei nomi

Per iniziare a lavorare con le raccolte di base in Aspose.Tasks, è necessario importare i seguenti spazi dei nomi:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Ora suddividiamo ciascun esempio in più passaggi:

## Passaggio 1: caricare il file di progetto

Innanzitutto, carica il file Microsoft Project utilizzando Aspose.Tasks:

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Passaggio 2: ottieni la risorsa

Successivamente, recupera la risorsa desiderata dal progetto:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Passaggio 3: visualizzare le informazioni di base

Ora, visualizza le informazioni sulle linee di base associate alla risorsa:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Passaggio 4: scorrere le linee di base

Scorrere ogni linea di base associata alla risorsa e stampare le informazioni rilevanti:

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

## Passaggio 5: rimuovere le linee di base

Elimina tutte le baseline associate alla risorsa:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come lavorare con le raccolte di base in Aspose.Tasks per .NET. Seguendo la guida passo passo, puoi gestire facilmente le linee di base all'interno delle tue applicazioni .NET, consentendo un monitoraggio e un'analisi efficaci dei progetti.

## Domande frequenti

### Q1: Aspose.Tasks può gestire file di progetto di grandi dimensioni?

A1: Sì, Aspose.Tasks è ottimizzato per gestire file di progetto di grandi dimensioni in modo efficiente, garantendo prestazioni fluide.

### Q2: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?

A2: Aspose.Tasks supporta varie versioni di Microsoft Project, garantendo la compatibilità tra diversi ambienti.

### Q3: posso personalizzare le linee di base in Aspose.Tasks?

A3: Sì, è possibile personalizzare le linee di base in base ai requisiti del progetto utilizzando Aspose.Tasks per .NET.

### Q4: Aspose.Tasks offre supporto per piattaforme cloud?

R4: Sì, Aspose.Tasks fornisce supporto per l'integrazione con le piattaforme cloud più diffuse, offrendo flessibilità nella distribuzione.

### Q5: esiste un forum della community per gli utenti di Aspose.Tasks per cercare aiuto e condividere conoscenze?

 A5: Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) interagire con la comunità e ottenere assistenza da esperti.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
