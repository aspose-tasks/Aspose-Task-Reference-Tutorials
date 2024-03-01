---
title: Recupera le informazioni sul file MS Project in Aspose.Tasks
linktitle: Recupero delle informazioni sul file di progetto in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come recuperare le informazioni sui file di Microsoft Project utilizzando Aspose.Tasks per .NET. Guida passo passo con esempi di codice.
type: docs
weight: 19
url: /it/net/project-management-integration/project-file-information/
---
## introduzione
Benvenuti nella nostra guida passo passo sul recupero delle informazioni sui file di Microsoft Project utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente libreria che consente agli sviluppatori .NET di lavorare con i file di Microsoft Project a livello di programmazione, abilitando attività come la lettura, la scrittura e la manipolazione dei dati di progetto.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza di base di C# e .NET: questo tutorial presuppone una conoscenza di base del linguaggio di programmazione C# e del framework .NET.
2. Visual Studio: installa Visual Studio o qualsiasi altro IDE compatibile con lo sviluppo .NET.
3.  Aspose.Tasks per .NET Library: Scarica e installa Aspose.Tasks per .NET Library. È possibile trovare il collegamento per il download[Qui](https://releases.aspose.com/tasks/net/).
4. File Microsoft Project: tenere pronto un file Microsoft Project (formato XML in questo esempio) a scopo di test.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo progetto C# per lavorare con Aspose.Tasks:
## Passaggio 1: importare lo spazio dei nomi Aspose.Tasks
```csharp
using Aspose.Tasks;
using System;

```
## Recupero delle informazioni sul file MS Project
Ora suddividiamo il codice di esempio fornito in più passaggi:
## Passaggio 2: impostare la directory dei documenti
```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";
```
 Sostituire`"Your Document Directory"` con il percorso della directory contenente il file MS Project.
## Passaggio 3: recuperare le informazioni sul file di progetto
```csharp
var info = Project.GetProjectFileInfo(dataDir + "Project.xml");
```
 Questa riga di codice recupera le informazioni sul file di progetto specificato. Sostituire`"Project.xml"` con il nome del file MS Project.
## Passaggio 4: visualizzare le informazioni sul progetto
```csharp
Console.WriteLine("CanRead: " + info.CanRead);
Console.WriteLine("ProjectApplicationInfo: " + info.ProjectApplicationInfo);
Console.WriteLine("ProjectFileFormat: " + info.ProjectFileFormat);
```
Queste righe di codice visualizzano varie informazioni sul file MS Project come leggibilità, informazioni sull'applicazione e formato file.

## Conclusione
In questo tutorial, abbiamo imparato come recuperare le informazioni sui file di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi semplici passaggi, puoi integrare perfettamente questa funzionalità nelle tue applicazioni .NET, permettendoti di lavorare in modo efficiente con i file MS Project.
## Domande frequenti
### Aspose.Tasks può gestire diverse versioni dei file di Microsoft Project?
Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi i formati MPP e XML.
### Aspose.Tasks è compatibile con .NET Core?
Sì, Aspose.Tasks è compatibile sia con .NET Framework che con .NET Core.
### Posso manipolare i dati del progetto utilizzando Aspose.Tasks?
Assolutamente, Aspose.Tasks offre ampie funzionalità per leggere, scrivere e manipolare i dati di progetto a livello di codice.
### È disponibile una prova gratuita per Aspose.Tasks?
 Sì, puoi accedere a una prova gratuita di Aspose.Tasks[Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Tasks?
 È possibile ottenere supporto per Aspose.Tasks tramite il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).## Codice sorgente completo