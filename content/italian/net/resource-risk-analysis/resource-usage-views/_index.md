---
title: Configurare le visualizzazioni di utilizzo delle risorse di MS Project in Aspose.Tasks
linktitle: Configurare le visualizzazioni di utilizzo delle risorse in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le visualizzazioni dell'utilizzo delle risorse di MS Project utilizzando Aspose.Tasks per .NET. Guida passo passo con esempi di codice inclusi.
type: docs
weight: 15
url: /it/net/resource-risk-analysis/resource-usage-views/
---
## introduzione
Microsoft Project (MS Project) è un potente strumento per la gestione dei progetti, che consente agli utenti di pianificare, eseguire e tenere traccia in modo efficiente dei propri progetti. Aspose.Tasks per .NET fornisce una perfetta integrazione con i file MS Project, consentendo agli sviluppatori di manipolare i dati del progetto a livello di codice. In questo tutorial, esploreremo come configurare le visualizzazioni dell'utilizzo delle risorse di MS Project utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: disporre di un file Microsoft Project (`.mpp`) contenente i dati del progetto con cui vuoi lavorare.

## Importa spazi dei nomi
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Passaggio 1: caricare il file di progetto
Innanzitutto, carica il file MS Project utilizzando Aspose.Tasks:
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## Passaggio 2: definire le opzioni di salvataggio
Definire le opzioni di salvataggio specificando le impostazioni di scala temporale e il formato di presentazione richiesti:
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## Passaggio 3: salvare il progetto con le visualizzazioni sull'utilizzo delle risorse
Salva il progetto con le visualizzazioni di utilizzo delle risorse configurate in un file PDF:
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## Conclusione
In questo tutorial, abbiamo imparato come configurare le visualizzazioni dell'utilizzo delle risorse di MS Project utilizzando Aspose.Tasks per .NET. Seguendo i passaggi forniti, gli sviluppatori possono integrare perfettamente Aspose.Tasks nelle loro applicazioni .NET per manipolare i dati del progetto in modo efficiente.

## Domande frequenti
### D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
R: Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi .mpp, .mpt, .xml e .mpx.
### D: Posso personalizzare ulteriormente le impostazioni della cronologia e il formato della presentazione?
R: Assolutamente, Aspose.Tasks offre flessibilità per personalizzare le impostazioni della scala temporale e i formati di presentazione in base alle proprie esigenze.
### D: Aspose.Tasks supporta altri formati di output oltre al PDF?
R: Sì, Aspose.Tasks supporta una varietà di formati di output tra cui XLSX, MPP, XML, HTML e altri.
### D: Esiste una community o un forum per il supporto di Aspose.Tasks?
 R: Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi domanda, discussione o necessità di supporto.
### D: Posso provare Aspose.Tasks prima dell'acquisto?
 R: Naturalmente puoi esplorare Aspose.Tasks con una prova gratuita disponibile[Qui](https://releases.aspose.com/).