---
title: Raccolta dei periodi di disponibilità in Aspose.Tasks
linktitle: Raccolta dei periodi di disponibilità in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire i periodi di disponibilità per le risorse in Aspose.Tasks per .NET. Questo tutorial passo passo ti guida attraverso l'aggiunta, l'aggiornamento e la rimozione dei periodi di disponibilità, garantendo un'efficace pianificazione delle risorse del progetto.
weight: 18
url: /it/net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Raccolta dei periodi di disponibilità in Aspose.Tasks

## introduzione

In questo tutorial esploreremo come lavorare con la raccolta del periodo di disponibilità di una risorsa in Aspose.Tasks per .NET. La gestione dei periodi di disponibilità è fondamentale per la gestione del progetto, poiché ci consente di definire quando le risorse sono disponibili per le attività all'interno di un progetto.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio: assicurati di avere Visual Studio installato sul tuo sistema.
2.  Aspose.Tasks per .NET: scaricare e installare la libreria Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Comprensioni di base: familiarità con C# e framework .NET.

## Importa spazi dei nomi

Innanzitutto, dobbiamo importare gli spazi dei nomi necessari nel nostro progetto:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Suddividiamo il codice di esempio in più passaggi e comprendiamo ciascuna parte:

## Passaggio 1: inizializzare il progetto e la risorsa

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Qui, stiamo caricando un file di progetto e ottenendo una risorsa specifica tramite il suo ID.

## Passaggio 2: Cancella i periodi di disponibilità esistenti

```csharp
resource.AvailabilityPeriods.Clear();
```

Cancelliamo tutti i periodi di disponibilità esistenti associati alla risorsa.

## Passaggio 3: aggiungi periodi di disponibilità

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Iteriamo attraverso una raccolta di periodi di disponibilità e li aggiungiamo alla risorsa.

## Passaggio 4: inserisci un nuovo periodo di disponibilità

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Creiamo un nuovo periodo di disponibilità per l'anno 2013 e lo inseriamo nella collezione.

## Passaggio 5: Visualizza i periodi di disponibilità

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Stampiamo il conteggio e i dettagli di ciascun periodo di disponibilità associato alla risorsa.

## Passaggio 6: copiare i periodi di disponibilità su un'altra risorsa

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Copiamo i periodi di disponibilità da una risorsa all'altra.

## Passaggio 7: aggiorna e rimuovi i periodi di disponibilità

```csharp
// Aggiorna le unità disponibili per un periodo specifico
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Rimuovere un periodo specifico
otherResource.AvailabilityPeriods.Remove(period2013);
```

Aggiorniamo le unità disponibili per un periodo e rimuoviamo periodi specifici dalla raccolta.

## Conclusione

In questo tutorial abbiamo imparato come lavorare con le raccolte dei periodi di disponibilità in Aspose.Tasks per .NET. La gestione della disponibilità delle risorse è essenziale per una pianificazione ed esecuzione efficace del progetto.

## Domande frequenti

### Q1: Posso aggiungere campi personalizzati ai periodi di disponibilità?

A1: No, i periodi di disponibilità in Aspose.Tasks per .NET non supportano i campi personalizzati.

### Q2: I periodi di disponibilità sono legati ad attività specifiche?

R2: No, i periodi di disponibilità sono associati alle risorse e definiscono quando sono disponibili per le attività in generale.

### Q3: Posso importare periodi di disponibilità da fonti esterne?

A3: Sì, è possibile importare periodi di disponibilità da varie origini dati utilizzando Aspose.Tasks per le API .NET.

### Q4: Come posso gestire i periodi di disponibilità sovrapposti?

A4: Aspose.Tasks per .NET non fornisce meccanismi incorporati per gestire periodi sovrapposti. Potrebbe essere necessario implementare una logica personalizzata per gestire tali scenari.

### D5: esiste un limite al numero di periodi di disponibilità che una risorsa può avere?

R5: Non esiste alcun limite predefinito al numero di periodi di disponibilità che una risorsa può avere, ma le prestazioni potrebbero peggiorare con un numero elevato di periodi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
