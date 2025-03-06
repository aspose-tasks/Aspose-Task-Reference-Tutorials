---
title: Personalizza le colonne di visualizzazione delle risorse di MS Project in Aspose.Tasks
linktitle: Personalizzazione delle colonne di visualizzazione delle risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come personalizzare in modo efficiente le colonne di visualizzazione delle risorse di MS Project utilizzando Aspose.Tasks per .NET. Crea viste personalizzate per una migliore gestione dei progetti.
weight: 17
url: /it/net/resource-risk-analysis/resource-view-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Personalizza le colonne di visualizzazione delle risorse di MS Project in Aspose.Tasks

## introduzione
Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice. Un'attività comune nella gestione dei progetti è la personalizzazione delle visualizzazioni per visualizzare informazioni specifiche. In questo tutorial, esploreremo come personalizzare le colonne di visualizzazione delle risorse di MS Project utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Aspose.Tasks per .NET Library: puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: tieni a portata di mano un file MS Project di esempio per i test.
3. Ambiente di sviluppo: un ambiente di sviluppo configurato con .NET framework.
## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari nel nostro progetto:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Passaggio 1: caricare il file di progetto
Carica il file MS Project utilizzando l'API Aspose.Tasks:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Passaggio 2: ottieni la risorsa e definisci le opzioni
Successivamente, ottieni la risorsa di cui desideri personalizzare le colonne di visualizzazione e definisci le opzioni di salvataggio del PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Passaggio 3: definire colonne personalizzate
Ora definisci le colonne personalizzate per la visualizzazione delle risorse. Puoi specificare vari campi e persino utilizzare i delegati per calcoli personalizzati:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Passaggio 4: ripetizione delle colonne
Itera sulle colonne definite e visualizza le loro proprietà:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Passaggio 5: salva la visualizzazione personalizzata
Infine, imposta la visualizzazione personalizzata e salvala come file PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Seguendo questi passaggi, è possibile personalizzare in modo efficiente le colonne di visualizzazione delle risorse di MS Project utilizzando Aspose.Tasks per .NET.
## Conclusione
La personalizzazione delle colonne di visualizzazione delle risorse di MS Project è essenziale per visualizzare informazioni pertinenti su misura per le esigenze del tuo progetto. Con Aspose.Tasks per .NET, questa attività diventa semplice ed efficiente, consentendoti di creare visualizzazioni personalizzate senza sforzo.
## Domande frequenti
### Posso personalizzare le visualizzazioni per altri elementi oltre alle risorse?
Sì, Aspose.Tasks consente la personalizzazione di attività, assegnazioni e anche altri elementi del progetto.
### Aspose.Tasks supporta il salvataggio di visualizzazioni in formati diversi da PDF?
Sì, puoi salvare le visualizzazioni in vari formati come XLSX, HTML e immagini.
### È possibile applicare la formattazione alla visualizzazione personalizzata?
Assolutamente, Aspose.Tasks fornisce ampie opzioni di formattazione per migliorare l'aspetto delle tue visualizzazioni personalizzate.
### Posso aggiornare dinamicamente la visualizzazione personalizzata in base alla modifica dei dati del progetto?
Sì, puoi aggiornare e rigenerare la visualizzazione personalizzata ogni volta che cambiano i dati del progetto sottostante.
### Aspose.Tasks supporta lo sviluppo multipiattaforma?
Aspose.Tasks per .NET si rivolge principalmente alle piattaforme .NET, ma sono disponibili anche versioni per Java e altre piattaforme.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
