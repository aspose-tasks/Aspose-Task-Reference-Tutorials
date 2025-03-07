---
title: Lavorare con l'operazione NOT in Aspose.Tasks
linktitle: Lavorare con l'operazione NOT in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come utilizzare l'operazione NOT in Aspose.Tasks per .NET per filtrare le attività in modo efficace. Migliora subito le tue capacità di gestione dei progetti.
weight: 20
url: /it/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lavorare con l'operazione NOT in Aspose.Tasks

## introduzione

In questo tutorial esploreremo come utilizzare l'operazione NOT in Aspose.Tasks per .NET. L'operazione NOT ci consente di invertire una condizione di filtro, permettendoci di selezionare elementi che non soddisfano un criterio specificato.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio: è necessaria un'installazione funzionante di Visual Studio da seguire insieme agli esempi di codice.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET dal[sito web](https://releases.aspose.com/tasks/net/).
3. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile per comprendere gli esempi di codice.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per il nostro codice:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Passaggio 1: imposta progetto e attività

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Iniziamo caricando un file di progetto denominato "Project2.mpp" utilizzando il file`Project` classe fornita da Aspose.Tasks. Assicurarsi che il file di progetto esista nella directory specificata.

## Passaggio 2: raccogliere le attività del progetto

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Qui creiamo un file`ChildTasksCollector` oggetto per raccogliere tutte le attività all'interno del progetto. Usiamo quindi`TaskUtils.Apply` metodo per attraversare la gerarchia delle attività del progetto e raccogliere tutte le attività figlio.

## Passaggio 3: definire la condizione del filtro

```csharp
var filter = new NullCondition();
```

 Definiamo una condizione di filtro utilizzando una classe personalizzata denominata`NullCondition`. Questa condizione seleziona le attività che hanno un valore nullo.

## Passaggio 4: applicare l'operazione NOT

```csharp
var condition = new Not<Task>(filter);
```

 Applichiamo l'operazione NOT alla condizione del filtro utilizzando il`Not<T>`classe fornita da Aspose.Tasks. Ciò invertirà la condizione del filtro, selezionando le attività che non hanno un valore nullo.

## Passaggio 5: filtra le attività

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Filtriamo le attività raccolte in base alla condizione applicata utilizzando un'applicazione personalizzata`Filter` metodo. Questo metodo accetta una raccolta enumerabile di attività e una condizione di filtro come parametri di input e restituisce un elenco di attività che soddisfano la condizione.

## Passaggio 6: elaborazione delle attività filtrate

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Collabora con altre proprietà...
}
```

Infine, iteriamo attraverso le attività filtrate ed eseguiamo le operazioni desiderate. In questo esempio, stampiamo semplicemente i nomi delle attività sulla console.

## Conclusione

In questo tutorial, abbiamo imparato come lavorare con l'operazione NOT in Aspose.Tasks per .NET. Invertendo le condizioni del filtro, possiamo scegliere selettivamente gli elementi che non soddisfano i criteri specificati, migliorando la nostra flessibilità nella manipolazione delle attività all'interno dei progetti.

## Domande frequenti

### Q1: posso utilizzare Aspose.Tasks con altri framework .NET?

R: Sì, Aspose.Tasks supporta vari framework .NET tra cui .NET Core, .NET Standard e .NET Framework.

### Q2: È disponibile una prova gratuita per Aspose.Tasks?

 R: Sì, puoi scaricare una versione di prova gratuita da[sito web](https://releases.aspose.com/).

### Q3: Come posso ottenere supporto per Aspose.Tasks?

 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi richiesta di supporto o assistenza tecnica.

### Q4: Posso acquistare una licenza temporanea per Aspose.Tasks?

 R: Sì, puoi acquistare una licenza temporanea da[pagina di acquisto](https://purchase.aspose.com/temporary-license/).

### Q5: dove posso trovare la documentazione completa per Aspose.Tasks?

 R: Puoi accedere alla documentazione completa su[Pagina della documentazione Aspose.Tasks](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
