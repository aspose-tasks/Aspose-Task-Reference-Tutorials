---
date: 2026-03-19
description: Scopri come impostare la baseline del progetto e gestire efficacemente
  le baseline delle attività con Aspose.Tasks per .NET, garantendo un monitoraggio
  accurato dell'avanzamento del progetto.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Imposta la baseline del progetto – Gestione della baseline delle assegnazioni
  in Aspose.Tasks
url: /it/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Impostare la baseline del progetto – Gestione della baseline delle assegnazioni in Aspose.Tasks

## Introduzione

Quando si lavora su attività di gestione dei progetti, **impostare una baseline del progetto** è fondamentale per misurare i progressi effettivi rispetto al piano originale. Aspose.Tasks per .NET non solo consente di **impostare la baseline del progetto**, ma offre anche il pieno controllo sulle baseline delle assegnazioni, permettendo un monitoraggio preciso delle prestazioni. In questo tutorial percorreremo l'intero processo—caricamento di un progetto, impostazione di una baseline, lettura dei dati della baseline delle assegnazioni e confronto delle baseline—così potrai monitorare i tuoi progetti con sicurezza.

## Risposte rapide
- **Cosa significa “impostare la baseline del progetto”?** Registra i dati originali di programmazione e di costo per un confronto successivo con le prestazioni effettive.  
- **Quale metodo API imposta una baseline?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Le baseline delle assegnazioni richiedono una chiamata separata?** No, vengono memorizzate automaticamente quando imposti una baseline del progetto.  
- **Quali formati sono supportati?** MPP, XML, MPX e altri tramite Aspose.Tasks.  
- **È necessaria una licenza per la produzione?** Sì, è necessaria una licenza commerciale per l'uso non‑trial.

## Prerequisiti

- Conoscenza di base della programmazione C#.  
- Visual Studio (qualsiasi versione recente).  
- Libreria Aspose.Tasks per .NET aggiunta al tuo progetto. Puoi scaricarla da [qui](https://releases.aspose.com/tasks/net/).  
- Accesso a un file di progetto in formato MPP (ad esempio `AssignmentBaseline2007.mpp`).

## Importare gli spazi dei nomi

Aggiungi gli spazi dei nomi richiesti all'inizio del tuo file C# in modo che il compilatore sappia dove trovare le classi di Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Passo 1: Caricare il progetto e impostare la baseline del progetto

Per prima cosa, carica il file MPP esistente e poi chiama `SetBaseline` per **impostare la baseline del progetto** per l'intero progetto.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Passo 2: Leggere le informazioni della baseline delle assegnazioni

Dopo che la baseline è stata impostata, ogni assegnazione di risorsa contiene i propri record di baseline. Il ciclo qui sotto estrae e stampa tali dettagli, inclusi le date di inizio/fine, il costo, il lavoro e eventuali dati a intervalli di tempo.

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

## Passo 3: Confrontare le baseline delle assegnazioni

Puoi confrontare le baseline di diverse assegnazioni utilizzando gli operatori di uguaglianza e confronto integrati. Questo è utile quando devi rilevare spostamenti di programma o superamenti di costo tra le attività.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Problemi comuni e soluzioni

| Problema | Perché accade | Soluzione |
|----------|----------------|-----------|
| **I dati della baseline appaiono vuoti** | Il file di progetto è stato aperto in modalità sola lettura o la baseline non è mai stata impostata. | Chiama `project.SetBaseline(BaselineType.Baseline)` prima di leggere le baseline delle assegnazioni. |
| **`NullReferenceException` su `TimephasedData`** | Non tutte le baseline contengono voci a intervalli di tempo. | Controlla sempre `baseline.TimephasedData != null` (come mostrato nel codice). |
| **Recupero UID errato** | I valori UID differiscono tra le versioni del file. | Usa `ResourceAssignments.GetByUid` con l'UID corretto oppure itera per trovare l'assegnazione necessaria. |

## Domande frequenti

**Q: Aspose.Tasks può gestire più baseline per una singola assegnazione?**  
A: Sì, Aspose.Tasks supporta più baseline per ogni assegnazione, consentendo un monitoraggio completo dell'avanzamento del progetto nel tempo.

**Q: Aspose.Tasks è compatibile con vari formati di file di progetto oltre a MPP?**  
A: Sì, Aspose.Tasks supporta un'ampia gamma di formati di file di progetto, inclusi XML, MPX e MPP, garantendo la compatibilità con diversi strumenti di gestione dei progetti.

**Q: Posso modificare le informazioni della baseline programmaticamente usando Aspose.Tasks?**  
A: Assolutamente, Aspose.Tasks fornisce API estese per modificare le informazioni della baseline in modo dinamico secondo i requisiti del progetto, offrendo flessibilità e controllo sui processi di gestione del progetto.

**Q: Aspose.Tasks offre documentazione e risorse di supporto per gli sviluppatori?**  
A: Sì, gli sviluppatori possono accedere a documentazione completa, tutorial e forum sul sito web di Aspose.Tasks, facilitando un'integrazione fluida e la risoluzione dei problemi.

**Q: È disponibile una versione di prova per Aspose.Tasks per .NET?**  
A: Sì, gli sviluppatori possono ottenere una versione di prova gratuita di Aspose.Tasks per .NET da [qui](https://releases.aspose.com/), consentendo loro di valutare le funzionalità e le capacità prima di prendere una decisione d'acquisto.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-19  
**Testato con:** Aspose.Tasks 24.12 for .NET  
**Autore:** Aspose