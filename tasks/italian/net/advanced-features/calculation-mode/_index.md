---
title: Modalità di calcolo in Aspose.Tasks
linktitle: Modalità di calcolo in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire le modalità di calcolo in modo efficace in Aspose.Tasks per .NET per semplificare la pianificazione dei progetti e le dipendenze delle attività.
weight: 29
url: /it/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modalità di calcolo in Aspose.Tasks

## introduzione

Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di lavorare con i file di Microsoft Project a livello di codice nelle loro applicazioni .NET. Un aspetto cruciale dell'utilizzo dei file di progetto è la gestione delle modalità di calcolo, che determinano il modo in cui le attività e le pianificazioni del progetto vengono calcolate e aggiornate. In questo tutorial, approfondiremo le varie modalità di calcolo supportate da Aspose.Tasks per .NET e dimostreremo come utilizzarle in modo efficace.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base della programmazione C#: familiarizza con i concetti di programmazione C#.

## Importa spazi dei nomi

Prima di iniziare a lavorare con Aspose.Tasks per .NET, importiamo gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;


```

## Applicazione della modalità di calcolo automatico

### Passaggio 1: crea una nuova istanza del progetto

 Inizializzarne uno nuovo`Project` oggetto e impostarlo`CalculationMode` proprietà a`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Passaggio 2: imposta la data di inizio del progetto e aggiungi attività

Definisci la data di inizio del progetto e aggiungi attività ad esso.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Passaggio 3: collega le attività

Stabilire le dipendenze tra le attività.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Passaggio 4: verificare le date ricalcolate

Controlla se le date sono state ricalcolate automaticamente.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Aggiungi ulteriori verifiche secondo necessità
```

## Applicazione della modalità di calcolo manuale

### Passaggio 1: crea una nuova istanza del progetto

 Inizializzarne uno nuovo`Project` oggetto e impostarlo`CalculationMode` proprietà a`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Passaggio 2: imposta la data di inizio del progetto e aggiungi attività

Definisci la data di inizio del progetto e aggiungi attività ad esso.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Passaggio 3: verificare le proprietà dell'attività

Controlla se le proprietà dell'attività sono impostate correttamente in modalità manuale.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Aggiungi ulteriori verifiche secondo necessità
```

### Passaggio 4: collega le attività e verifica le date

Collega insieme le attività e controlla se le loro date non vengono ricalcolate.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Applicazione della modalità di calcolo Nessuna

### Passaggio 1: crea una nuova istanza del progetto

 Inizializzarne uno nuovo`Project` oggetto e impostarlo`CalculationMode` proprietà a`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Passaggio 2: aggiungi una nuova attività

Aggiungi una nuova attività al progetto.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Passaggio 3: verificare le proprietà dell'attività

Controlla se le proprietà dell'attività non vengono calcolate automaticamente.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Aggiungi ulteriori verifiche secondo necessità
```

## Conclusione

In questo tutorial, abbiamo esplorato le modalità di calcolo disponibili in Aspose.Tasks per .NET e abbiamo imparato come applicarle in scenari pratici. Sia che tu abbia bisogno della modalità di calcolo automatica, manuale o di nessuna, Aspose.Tasks offre la flessibilità per soddisfare le esigenze del tuo progetto.

## Domande frequenti

### Q1: Posso modificare dinamicamente la modalità di calcolo durante il runtime?

R1: Sì, puoi cambiare la modalità di calcolo di un progetto in qualsiasi momento durante il runtime modificando il file`CalculationMode` proprietà.

### Q2: Aspose.Tasks supporta altri formati di file di gestione dei progetti oltre a Microsoft Project?

R2: Aspose.Tasks si concentra principalmente sui formati di file Microsoft Project, ma supporta anche altri formati come Primavera P6 XML, Primavera DB e Asta Powerproject XML.

### Q3: Aspose.Tasks è adatto sia a progetti su piccola scala che a livello aziendale?

A3: Assolutamente! Aspose.Tasks è progettato per soddisfare le esigenze di progetti sia su piccola scala che a livello aziendale con le sue funzionalità complete e API robuste.

### Q4: posso integrare Aspose.Tasks con altre librerie e framework .NET?

A4: Sì, puoi integrare perfettamente Aspose.Tasks con altre librerie e framework .NET per migliorare la funzionalità delle tue applicazioni.

### Q5: È disponibile un forum della community o un canale di supporto per gli utenti di Aspose.Tasks?

 A5: Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e le discussioni della comunità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
