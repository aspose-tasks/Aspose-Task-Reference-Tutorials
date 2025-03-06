---
title: Gestione della durata in Aspose.Tasks
linktitle: Gestione della durata in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le durate in modo efficace in Aspose.Tasks per .NET con esercitazioni dettagliate.
weight: 30
url: /it/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione della durata in Aspose.Tasks

## introduzione

Gestire le durate in modo efficace è fondamentale nelle applicazioni di gestione dei progetti. Aspose.Tasks per .NET fornisce funzionalità robuste per gestire le durate in modo efficiente. In questo tutorial esploreremo vari aspetti della gestione della durata utilizzando Aspose.Tasks per .NET.

## Prerequisiti

Prima di immergerci nel tutorial, assicurati di avere i seguenti prerequisiti:

1. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# è essenziale per comprendere e implementare gli esempi.
2. Visual Studio: installa l'IDE di Visual Studio per creare ed eseguire applicazioni .NET.
3.  Aspose.Tasks per .NET: scarica e installa la libreria Aspose.Tasks per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/tasks/net/).

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per utilizzare le funzionalità Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Suddividiamo ciascun esempio in più passaggi in un formato di guida passo passo:

## Aggiornamento delle durate delle attività

### Passaggio 1: caricare il file di progetto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Passaggio 2: ottieni attività e durata

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Passaggio 3: durata dell'aggiornamento

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Passaggio 4: visualizza la durata aggiornata

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Sottrarre le durate delle attività

### Passaggio 1: caricare il file di progetto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Passaggio 2: ottieni attività e durata

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Passaggio 3: sottrai la durata

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Passaggio 4: visualizza la durata aggiornata

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Conversione della durata in TimeSpan

### Passaggio 1: caricare il file di progetto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Passaggio 2: ottieni attività e durata

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Passaggio 3: converti la durata in TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Conversione della durata in stringa

### Passaggio 1: caricare il file di progetto

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Passaggio 2: ottieni attività e durata

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Passaggio 3: converti la durata in stringa

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Conclusione

In questo tutorial, abbiamo coperto vari aspetti della gestione della durata in Aspose.Tasks per .NET. Comprendere e gestire in modo efficace le durate è vitale per una gestione di progetto di successo. Aspose.Tasks fornisce funzionalità complete per semplificare le attività di gestione della durata nelle applicazioni .NET.

## Domande frequenti

### Q1: Cos'è Aspose.Tasks per .NET?

A1: Aspose.Tasks per .NET è una potente libreria per lavorare con file Microsoft Project nelle applicazioni .NET.

### Q2: Aspose.Tasks può gestire strutture di progetto complesse?

A2: Sì, Aspose.Tasks può gestire facilmente strutture di progetto complesse, fornendo API estese per la manipolazione.

### Q3: Aspose.Tasks per .NET è compatibile con .NET Core?

A3: Sì, Aspose.Tasks per .NET è compatibile con .NET Core, consentendoti di utilizzarlo in applicazioni multipiattaforma.

### Q4: Aspose.Tasks supporta la lettura e la scrittura di file Microsoft Project?

R4: Sì, Aspose.Tasks supporta la lettura e la scrittura di file Microsoft Project in vari formati, inclusi MPP, XML e MPX.

### Q5: È disponibile una versione di prova per Aspose.Tasks per .NET?

A5: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
