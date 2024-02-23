---
title: Colonna Visualizzazione assegnazione personalizzata in Aspose.Tasks
linktitle: Colonna Visualizzazione assegnazione personalizzata in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come aggiungere colonne di visualizzazione delle assegnazioni personalizzate in Aspose.Tasks per .NET per migliorare le funzionalità di gestione dei progetti.
type: docs
weight: 16
url: /it/net/advanced-features/assignment-view-column/
---
## introduzione

In questo tutorial esploreremo come aggiungere colonne personalizzate per le visualizzazioni di assegnazione utilizzando Aspose.Tasks per .NET. Le colonne personalizzate offrono flessibilità e consentono di visualizzare informazioni aggiuntive rilevanti per le esigenze di gestione del progetto.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Conoscenza base del linguaggio di programmazione C#.
2.  Aspose.Tasks per la libreria .NET installata. In caso contrario, puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
3. Un ambiente di sviluppo integrato (IDE) come Visual Studio.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per accedere alle classi e ai metodi richiesti per creare colonne di visualizzazione delle assegnazioni personalizzate:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Passaggio 1: caricare il progetto

 Per iniziare, carica il file di progetto utilizzando il file`Project` classe:

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Passaggio 2: crea le opzioni di salvataggio del foglio di calcolo

 Successivamente, crea un'istanza di`Spreadsheet2003SaveOptions` che ci consente di personalizzare le colonne della visualizzazione dei compiti:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Passaggio 3: definire la colonna personalizzata

 Ora definisci la tua colonna personalizzata creando un'istanza di`AssignmentViewColumn`Questa classe richiede il nome della colonna, la larghezza e una funzione delegata per convertire i dati dell'assegnazione in testo di colonna:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Passaggio 4: aggiungi colonna personalizzata alle opzioni

Aggiungi la colonna personalizzata alla raccolta di colonne della vista assegnazione delle opzioni di salvataggio:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Passaggio 5: scorrere i compiti

Scorri ogni assegnazione di risorse nel progetto e visualizza il testo della colonna personalizzata:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Passaggio 6: salva il progetto con colonne personalizzate

Infine, salva il progetto con le colonne della visualizzazione delle assegnazioni personalizzate:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere colonne di visualizzazione delle assegnazioni personalizzate utilizzando Aspose.Tasks per .NET. Le colonne personalizzate offrono flessibilità nella visualizzazione di informazioni aggiuntive su misura per i requisiti del progetto, migliorando le capacità di gestione del progetto.

## Domande frequenti

### Q1: posso aggiungere più colonne personalizzate alla visualizzazione delle assegnazioni?

 R1: Sì, puoi aggiungere più colonne personalizzate creando ulteriori istanze di`AssignmentViewColumn` e aggiungendoli al`Columns` collezione.

### Q2: Sono disponibili convertitori predefiniti per i campi di assegnazione comuni?

A2: Sì, Aspose.Tasks fornisce convertitori predefiniti per campi di assegnazione comuni, semplificando l'estrazione dei dati per le colonne personalizzate.

### Q3: posso personalizzare l'aspetto delle colonne personalizzate, ad esempio formattando il testo o applicando stili?

R3: Sì, puoi personalizzare l'aspetto delle colonne personalizzate modificando proprietà quali larghezza, carattere e allineamento.

### Q4: è possibile rimuovere le colonne predefinite dalla visualizzazione delle assegnazioni?

 R4: Sì, puoi rimuovere le colonne predefinite escludendole dal file`Columns` collection o impostandone la larghezza su zero.

### Q5: Aspose.Tasks supporta l'esportazione di progetti in altri formati oltre ai fogli di calcolo con colonne personalizzate?

A5: Sì, Aspose.Tasks supporta l'esportazione di progetti in vari formati come PDF, HTML e XML, consentendo opzioni versatili di reporting dei progetti.