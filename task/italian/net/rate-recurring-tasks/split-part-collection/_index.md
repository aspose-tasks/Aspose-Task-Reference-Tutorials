---
title: Raccogli il progetto MS di parti divise in Aspose.Tasks
linktitle: Raccolta di parti divise in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come raccogliere parti divise in MS Project utilizzando Aspose.Tasks per .NET. Questo tutorial completo ti guida attraverso il processo passo dopo passo.
type: docs
weight: 19
url: /it/net/rate-recurring-tasks/split-part-collection/
---
## introduzione
In questo tutorial, approfondiremo come raccogliere parti divise in MS Project utilizzando Aspose.Tasks per .NET. Suddividere le attività in parti può essere un aspetto cruciale della gestione del progetto e Aspose.Tasks fornisce metodi convenienti per gestirlo in modo efficiente.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Installazione di Aspose.Tasks per .NET: assicurati di aver installato Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile poiché scriveremo frammenti di codice in C#.

## Importa spazi dei nomi
Nel tuo progetto C#, includi gli spazi dei nomi necessari:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## Passaggio 1: imposta il tuo progetto
Innanzitutto, crea un nuovo progetto nel tuo IDE preferito e assicurati che Aspose.Tasks per .NET venga fatto riferimento correttamente.
## Passaggio 2: inizializzare l'oggetto del progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
Inizializza un nuovo oggetto Project con il percorso del tuo file MS Project.
## Passaggio 3: recuperare l'attività e ripetere le parti divise
```csharp
var task = project.RootTask.Children.GetById(1);
// Itera su parti divise
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
Recupera l'attività dal progetto ed esegui l'iterazione sulle sue parti divise, stampando le date di inizio e fine.
## Passaggio 4: ottieni la parte divisa per indice
```csharp
// Ottieni la parte tramite indice
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
Recupera una parte divisa specifica per indice e stampa la sua data di inizio.

## Conclusione
La gestione delle parti divise nei file MS Project può migliorare significativamente l'efficienza della gestione del progetto. Aspose.Tasks per .NET semplifica questo processo fornendo API intuitive per gestire attività divise senza problemi.
## Domande frequenti
### D: Posso dividere le attività in modo dinamico durante il runtime?
R: Sì, puoi dividere le attività a livello di codice utilizzando Aspose.Tasks per .NET.
### D: Aspose.Tasks supporta tutte le versioni dei file MS Project?
R: Aspose.Tasks supporta varie versioni dei file MS Project, garantendo la compatibilità tra diverse piattaforme.
### D: È disponibile una versione di prova a scopo di test?
 R: Sì, puoi ottenere una versione di prova gratuita da[Qui](https://releases.aspose.com/) Per la valutazione.
### D: Come posso ottenere licenze temporanee per i miei progetti?
 R: È possibile acquistare licenze temporanee da[Qui](https://purchase.aspose.com/temporary-license/) per un utilizzo a breve termine.
### D: Dove posso cercare aiuto o supporto per quanto riguarda Aspose.Tasks?
 R: È possibile visitare il forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15)per chiedere assistenza alla comunità o al team di supporto Aspose.