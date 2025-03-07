---
title: Estrai le informazioni di intestazione e piè di pagina con Aspose.Tasks
linktitle: Informazioni sull'intestazione e sul piè di pagina in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Impara a estrarre informazioni su intestazione e piè di pagina dai file MS Project utilizzando Aspose.Tasks per .NET. Soluzione semplice, efficiente e intuitiva per gli sviluppatori.
weight: 29
url: /it/net/tasks-project-management/header-footer-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Estrai le informazioni di intestazione e piè di pagina con Aspose.Tasks

## introduzione
Aspose.Tasks per .NET è una potente libreria che consente agli sviluppatori di manipolare facilmente i file di Microsoft Project. In questo tutorial impareremo come recuperare le informazioni di intestazione e piè di pagina dai file MS Project utilizzando Aspose.Tasks.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Visual Studio: installa Visual Studio sul tuo sistema.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarità con il linguaggio di programmazione C#.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto C#. Ciò ti consentirà di accedere alle classi e ai metodi forniti dalla libreria Aspose.Tasks.
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Passaggio 1: inizializzare l'oggetto del progetto
 Per iniziare, è necessario inizializzare a`Project` oggetto caricando un file MS Project esistente.
```csharp
// Il percorso della directory dei documenti.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Passaggio 2: recuperare le informazioni di intestazione e piè di pagina
 Una volta caricato il file di progetto, puoi recuperare le informazioni di intestazione e piè di pagina utilizzando il file`PageInfo` proprietà.
```csharp
var info = project.DefaultView.PageInfo;
// Informazioni sull'intestazione
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Informazioni a piè di pagina
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
Seguendo questi semplici passaggi, puoi facilmente recuperare le informazioni di intestazione e piè di pagina dai file MS Project utilizzando Aspose.Tasks per .NET.

## Conclusione
In questo tutorial, abbiamo esplorato come estrarre le informazioni di intestazione e piè di pagina dai file MS Project utilizzando Aspose.Tasks per .NET. Questa potente libreria semplifica l'attività di lavoro con i file di progetto nelle applicazioni C#, fornendo agli sviluppatori robusti strumenti di manipolazione.
### Domande frequenti
### Posso modificare le informazioni di intestazione e piè di pagina utilizzando Aspose.Tasks?
Sì, puoi modificare le informazioni di intestazione e piè di pagina a livello di codice utilizzando Aspose.Tasks per .NET.
### Aspose.Tasks supporta altri formati di file di progetto oltre a MS Project?
Sì, Aspose.Tasks supporta vari formati di file di progetto, inclusi MPP, XML e MPX.
### È disponibile una prova gratuita per Aspose.Tasks?
 Sì, puoi scaricare una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Tasks?
 È possibile trovare la documentazione per Aspose.Tasks[Qui](https://reference.aspose.com/tasks/net/).
### Come posso ottenere supporto per Aspose.Tasks?
 È possibile ottenere supporto per Aspose.Tasks visitando il sito[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
