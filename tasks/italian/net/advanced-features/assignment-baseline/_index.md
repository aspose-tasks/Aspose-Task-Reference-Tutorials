---
title: Gestione della baseline di assegnazione in Aspose.Tasks
linktitle: Gestione della baseline di assegnazione in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente le linee di base delle assegnazioni con Aspose.Tasks per .NET, garantendo un monitoraggio accurato dell'avanzamento e delle prestazioni del progetto.
weight: 14
url: /it/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione della baseline di assegnazione in Aspose.Tasks

## introduzione

Quando si lavora su attività di gestione del progetto, la gestione delle basi di assegnazione è fondamentale per monitorare accuratamente i progressi. Aspose.Tasks per .NET fornisce un set completo di strumenti per gestire in modo efficiente le linee di base delle assegnazioni. In questo tutorial approfondiremo passo dopo passo il processo di gestione delle basi di assegnazione.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

- Conoscenza base del linguaggio di programmazione C#.
- Visual Studio installato nel sistema.
- Libreria Aspose.Tasks per .NET aggiunta al tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
- Accesso a un file di progetto in formato MPP.

## Importa spazi dei nomi

Per iniziare a lavorare con Aspose.Tasks, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Aggiungi i seguenti spazi dei nomi all'inizio del file C#:

```csharp
using Aspose.Tasks;
using System;


```

## Passaggio 1: caricare il progetto e impostare la baseline

 Innanzitutto, carica il file di progetto utilizzando il file`Project` classe da Aspose.Tasks. Quindi, imposta il tipo di baseline per il progetto utilizzando il file`SetBaseline` metodo.

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Passaggio 2: leggere le informazioni di base sull'assegnazione

Scorrere ogni assegnazione di risorse nel progetto e recuperare le informazioni di base per ogni assegnazione.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Passaggio 3: verificare l'uguaglianza della linea di base

Confronta le informazioni di base per diversi incarichi utilizzando vari metodi di confronto forniti da Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Controllare l'uguaglianza della linea di base
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Controllare il confronto di base
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Visualizza gli hashcode di base
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Conclusione

La gestione delle basi di assegnazione è parte integrante della gestione dei progetti, consentendo un monitoraggio accurato dei progressi e delle prestazioni. Con Aspose.Tasks per .NET, la gestione delle linee di base delle assegnazioni diventa semplificata ed efficiente, fornendo agli sviluppatori potenti strumenti per migliorare i flussi di lavoro di gestione dei progetti.

## Domande frequenti

### Q1: Aspose.Tasks può gestire più linee di base per una singola assegnazione?

R1: Sì, Aspose.Tasks supporta più linee di base per ogni assegnazione, consentendo un monitoraggio completo dell'avanzamento del progetto nel tempo.

### Q2: Aspose.Tasks è compatibile con vari formati di file di progetto diversi da MPP?

R2: Sì, Aspose.Tasks supporta un'ampia gamma di formati di file di progetto, inclusi XML, MPX e MPP, garantendo la compatibilità con vari strumenti di gestione dei progetti.

### Q3: posso modificare le informazioni di base a livello di codice utilizzando Aspose.Tasks?

A3: Assolutamente, Aspose.Tasks fornisce API estese per modificare dinamicamente le informazioni di base in base ai requisiti del progetto, offrendo flessibilità e controllo sui processi di gestione del progetto.

### Q4: Aspose.Tasks offre documentazione e risorse di supporto per gli sviluppatori?

R4: Sì, gli sviluppatori possono accedere a documentazione completa, tutorial e forum sul sito Web Aspose.Tasks, facilitando un'integrazione e una risoluzione dei problemi fluide.

### Q5: È disponibile una versione di prova per Aspose.Tasks per .NET?

 A5: Sì, gli sviluppatori possono ottenere una versione di prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/), consentendo loro di valutarne le caratteristiche e le capacità prima di prendere una decisione di acquisto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
