---
title: Tipo di calcolo in Aspose.Tasks
linktitle: Tipo di calcolo in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come personalizzare i calcoli dei valori nei progetti .NET con il tipo di calcolo nella libreria Aspose.Tasks.
weight: 30
url: /it/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tipo di calcolo in Aspose.Tasks

## introduzione

In questo tutorial esploreremo la funzionalità Tipo di calcolo in Aspose.Tasks per .NET. Aspose.Tasks è una potente libreria che consente agli sviluppatori .NET di lavorare con file Microsoft Project senza la necessità di Microsoft Project installato sui loro sistemi. Il Tipo di calcolo ci consente di definire come vengono calcolati i valori per le attività e le attività di riepilogo all'interno di un progetto.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

1. Conoscenza base di C# e framework .NET.
2. Visual Studio installato nel sistema.
3.  Aspose.Tasks per la libreria .NET installata. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).
4.  Accesso alla documentazione Aspose.Tasks per .NET come riferimento, disponibile[Qui](https://reference.aspose.com/tasks/net/).

## Importa spazi dei nomi

Prima di immergerti nell'esempio, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;


```

## Passaggio 1: crea un nuovo progetto

Innanzitutto, creiamo un nuovo oggetto di progetto:

```csharp
var project = new Project();
```

## Passaggio 2: aggiungi un'attività

Ora aggiungiamo un'attività al nostro progetto:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Passaggio 3: definire il tipo di calcolo per un attributo esteso

Creeremo una definizione di attributo esteso con il Tipo di calcolo impostato su Formula:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Passaggio 4: definire il tipo di calcolo per le righe di riepilogo

Successivamente, creeremo un'altra definizione di attributo esteso in cui i valori per le attività di riepilogo vengono calcolati utilizzando il tipo di rollup medio:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusione

In questo tutorial, abbiamo esplorato come lavorare con il tipo di calcolo in Aspose.Tasks per .NET. Definendo i tipi di calcolo per gli attributi estesi, possiamo personalizzare il modo in cui vengono calcolati i valori per le attività e le attività di riepilogo all'interno di un progetto, fornendo maggiore flessibilità e controllo.

## Domande frequenti

### Q1: Qual è il tipo di calcolo in Aspose.Tasks?

A1: Il tipo di calcolo in Aspose.Tasks determina il modo in cui vengono calcolati i valori per le attività e le attività di riepilogo all'interno di un progetto, offrendo opzioni come Formula e Rollup.

### Q2: Come imposto il tipo di calcolo per un attributo esteso?

A2: è possibile impostare il tipo di calcolo per un attributo esteso definendo di conseguenza la relativa proprietà CalculationType.

### Q3: Posso personalizzare il tipo di calcolo per le righe di riepilogo in un progetto?

A3: Sì, Aspose.Tasks ti consente di specificare il tipo di calcolo per le righe di riepilogo, consentendoti di personalizzare i calcoli dei valori in base alle tue esigenze.

### Q4: Sono disponibili diversi tipi di rollup per i calcoli delle attività di riepilogo?

A4: Sì, Aspose.Tasks fornisce vari tipi di rollup come media, somma e conteggio per il calcolo dei valori delle attività di riepilogo.

### Q5: Dove posso trovare più risorse su Aspose.Tasks per .NET?

 R5: È possibile esplorare la documentazione e i forum di supporto della community disponibili su[Aspose.Tasks per .NET](https://reference.aspose.com/tasks/net/) per una guida e un'assistenza complete.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
