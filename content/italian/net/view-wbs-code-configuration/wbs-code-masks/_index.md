---
title: Configurazione dettagliata del codice WBS in Aspose.Tasks .NET
linktitle: Configura le maschere codice WBS in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora la configurazione dettagliata delle maschere codice WBS nei progetti .NET utilizzando Aspose.Tasks. Migliora facilmente le capacità di gestione dei progetti.
type: docs
weight: 14
url: /it/net/view-wbs-code-configuration/wbs-code-masks/
---
## introduzione
Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di manipolare in modo efficiente i dati di gestione dei progetti nelle applicazioni .NET. In questo tutorial, esploreremo il processo di configurazione delle maschere codice Work Breakdown Structure (WBS) utilizzando Aspose.Tasks.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
-  Aspose.Tasks per .NET Library: scarica e installa la libreria da[Aspose.Tasks per la documentazione .NET](https://reference.aspose.com/tasks/net/).
- Ambiente di sviluppo: assicurati di avere configurato un ambiente di sviluppo .NET funzionante.
- Directory dei documenti: scegli una directory sul tuo sistema per archiviare i file di progetto.
## Importa spazi dei nomi
Nel tuo progetto .NET, includi gli spazi dei nomi necessari per lavorare con Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Passaggio 1: crea un'istanza del progetto
Inizia creando una nuova istanza del progetto:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Passaggio 2: definire la definizione del codice WBS
Imposta la definizione del codice WBS per il tuo progetto:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Passaggio 3: aggiungere maschere codice WBS
Definisci le maschere codice WBS e aggiungile al progetto:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Passaggio 4: crea attività
Aggiungi attività al progetto:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Passaggio 5: ricalcolare
Ricalcolare il progetto per garantire che i codici WBS vengano applicati correttamente:
```csharp
project.Recalculate();
```
## Passaggio 6: visualizzare le informazioni sulla maschera WBS
Invia informazioni sulle maschere WBS alla console:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Passaggio 7: salva il progetto
Salvare il progetto con i codici WBS aggiunti:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Congratulazioni! Hai configurato correttamente le maschere codice WBS nel tuo progetto Aspose.Tasks.
## Conclusione
In questo tutorial, abbiamo esplorato il processo passo passo di configurazione delle maschere di codice WBS utilizzando Aspose.Tasks per .NET. Questa potente libreria fornisce agli sviluppatori un modo semplice per migliorare le capacità di gestione dei progetti all'interno delle loro applicazioni .NET.

## Domande frequenti
### Posso utilizzare Aspose.Tasks gratuitamente?
 Aspose.Tasks offre una prova gratuita, che puoi scaricare[Qui](https://releases.aspose.com/).
### Dove posso trovare ulteriore supporto?
 visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)per il sostegno della comunità.
### Come posso ottenere una licenza temporanea?
 Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### È disponibile una documentazione dettagliata?
 Sì, la documentazione completa è disponibile[Qui](https://reference.aspose.com/tasks/net/).
### Dove posso acquistare Aspose.Tasks?
 Acquista Aspose.Tasks[Qui](https://purchase.aspose.com/buy).