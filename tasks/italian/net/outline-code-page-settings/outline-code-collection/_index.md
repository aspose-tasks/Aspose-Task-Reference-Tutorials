---
title: Raccolta MS Project di codici di struttura in Aspose.Tasks
linktitle: Raccolta di codici di struttura in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come raccogliere codici di struttura di Microsoft Project utilizzando Aspose.Tasks per .NET. Questo tutorial completo fornisce istruzioni dettagliate.
weight: 11
url: /it/net/outline-code-page-settings/outline-code-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Raccolta MS Project di codici di struttura in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come raccogliere i codici di struttura di Microsoft Project utilizzando Aspose.Tasks per .NET. Suddivideremo il processo in istruzioni dettagliate per garantire chiarezza e comprensione.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Visual Studio: installa Visual Studio sul tuo sistema.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base della programmazione C#: la familiarità con C# sarà utile.

## Importa spazi dei nomi
Innanzitutto, importa gli spazi dei nomi necessari per accedere alla funzionalità Aspose.Tasks nel tuo progetto C#.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Passaggio 1: caricare il file di progetto
 Inizia caricando il file Microsoft Project utilizzando il file`Project` classe.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Passaggio 2: raccogli i codici di struttura
Creare un raccoglitore per raccogliere i codici di struttura dalle attività progettuali.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Passaggio 3: scorrere le attività e i codici di struttura
Scorrere le attività raccolte e delineare i codici, stampandone i dettagli.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Passaggio 4: aggiungere la definizione del codice di struttura personalizzato
Aggiungere una definizione di codice di struttura personalizzata al progetto.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Passaggio 5: crea e inserisci il codice di struttura
Crea un codice di struttura e inseriscilo in un'attività.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Passaggio 6: manipolare i codici di struttura
Manipolare i codici di struttura secondo necessità, ad esempio inserendo, rimuovendo o cancellando.
```csharp
// Esempio di manipolazione
// ...
// Inserisci il codice con 2 nella posizione giusta
task.OutlineCodes.Insert(2, code2);
// Controlla se il codice è stato inserito
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusione
In questo tutorial, abbiamo imparato come raccogliere codici di struttura di Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi gestire in modo efficace i codici di struttura all'interno dei tuoi progetti, migliorando l'organizzazione e la chiarezza.
## Domande frequenti
### D: Posso utilizzare Aspose.Tasks per .NET con altri linguaggi di programmazione?
R: Sì, Aspose.Tasks per .NET si rivolge principalmente alla piattaforma .NET, ma fornisce anche supporto per altri linguaggi di programmazione tramite Aspose.Tasks for Cloud.
### D: Esistono limitazioni sulla dimensione dei file di progetto che Aspose.Tasks per .NET può gestire?
R: Aspose.Tasks per .NET può gestire file di progetto di grandi dimensioni in modo efficiente, ma le prestazioni possono variare a seconda della complessità e delle dimensioni del file.
### D: Aspose.Tasks per .NET è compatibile con le ultime versioni di Microsoft Project?
R: Sì, Aspose.Tasks per .NET supporta varie versioni di Microsoft Project, comprese quelle più recenti.
### D: Posso personalizzare il formato di output quando lavoro con Aspose.Tasks per .NET?
R: Assolutamente, Aspose.Tasks per .NET fornisce ampie opzioni per personalizzare il formato di output in base alle proprie esigenze.
### D: Dove posso trovare ulteriore supporto o risorse per Aspose.Tasks per .NET?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per qualsiasi assistenza o domanda riguardante Aspose.Tasks per .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
