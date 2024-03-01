---
title: Utilizzo dei periodi di disponibilità in Aspose.Tasks
linktitle: Utilizzo dei periodi di disponibilità in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire in modo efficiente i periodi di disponibilità delle risorse utilizzando Aspose.Tasks per .NET. Questa esercitazione fornisce una guida dettagliata per lavorare con i periodi di disponibilità nei progetti .NET.
type: docs
weight: 17
url: /it/net/advanced-features/working-with-availability-periods/
---
## introduzione

In questo tutorial esploreremo come lavorare con i periodi di disponibilità in Aspose.Tasks per .NET. I periodi di disponibilità sono cruciali per gestire le risorse in modo efficiente negli scenari di gestione dei progetti. Ti guideremo attraverso il processo passo dopo passo.

## Prerequisiti

Prima di iniziare, assicurati di possedere i seguenti prerequisiti:

1. Visual Studio: installa Visual Studio o qualsiasi altro IDE preferito per lo sviluppo .NET.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base della programmazione C#: sarà utile avere familiarità con le nozioni di base del linguaggio di programmazione C#.

## Importa spazi dei nomi

Prima di immergerti nel codice, assicurati di importare gli spazi dei nomi necessari:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Suddividiamo il codice di esempio in più passaggi:

## Passaggio 1: crea una nuova istanza del progetto

```csharp
var project = new Project();
```

Questa riga inizializza una nuova istanza della classe Project, che rappresenta un progetto in Aspose.Tasks.

## Passaggio 2: aggiungi una risorsa

```csharp
var resource = project.Resources.Add("Work Resource");
```

Qui aggiungiamo una nuova risorsa al progetto con il nome "Risorsa lavoro".

## Passaggio 3: definire i periodi di disponibilità

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Chiamiamo il`GetPeriods()` metodo per recuperare una raccolta di periodi di disponibilità.

## Passaggio 4: aggiungere periodi di disponibilità alla risorsa

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Iteriamo attraverso la raccolta dei periodi di disponibilità ottenuti nel passaggio precedente e li aggiungiamo alla risorsa.

## Passaggio 5: visualizzare i dettagli del periodo di disponibilità

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Infine, esaminiamo i periodi di disponibilità associati alla risorsa e stampiamo i relativi dettagli, tra cui la data di inizio, la data di fine e le unità disponibili.

## Conclusione

In questo tutorial, abbiamo imparato come lavorare con i periodi di disponibilità in Aspose.Tasks per .NET. Seguendo la guida passo passo, puoi gestire in modo efficiente la disponibilità delle risorse nelle tue applicazioni di gestione dei progetti.

## Domande frequenti

### Q1: posso utilizzare Aspose.Tasks per .NET in progetti commerciali?

 A1: Sì, Aspose.Tasks per .NET può essere utilizzato in progetti commerciali. È possibile acquistare una licenza[Qui](https://purchase.aspose.com/buy).

### Q2: È disponibile una prova gratuita per Aspose.Tasks per .NET?

A2: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET[Qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.Tasks per .NET?

 A3: È possibile trovare la documentazione[Qui](https://reference.aspose.com/tasks/net/).

### Q4: Come posso ottenere supporto per Aspose.Tasks per .NET?

 R4: Puoi ottenere supporto dal forum della community[Qui](https://forum.aspose.com/c/tasks/15).

### Q5: Offrite licenze temporanee per Aspose.Tasks per .NET?

 R5: Sì, sono disponibili licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).