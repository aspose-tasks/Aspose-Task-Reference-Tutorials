---
title: Master Maschere di struttura del progetto MS con Aspose.Tasks
linktitle: Raccolta di maschere di contorno in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come manipolare le maschere di contorno della raccolta di MS Project utilizzando Aspose.Tasks per .NET. Migliora la produttività con questo tutorial completo.
weight: 15
url: /it/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master Maschere di struttura del progetto MS con Aspose.Tasks

## introduzione
Stai cercando di sfruttare la potenza delle maschere di contorno di Microsoft Project utilizzando Aspose.Tasks per .NET? Sei arrivato nel posto giusto! In questo tutorial completo, ti guideremo attraverso il processo passo dopo passo, assicurandoti di acquisire una solida conoscenza di come manipolare in modo efficace le maschere di contorno nei tuoi progetti. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, questa guida ti fornirà le conoscenze e le competenze necessarie per ottimizzare il tuo flusso di lavoro.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di avere i seguenti prerequisiti:
### 1. Installazione di Aspose.Tasks per .NET
Assicurati di avere Aspose.Tasks per .NET installato nel tuo ambiente di sviluppo. È possibile scaricare la libreria dal sito Web Aspose[Qui](https://releases.aspose.com/tasks/net/).
### 2. Conoscenza di base di C# e .NET Framework
Acquisisci familiarità con il linguaggio di programmazione C# e .NET Framework, poiché questo tutorial utilizzerà entrambi.
### 3. File di progetto Microsoft
Tieni pronto un file Microsoft Project (MPP) a scopo di test. È possibile utilizzare un file esistente o crearne uno nuovo per la sperimentazione.
## Importa spazi dei nomi
Iniziamo importando gli spazi dei nomi necessari nel tuo progetto C#. Questo passaggio garantisce l'accesso alle classi e alle funzionalità richieste fornite da Aspose.Tasks per .NET.

Aggiungi i seguenti spazi dei nomi all'inizio del file di codice:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Ora suddividiamo l'esempio fornito in più passaggi e spieghiamo ogni passaggio in dettaglio:
## Passaggio 1: inizializzare l'oggetto del progetto
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Qui creiamo una nuova istanza di`Project` class e caricare un file Microsoft Project esistente denominato "OutlineValues2010.mpp".
## Passaggio 2: accedi ai codici struttura
```csharp
var outline = project.OutlineCodes[0];
```
Accediamo ai codici di contorno del progetto. I codici struttura sono campi personalizzati in Microsoft Project che consentono di classificare e organizzare le attività.
## Passaggio 3: Cancella maschere di contorno
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Questo passaggio garantisce che tutte le maschere di contorno esistenti vengano cancellate prima di procedere ulteriormente.
## Passaggio 4: crea maschere di contorno
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Creiamo nuove maschere di contorno e ne specifichiamo i tipi. In questo esempio creiamo una maschera di contorno valida e una sbagliata.
## Passaggio 5: inserisci e modifica le maschere
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Qui inseriamo una maschera sbagliata nella raccolta e modifichiamo la lunghezza di una maschera utilizzando il suo indice.
## Passaggio 6: rimuovere le maschere
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Rimuoviamo la maschera sbagliata dalla raccolta in base al suo indice.
## Passaggio 7: ripetere le maschere
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Questo ciclo esegue un'iterazione su ciascuna maschera di contorno nella raccolta e ne stampa le proprietà quali lunghezza, livello, separatore e tipo.
## Passaggio 8: copia le maschere in un altro progetto
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Infine, copiamo le maschere di contorno da un progetto all'altro, garantendo la coerenza tra progetti diversi.
## Conclusione
Congratulazioni! Hai imparato con successo come manipolare le maschere di contorno della raccolta di MS Project utilizzando Aspose.Tasks per .NET. Seguendo questo tutorial, ora disponi delle competenze per gestire in modo efficiente le maschere di contorno nei tuoi progetti, migliorando in definitiva la produttività e il flusso di lavoro.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks per .NET con diverse versioni di file Microsoft Project?
R: Sì, Aspose.Tasks per .NET supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### Q2: Aspose.Tasks per .NET è compatibile con .NET Core?
R: Sì, Aspose.Tasks per .NET è compatibile con .NET Core, consentendoti di utilizzarlo in applicazioni multipiattaforma.
### Q3: Posso personalizzare le proprietà delle maschere di contorno in base ai requisiti del mio progetto?
R: Assolutamente! Puoi personalizzare le maschere di contorno regolandone la lunghezza, il livello, il separatore e il tipo in base alle esigenze specifiche del tuo progetto.
### Q4: Aspose.Tasks per .NET fornisce documentazione e supporto?
R: Sì, Aspose.Tasks per .NET offre documentazione completa e supporto dedicato attraverso il proprio sito Web e[forum](https://forum.aspose.com/c/tasks/15).
### Q5: È disponibile una prova gratuita per Aspose.Tasks per .NET?
 R: Sì, puoi accedere a una prova gratuita di Aspose.Tasks per .NET dal loro[sito web](https://releases.aspose.com/tasks/net/). per esplorarne caratteristiche e funzionalità prima di effettuare un acquisto.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
