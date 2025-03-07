---
title: Gestione delle raccolte di progetti in Aspose.Tasks
linktitle: Gestione della raccolta di gruppi in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le raccolte di MS Project in modo efficiente utilizzando Aspose.Tasks per .NET. Segui la nostra guida passo passo.
weight: 26
url: /it/net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione delle raccolte di progetti in Aspose.Tasks

## introduzione
In questo tutorial esploreremo come gestire le raccolte di gruppo MS Project utilizzando Aspose.Tasks per .NET. La gestione delle raccolte di gruppo è fondamentale per organizzare e manipolare attività e risorse in modo efficiente all'interno del progetto.
## Prerequisiti
Prima di procedere con questo tutorial, assicurati di avere i seguenti prerequisiti:
1.  Aspose.Tasks for .NET Library: Scarica e installa la libreria Aspose.Tasks for .NET dal[Link per scaricare](https://releases.aspose.com/tasks/net/).
2. Conoscenza di base di C#: acquisisci familiarità con le nozioni di base del linguaggio di programmazione C# poiché questo tutorial prevede la codifica in C#.
3. Ambiente di sviluppo: configura un ambiente di sviluppo come Visual Studio o qualsiasi altro IDE che supporti lo sviluppo .NET.

## Importa spazi dei nomi
Innanzitutto, importiamo gli spazi dei nomi necessari per lavorare con le funzionalità Aspose.Tasks nel nostro codice C#.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Passaggio 1: caricare il progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Questo passaggio prevede il caricamento del file MS Project nell'oggetto del progetto Aspose.Tasks, consentendoci di eseguire operazioni su di esso.
## Passaggio 2: ripetere i gruppi di attività
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Qui iteriamo sui gruppi di attività all'interno del progetto, stampando dettagli come indice, nome e visibilità nel menu per ciascun gruppo.
## Passaggio 3: ripetere i gruppi di risorse
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Allo stesso modo, questo passaggio scorre sui gruppi di risorse, visualizzandone l'indice, il nome e la visibilità nel menu.
## Passaggio 4: cancella e copia i gruppi in un altro progetto
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Cancella i gruppi di altri progetti
otherProject.TaskGroups.Clear();
// Copia i gruppi in un altro progetto
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Qui cancelliamo i gruppi di un altro progetto e quindi copiamo i gruppi dal progetto originale ad esso.
## Passaggio 5: aggiungi un gruppo di attività personalizzato
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
In questo passaggio creiamo un gruppo di attività personalizzato e lo aggiungiamo all'altro progetto se non è già presente.
## Passaggio 6: rimuovi tutti i gruppi
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Infine, rimuoviamo tutti i gruppi dall'altro progetto.

## Conclusione
La gestione delle raccolte di progetti MS di gruppo in Aspose.Tasks per .NET è essenziale per organizzare e manipolare i dati del progetto in modo efficiente. Seguendo i passaggi descritti in questo tutorial, puoi gestire in modo efficace gruppi di attività e risorse all'interno dei tuoi progetti, migliorando la gestione complessiva del progetto.
## Domande frequenti
### Aspose.Tasks per .NET è compatibile con tutte le versioni di MS Project?
Aspose.Tasks per .NET supporta varie versioni di Microsoft Project, tra cui 2003, 2007, 2010, 2013, 2016 e 2019.
### Posso personalizzare le proprietà del gruppo utilizzando Aspose.Tasks per .NET?
Sì, puoi personalizzare le proprietà del gruppo come nome e visibilità utilizzando Aspose.Tasks per .NET.
### Aspose.Tasks per .NET offre compatibilità multipiattaforma?
Aspose.Tasks per .NET è destinato principalmente al framework .NET, ma può essere utilizzato in scenari multipiattaforma con .NET Core e .NET Standard.
### Come posso ottenere supporto per Aspose.Tasks per .NET?
 È possibile ottenere supporto per Aspose.Tasks per .NET tramite il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### È disponibile una versione di prova per Aspose.Tasks per .NET?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.Tasks per .NET da[sito web](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
