---
title: Raccolta di definizioni di codice struttura in Aspose.Tasks .NET
linktitle: Raccolta di definizioni di codice struttura in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come manipolare le definizioni del codice di struttura nei documenti di Microsoft Project utilizzando Aspose.Tasks per .NET. Categorizzazione dei dati del tuo progetto senza sforzo.
type: docs
weight: 13
url: /it/net/outline-code-page-settings/outline-code-definition-collection/
---
## introduzione
Aspose.Tasks è una potente libreria .NET progettata per manipolare i documenti di Microsoft Project con facilità ed efficienza. Una delle sue caratteristiche principali è la capacità di lavorare con le definizioni del codice di contorno, consentendo agli utenti di organizzare e classificare i dati del progetto in modo efficace. In questo tutorial esploreremo come lavorare con le definizioni di codice di struttura utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di immergerci nel tutorial, assicurati di avere quanto segue:
1. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.
2. Visual Studio: installa Visual Studio o qualsiasi altro ambiente di sviluppo C# preferito.
3.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).

## Importa spazi dei nomi
Per iniziare, assicurati di importare gli spazi dei nomi necessari:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Passaggio 1: caricare un documento di Microsoft Project
Innanzitutto, carica un documento di Microsoft Project per iniziare a lavorare con le definizioni del codice di struttura:
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## Passaggio 2: accedere alle definizioni del codice struttura
Ora accediamo alle definizioni del codice di contorno all'interno del progetto:
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## Passaggio 3: aggiungere definizioni di codice di struttura personalizzate
È possibile aggiungere definizioni di codice di struttura personalizzate come segue:
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## Passaggio 4: modificare le definizioni del codice struttura
Modifica facilmente le definizioni dei codici di struttura esistenti:
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## Passaggio 5: rimuovere le definizioni del codice di struttura
Rimuovere le definizioni del codice di struttura quando non sono più necessarie:
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## Passaggio 6: salva le modifiche
Infine, salva le modifiche al documento di progetto:
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## Conclusione
In conclusione, Aspose.Tasks per .NET fornisce funzionalità complete per la gestione delle definizioni di codice di struttura nei documenti di Microsoft Project. Seguendo i passaggi descritti in questo tutorial, puoi manipolare in modo efficiente le definizioni del codice di struttura per organizzare e classificare i dati del tuo progetto in modo efficace.
## Domande frequenti
### D: Posso aggiungere più definizioni di codice di struttura a un singolo progetto?
 R: Sì, puoi aggiungere più definizioni di codice di struttura a un progetto in base alle tue esigenze. Usa semplicemente il`Add` per ogni definizione che desideri includere.
### D: È possibile rimuovere contemporaneamente tutte le definizioni del codice di struttura da un progetto?
 R: Sì, puoi cancellare tutte le definizioni del codice di struttura da un progetto utilizzando il file`Clear` metodo.
### D: Cosa succede se provo a modificare una definizione di codice di struttura di sola lettura?
R: Se la definizione di un codice di struttura è di sola lettura, non sarà possibile modificarla direttamente. Dovrai verificarne lo stato di sola lettura prima di tentare qualsiasi modifica.
### D: Esistono limitazioni al numero di definizioni di codice di struttura che posso aggiungere a un progetto?
R: Aspose.Tasks per .NET non impone limitazioni specifiche sul numero di definizioni di codice di struttura che è possibile aggiungere a un progetto. Tuttavia, considerare le implicazioni sulle prestazioni quando si lavora con un numero elevato di definizioni.
### D: Posso utilizzare le definizioni del codice di struttura per raggruppare le attività in base a criteri personalizzati?
R: Sì, le definizioni del codice di contorno ti consentono di classificare le attività in base a criteri personalizzati, fornendo flessibilità nell'organizzazione dei dati del progetto.## Codice sorgente completo