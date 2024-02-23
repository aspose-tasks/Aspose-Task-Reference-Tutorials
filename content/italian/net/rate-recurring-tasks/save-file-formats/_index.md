---
title: Salvataggio di file MS Project in vari formati in Aspose.Tasks
linktitle: Salvataggio di file in vari formati in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come salvare i file MS Project in vari formati utilizzando Aspose.Tasks per .NET. Semplici passaggi per una gestione efficiente del progetto.
type: docs
weight: 17
url: /it/net/rate-recurring-tasks/save-file-formats/
---
## introduzione
In questo tutorial esploreremo come salvare i file di Microsoft Project in vari formati utilizzando Aspose.Tasks per .NET. Aspose.Tasks è una potente API che consente agli sviluppatori di manipolare e gestire i file di progetto a livello di codice.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: configura un ambiente di sviluppo .NET, come Visual Studio.
3. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi
Assicurati di importare gli spazi dei nomi necessari all'inizio del file C#:
```csharp

using Aspose.Tasks.Saving;
```
## Passaggio 1: crea un oggetto di progetto
Innanzitutto, crea un oggetto Project e carica il file Microsoft Project.
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Passaggio 2: salva il progetto in formato CSV
Ora salviamo il progetto in formato CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Passaggio 3: esplora altri formati
 Aspose.Tasks supporta vari formati per il salvataggio di file di progetto, come XML, PDF, XLSX e altri. Puoi esplorare questi formati semplicemente modificando il file`SaveFileFormat` parametri nel`Save` metodo.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Seguendo questi passaggi, puoi facilmente salvare i file di Microsoft Project in vari formati utilizzando Aspose.Tasks per .NET.

## Conclusione
In questo tutorial, abbiamo imparato come salvare file MS Project in diversi formati utilizzando Aspose.Tasks per .NET. Aspose.Tasks semplifica il processo di manipolazione dei file di progetto a livello di codice, offrendo flessibilità ed efficienza agli sviluppatori.
## Domande frequenti
### D: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?
R: Aspose.Tasks supporta i formati Microsoft Project 2003 XML, Microsoft Project 2007 MPP e Microsoft Project 2010 MPP.
### D: Posso provare Aspose.Tasks prima dell'acquisto?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### D: Come posso ottenere supporto per Aspose.Tasks?
 R: Puoi ottenere supporto dal forum della community Aspose.Tasks.[Qui](https://forum.aspose.com/c/tasks/15).
### D: Sono disponibili licenze temporanee per Aspose.Tasks?
 R: Sì, sono disponibili licenze temporanee a scopo di valutazione. Puoi prenderne uno[Qui](https://purchase.aspose.com/temporary-license/).
### D: Qual è il prezzo per Aspose.Tasks?
 R: Le informazioni sui prezzi sono disponibili nella pagina di acquisto Aspose.Tasks[Qui](https://purchase.aspose.com/buy).