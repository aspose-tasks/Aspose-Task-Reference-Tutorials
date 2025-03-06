---
title: Gestisci la raccolta di attributi di MS Project in Aspose.Tasks
linktitle: Gestione della raccolta di attributi estesi in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente gli attributi estesi di MS Project utilizzando Aspose.Tasks per .NET. Manipola senza problemi gli attributi delle attività con una guida passo passo.
weight: 12
url: /it/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestisci la raccolta di attributi di MS Project in Aspose.Tasks

## introduzione
Stai cercando di gestire in modo efficiente gli attributi estesi di MS Project utilizzando Aspose.Tasks per .NET? In questo tutorial ti guideremo attraverso il processo passo dopo passo. Immergiamoci!
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Visual Studio: installa Visual Studio sul tuo sistema.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: familiarizza con le nozioni di base del linguaggio di programmazione C#.

## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nel tuo progetto:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Passaggio 1: caricare il file di progetto
Innanzitutto, carica il file MS Project utilizzando il seguente snippet di codice:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Passaggio 2: accesso all'attività e agli attributi estesi
Accedi a un'attività specifica e ai suoi attributi estesi:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Passaggio 3: cancella gli attributi estesi
Se necessario, cancella gli attributi estesi esistenti:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Passaggio 4: creare definizioni di attributi estesi
Crea definizioni per nuovi attributi estesi:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Passaggio 5: ripetere gli attributi estesi dell'attività
Itera sugli attributi estesi dell'attività:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Passaggio 6: aggiungi attributi estesi
Aggiungi nuovi attributi estesi all'attività:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Passaggio 7: lavorare con gli attributi estesi
Eseguire operazioni sugli attributi estesi come richiesto.
## Passaggio 8: rimuovere gli attributi estesi
Rimuovi gli attributi estesi per indice o in modo condizionale:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Passaggio 9: copiare gli attributi in un'altra attività
Copia gli attributi in un'altra attività all'interno dello stesso progetto o di un progetto diverso:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusione
La gestione delle raccolte di attributi estesi di MS Project diventa semplice con Aspose.Tasks per .NET. Seguendo i passaggi descritti in questo tutorial, puoi gestire in modo efficiente gli attributi estesi, migliorando le tue capacità di gestione del progetto.
## Domande frequenti
### D: Posso manipolare gli attributi estesi su più progetti?
R: Sì, puoi copiare attributi estesi tra attività in diversi progetti utilizzando Aspose.Tasks per .NET.
### D: Esistono limitazioni al numero di attributi estesi per attività?
R: Aspose.Tasks per .NET non impone limitazioni intrinseche al numero di attributi estesi per attività.
### D: Posso creare campi di attributi estesi personalizzati?
R: Assolutamente! Aspose.Tasks per .NET ti consente di definire campi di attributi estesi personalizzati su misura per i requisiti del tuo progetto.
### D: Aspose.Tasks per .NET supporta la lettura e la scrittura su file MS Project di varie versioni?
R: Sì, Aspose.Tasks per .NET supporta i formati di file MS Project in diverse versioni.
### D: È disponibile una versione di prova per Aspose.Tasks per .NET?
 R: Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
