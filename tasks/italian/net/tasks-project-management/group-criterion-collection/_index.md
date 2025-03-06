---
title: Gestisci i criteri del gruppo MS Project con Aspose.Tasks
linktitle: Gestione della raccolta di criteri di gruppo in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire la raccolta di Group Criterion MS Project utilizzando Aspose.Tasks per .NET. Guida passo passo per gli sviluppatori.
weight: 28
url: /it/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestisci i criteri del gruppo MS Project con Aspose.Tasks

## introduzione
Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice. In questo tutorial esploreremo come gestire la raccolta Group Criterion all'interno di MS Project utilizzando Aspose.Tasks.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1.  Aspose.Tasks per .NET: assicurati di avere la libreria Aspose.Tasks installata nel tuo progetto .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).

2. File Microsoft Project: tieni pronto un file Microsoft Project (MPP) con cui lavorare.

## Importa spazi dei nomi

Innanzitutto, devi importare gli spazi dei nomi necessari nel tuo codice C#. Questo passaggio è fondamentale per accedere alle funzionalità fornite da Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Passaggio 1: caricare il file di progetto

 Inizializzare a`Project` oggetto caricando il file MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Passaggio 2: accedere ai criteri del gruppo

Recupera il gruppo dal progetto e accedi ai suoi criteri.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Passaggio 3: ripetere i criteri di gruppo

Passa in rassegna ciascun criterio nel gruppo e visualizza le sue proprietà.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Passaggio 4: Cancellare i criteri del gruppo

Cancella i criteri di gruppo esistenti se non è di sola lettura.

```csharp
group.GroupCriteria.Clear();
```

## Passaggio 5: aggiungi un nuovo criterio

Crea un nuovo criterio di gruppo e aggiungilo al gruppo.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Passaggio 6: copiare i criteri in un altro gruppo

Copia i criteri da un gruppo all'altro.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusione

In questo tutorial, abbiamo imparato come gestire la raccolta Group Criterion MS Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi è possibile manipolare in modo efficace i criteri di gruppo all'interno dei file di Microsoft Project a livello di codice.

## Domande frequenti

### Q1: Aspose.Tasks è compatibile con tutte le versioni di Microsoft Project?

R: Sì, Aspose.Tasks supporta file Microsoft Project di varie versioni, tra cui 2003, 2007, 2010, 2013 e 2016.

### Q2: Posso applicare più criteri a un singolo gruppo?

R: Assolutamente, puoi aggiungere più criteri a un gruppo scorrendoli ciascuno e aggiungendoli di conseguenza.

### Q3: È disponibile una versione di prova per Aspose.Tasks?

 R: Sì, puoi ottenere una prova gratuita di Aspose.Tasks da[Qui](https://releases.aspose.com/).

### Q4: dove posso trovare la documentazione per Aspose.Tasks?

 R: Puoi fare riferimento alla documentazione[Qui](https://reference.aspose.com/tasks/net/).

### Q5: Come posso ottenere supporto in caso di problemi?

 R: Se hai domande o riscontri problemi, puoi chiedere supporto al forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
