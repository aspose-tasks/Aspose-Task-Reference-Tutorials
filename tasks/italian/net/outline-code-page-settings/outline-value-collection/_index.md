---
title: Gestisci i valori della struttura di MS Project con Aspose.Tasks
linktitle: Raccolta di valori di struttura in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire i valori di struttura nei file di Microsoft Project utilizzando Aspose.Tasks per .NET. Tutorial passo passo con esempi di codice.
type: docs
weight: 17
url: /it/net/outline-code-page-settings/outline-value-collection/
---
## introduzione
Aspose.Tasks per .NET fornisce un set completo di funzionalità per interagire con i file di Microsoft Project. Una di queste funzionalità è la capacità di gestire i valori di struttura all'interno di un progetto. In questo tutorial esploreremo come raccogliere e manipolare i valori di struttura utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Aspose.Tasks per .NET: è possibile scaricare la libreria da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: assicurati di avere installato un IDE adatto, come Visual Studio.
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.
## Importa spazi dei nomi
Nel file di codice C#, importa gli spazi dei nomi necessari per accedere alle classi e ai metodi Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;

```
Suddividiamo l'esempio fornito in più passaggi:
## Passaggio 1: caricare un file di progetto
 Innanzitutto, inizializza a`Project` oggetto caricando un file Microsoft Project esistente:
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## Passaggio 2: cancellare i valori di struttura esistenti
Successivamente, cancella tutti i valori di struttura esistenti dal progetto:
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## Passaggio 3: definire il nuovo codice struttura
Ora definisci un nuovo codice di struttura con una descrizione e un valore:
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## Passaggio 4: aggiorna il valore della struttura
Aggiorna il valore del codice di struttura:
```csharp
codeDefinition.Values[0].Value = "654321";
```
## Passaggio 5: ripetere i valori del contorno
Scorrere i valori del contorno e stamparne i dettagli:
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## Passaggio 6: manipolare i valori del contorno
Eseguire operazioni come rimuovere, inserire e copiare i valori del contorno secondo necessità:
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## Conclusione
In questo tutorial, abbiamo imparato come lavorare con i valori di struttura nei file di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo i passaggi forniti, puoi gestire in modo efficiente i valori di struttura all'interno dei tuoi progetti, consentendo maggiore controllo e flessibilità.
## Domande frequenti
### D: Posso manipolare più codici di struttura contemporaneamente?
R: Sì, puoi definire e manipolare più codici di struttura all'interno di un progetto utilizzando Aspose.Tasks.
### D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
R: Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi i formati MPP e XML.
### D: Come posso gestire gli errori mentre lavoro con i valori di struttura?
R: È possibile implementare meccanismi di gestione degli errori come i blocchi try-catch per gestire le eccezioni in modo corretto.
### D: Posso personalizzare l'aspetto dei valori di contorno nel mio progetto?
R: Sì, Aspose.Tasks fornisce API estese per personalizzare l'aspetto e il comportamento dei valori di struttura in base alle proprie esigenze.
### D: Dove posso trovare risorse aggiuntive e supporto per Aspose.Tasks?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto della comunità ed esplorare il[documentazione](https://reference.aspose.com/tasks/net/) per informazioni dettagliate su API e funzionalità.