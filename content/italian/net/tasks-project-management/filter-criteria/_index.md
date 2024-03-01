---
title: Padroneggiare i criteri di filtro di MS Project con Aspose.Tasks
linktitle: Criteri di filtro in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come implementare i criteri di filtro in MS Project utilizzando Aspose.Tasks per .NET. Aumenta l'efficienza della gestione dei progetti con l'analisi mirata dei dati.
type: docs
weight: 18
url: /it/net/tasks-project-management/filter-criteria/
---
## introduzione
Nel campo della gestione dei progetti, Microsoft Project è uno strumento valido, offrendo una vasta gamma di funzionalità per aiutare i pianificatori e i gestori di progetti. Tra le sue numerose funzionalità c'è la capacità di filtrare i dati del progetto, consentendo agli utenti di concentrarsi su aspetti specifici delle attività del proprio progetto. Tuttavia, padroneggiare queste capacità di filtraggio può essere un compito arduo senza la giusta guida. Questo tutorial mira a demistificare il processo fornendo una guida passo passo sull'implementazione dei criteri di filtro in MS Project utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# è necessaria per comprendere i concetti trattati in questo tutorial.
2.  Installazione di Aspose.Tasks per .NET: assicurati di avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
3. File Microsoft Project: tieni pronto un file Microsoft Project (ad esempio Project2003.mpp), che utilizzerai per implementare i criteri di filtro.

## Importa spazi dei nomi
Innanzitutto, è necessario importare gli spazi dei nomi necessari per lavorare con Aspose.Tasks per .NET. Segui questi passi:

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## Passaggio 1: caricare il file di progetto
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
 Spiegazione: Questa riga di codice inizializza una nuova istanza di`Project` classe e carica il file Microsoft Project specificato dal suo percorso.
## Passaggio 2: recupera il filtro attività
```csharp
var filter = project.TaskFilters.ToList()[1];
```
Spiegazione: qui recuperiamo un filtro attività dal progetto. Regolare l'indice (`[1]`) secondo le vostre esigenze per selezionare il filtro desiderato.
## Passaggio 3: visualizzare le righe dei criteri
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
Spiegazione: questa sezione scorre ciascuna riga di criteri del filtro e ne visualizza il campo, l'operazione, il test e i valori (se presenti).
## Passaggio 4: stampa dei criteri di filtro
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
Spiegazione: Stampa l'operazione dei criteri di filtro.
## Passaggio 5: visualizzare i dettagli dei criteri
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
Spiegazione: questa parte recupera e visualizza informazioni dettagliate su ciascuna riga di criteri, fornendo approfondimenti sulla configurazione del filtro.

## Conclusione
Padroneggiare i criteri di filtro in MS Project utilizzando Aspose.Tasks per .NET è un'abilità preziosa che può migliorare significativamente l'efficienza della gestione del progetto. Seguendo questo tutorial, hai imparato come manipolare i criteri di filtro a livello di codice, consentendoti di personalizzare le visualizzazioni del progetto in base alle tue esigenze specifiche.
## Domande frequenti
### D: Posso applicare più filtri contemporaneamente in MS Project?
R: Sì, puoi combinare più filtri per perfezionare ulteriormente i dati del tuo progetto.
### D: Aspose.Tasks supporta le versioni precedenti dei file Microsoft Project?
R: Sì, Aspose.Tasks fornisce compatibilità con le versioni precedenti, consentendoti di lavorare con varie versioni di file Microsoft Project.
### D: Aspose.Tasks è compatibile con altri framework .NET?
R: Aspose.Tasks supporta .NET Framework, .NET Core e .NET Standard, garantendo flessibilità tra diversi ambienti di sviluppo.
### D: Posso personalizzare i criteri di filtro in base alle condizioni dinamiche?
R: Assolutamente, puoi regolare a livello di codice i criteri di filtro in base a parametri dinamici, consentendo l'analisi adattiva dei dati di progetto.
### D: Dove posso chiedere assistenza se riscontro problemi con Aspose.Tasks?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per cercare supporto dalla comunità o contattare direttamente il supporto di Aspose.Tasks per assistenza personalizzata.