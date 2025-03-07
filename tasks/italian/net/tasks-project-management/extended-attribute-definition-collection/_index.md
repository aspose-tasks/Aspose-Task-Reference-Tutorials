---
title: Definizioni degli attributi estesi principali Progetto MS in Aspose.Tasks
linktitle: Raccolta di definizioni di attributi estesi in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le definizioni di attributi estesi in Microsoft Project utilizzando Aspose.Tasks per .NET. Personalizza e migliora i dati del tuo progetto senza sforzo.
weight: 14
url: /it/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definizioni degli attributi estesi principali Progetto MS in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come lavorare con le definizioni di attributi estesi in Microsoft Project utilizzando Aspose.Tasks per .NET. Gli attributi estesi offrono un modo flessibile per personalizzare e migliorare i dati del progetto, consentendo agli utenti di aggiungere campi aggiuntivi oltre a quelli standard forniti per impostazione predefinita. Con Aspose.Tasks, puoi gestire facilmente questi attributi estesi per personalizzare le tue esigenze di gestione del progetto.
## Prerequisiti
Prima di procedere, assicurati di avere installati i seguenti prerequisiti:
- [.NET Framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks per la libreria .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari per accedere alle classi e ai metodi Aspose.Tasks nel tuo progetto .NET. Segui questi passi:
## Passaggio 1: apri il tuo progetto .NET
Apri il tuo progetto .NET nel tuo IDE preferito, come Visual Studio.
## Passaggio 2: aggiungere lo spazio dei nomi Aspose.Tasks
Aggiungi la seguente riga all'inizio del file di codice per importare lo spazio dei nomi Aspose.Tasks:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Ora, suddividiamo gli esempi di codice forniti in più passaggi per una comprensione completa:
## Passaggio 1: caricare il file di progetto
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Passaggio 2: Cancella le definizioni degli attributi estesi esistenti (facoltativo)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Passaggio 3: creare e aggiungere la definizione di attributi estesi per un'attività
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Passaggio 4: ripetere gli attributi estesi dell'attività
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Passaggio 5: creare e aggiungere la definizione di attributi estesi per una risorsa
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Passo 6: inserire una definizione di attributo esteso della risorsa
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Passaggio 7: rimuovere un attributo esteso tramite indice
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Conclusione
In questo tutorial abbiamo trattato le nozioni di base per lavorare con le definizioni di attributi estesi in Microsoft Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi è possibile gestire e personalizzare in modo efficiente gli attributi estesi per adattarli ai requisiti di gestione del progetto.
## Domande frequenti
### D: Posso modificare le definizioni degli attributi estesi esistenti?
R: Sì, puoi modificare le definizioni degli attributi estesi esistenti o crearne di nuovi in base alle tue esigenze.
### D: Gli attributi estesi sono supportati in tutte le versioni di Microsoft Project?
R: Sì, gli attributi estesi sono supportati nella maggior parte delle versioni di Microsoft Project, incluse quelle recenti.
### D: Posso utilizzare gli attributi estesi per calcolare i campi personalizzati?
R: Assolutamente, gli attributi estesi possono essere utilizzati per calcolare campi personalizzati in base a criteri specifici da te definiti.
### D: Aspose.Tasks è compatibile con altri framework .NET?
R: Aspose.Tasks è compatibile con vari framework .NET, garantendo flessibilità e facilità di integrazione.
### D: Dove posso trovare ulteriori risorse e supporto per Aspose.Tasks?
 R: Puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per supporto ed esplorare la documentazione[Qui](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
