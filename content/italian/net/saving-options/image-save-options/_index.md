---
title: Immagine Salva opzioni MS Project per Aspose.Tasks
linktitle: Opzioni di salvataggio immagine per Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come salvare le opzioni di MS Project come immagini utilizzando Aspose.Tasks per .NET. Segui la nostra guida passo passo per un'integrazione perfetta.
type: docs
weight: 11
url: /it/net/saving-options/image-save-options/
---

## introduzione
Nel mondo dello sviluppo software, gestire le attività del progetto in modo efficiente è fondamentale per una gestione di successo del progetto. Aspose.Tasks per .NET offre una potente soluzione per gli sviluppatori che lavorano con file Microsoft Project, consentendo loro di manipolare, convertire e gestire le attività di progetto senza problemi all'interno delle loro applicazioni .NET.
## Prerequisiti
Prima di immergerti nell'utilizzo di Aspose.Tasks per .NET per salvare le opzioni di MS Project come immagini, assicurati di disporre dei seguenti prerequisiti:
### 1. Installare Aspose.Tasks per .NET
 Per iniziare, è necessario che Aspose.Tasks per .NET sia installato nel tuo ambiente di sviluppo. È possibile scaricare la libreria da[sito web](https://releases.aspose.com/tasks/net/) e seguire le istruzioni di installazione fornite.
### 2. Ottieni una licenza (facoltativo)
 Sebbene Aspose.Tasks per .NET possa essere utilizzato senza licenza in modalità di valutazione, si consiglia di ottenere una licenza per la piena funzionalità e per rimuovere le limitazioni di valutazione. È possibile acquisire una licenza da[pagina di acquisto](https://purchase.aspose.com/buy) oppure optare per a[licenza temporanea](https://purchase.aspose.com/temporary-license/) a scopo di test.
### 3. Conoscenza di base dello sviluppo C# e .NET
È necessaria una conoscenza fondamentale del linguaggio di programmazione C# e del framework .NET per seguire gli esempi e integrare in modo efficace le funzionalità Aspose.Tasks nelle tue applicazioni.
## Importa spazi dei nomi
Prima di iniziare a salvare le opzioni di MS Project come immagini utilizzando Aspose.Tasks per .NET, assicuriamoci di importare gli spazi dei nomi necessari nel nostro progetto C#:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Passaggio 1: impostare il percorso della directory dei documenti
Assicurati di avere una directory designata per i tuoi documenti e imposta il percorso di conseguenza:
```csharp
String DataDir = "Your Document Directory";
```
## Passaggio 2: caricare il file MS Project
 Inizializzarne uno nuovo`Project` oggetto caricando il file MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Passaggio 3: definire le opzioni di salvataggio dell'immagine
 Crea un'istanza di`ImageSaveOptions` e specificare le impostazioni desiderate:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Passaggio 4: specificare le pagine da salvare
Se necessario, specificare le pagine da salvare. In questo esempio, stiamo aggiungendo la pagina 2:
```csharp
options.Pages.Add(2);
```
## Passaggio 5: salva l'immagine
Infine, salva le pagine selezionate come immagine con le opzioni specificate:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Conclusione
Aspose.Tasks per .NET semplifica il processo di lavoro con i file MS Project, consentendo agli sviluppatori di manipolare senza sforzo le attività del progetto. Seguendo i passaggi descritti in questo tutorial, puoi salvare in modo efficiente le opzioni di MS Project come immagini all'interno delle tue applicazioni .NET.
## Domande frequenti
### Q1: posso utilizzare Aspose.Tasks per .NET senza licenza?
R: Sì, puoi utilizzare Aspose.Tasks per .NET senza licenza in modalità di valutazione. Tuttavia, si consiglia di ottenere una licenza per la funzionalità completa e di rimuovere le limitazioni di valutazione.
### Q2: Come posso ottenere una licenza temporanea per i test?
 R: Puoi ottenere una licenza temporanea a scopo di test da[pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).
### Q3: Aspose.Tasks per .NET è compatibile con altri framework .NET?
R: Sì, Aspose.Tasks per .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Standard.
### Q4: Posso personalizzare ulteriormente le opzioni di salvataggio delle immagini?
R: Sì, puoi personalizzare le opzioni di salvataggio dell'immagine in base ai tuoi requisiti specifici, come la regolazione delle dimensioni della pagina, della risoluzione o del formato di output.
### Q5: Dove posso trovare supporto per Aspose.Tasks per .NET?
 R: Puoi trovare supporto e assistenza per Aspose.Tasks per .NET su[Forum](https://forum.aspose.com/c/tasks/15).