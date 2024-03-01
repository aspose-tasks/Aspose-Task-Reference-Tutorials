---
title: Configurare le impostazioni della pagina MS Project con Aspose.Tasks
linktitle: Configurazione delle impostazioni della pagina in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le impostazioni della pagina MS Project utilizzando Aspose.Tasks per .NET. Personalizza orientamento, dimensioni e altro con semplici passaggi.
type: docs
weight: 20
url: /it/net/outline-code-page-settings/page-settings/
---
## introduzione
In questo tutorial, esamineremo il processo di configurazione delle impostazioni della pagina di Microsoft Project utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente API che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET: assicurati di aver installato Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo configurato con Visual Studio o qualsiasi altro IDE preferito per lo sviluppo .NET.

## Importazione di spazi dei nomi
Per iniziare, devi importare gli spazi dei nomi necessari nel tuo progetto. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi Aspose.Tasks richiesti per manipolare i file MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Passaggio 1: caricare il file di progetto
Innanzitutto, devi caricare il file MS Project per il quale desideri configurare le impostazioni della pagina.
```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Passaggio 2: accedi alle Impostazioni della pagina
Successivamente, accederai alle impostazioni della pagina del file di progetto.
```csharp
// Ottieni le impostazioni
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Passaggio 3: configura le impostazioni della pagina
Ora configuriamo varie proprietà delle impostazioni della pagina in base alle tue esigenze.
```csharp
// Imposta l'orientamento della pagina su verticale
settings.IsPortrait = true;
// Imposta il numero di pagine in larghezza da stampare
settings.PagesInWidth = 5;
// Imposta il numero di pagine in altezza da stampare
settings.PagesInHeight = 7;
// Imposta la percentuale del formato normale su cui regolare la stampa
settings.PercentOfNormalSize = 200;
// Imposta il formato della carta
settings.PaperSize = PrinterPaperSize.PaperB4;
// Imposta il numero della prima pagina per la stampa
settings.FirstPageNumber = 3;
```
## Passaggio 4: salva il file di progetto
Infine, salva il file di progetto con le impostazioni della pagina aggiornate.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Conclusione
In questo tutorial, abbiamo imparato come configurare le impostazioni della pagina di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi personalizzare facilmente l'orientamento della pagina, le dimensioni e altre opzioni di stampa in base alle tue esigenze.

## Domande frequenti
### D: Posso configurare le impostazioni della pagina per più file MS Project contemporaneamente?
R: Sì, puoi scorrere più file di progetto e applicare le stesse impostazioni di pagina a ciascuno di essi.
### D: È possibile ripristinare le impostazioni predefinite della pagina?
R: Assolutamente sì, puoi semplicemente omettere i passaggi di configurazione o ripristinare le impostazioni ai valori predefiniti.
### D: Esistono limitazioni sui formati carta supportati?
R: Aspose.Tasks supporta un'ampia gamma di formati carta, inclusi formati standard e personalizzati.
### D: Posso automatizzare il processo di configurazione delle impostazioni della pagina?
R: Certamente puoi integrare questa funzionalità nel flusso di lavoro della tua applicazione per automatizzare la configurazione delle impostazioni della pagina.
### D: Aspose.Tasks offre supporto per diversi formati di file oltre a .mpp?
R: Sì, Aspose.Tasks supporta vari formati di file come XML, MPT e HTML, tra gli altri.