---
date: 2026-03-21
description: Scopri come gestire i periodi di disponibilità delle risorse e ottenere
  una efficace disponibilità delle risorse di progetto con Aspose.Tasks per .NET.
  Questa guida passo‑passo mostra come aggiungere, aggiornare e rimuovere i periodi
  di disponibilità.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Disponibilità delle risorse di progetto – Gestione dei periodi di disponibilità
  in Aspose.Tasks
url: /it/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Disponibilità delle risorse di progetto: raccolta di periodi di disponibilità in Aspose.Tasks

Gestire la **disponibilità delle risorse di progetto** è una parte fondamentale di una pianificazione di successo. In questo tutorial imparerai **come gestire la disponibilità** delle risorse usando l'API Aspose.Tasks per .NET, passo dopo passo, dal caricamento di un progetto alla copia dei periodi tra risorse.

## Risposte rapide
- **Qual è la classe principale per i periodi di disponibilità?** `AvailabilityPeriod` nello spazio dei nomi `Aspose.Tasks`.  
- **Posso cancellare i periodi esistenti?** Sì, chiama `resource.AvailabilityPeriods.Clear()`.  
- **Come aggiungo un nuovo periodo?** Crea un oggetto `AvailabilityPeriod` e usa `Add` o `Insert`.  
- **È possibile copiare i periodi in un'altra risorsa?** Assolutamente – usa `CopyTo` e poi aggiungi ogni elemento alla risorsa di destinazione.  
- **È necessaria una licenza per l'uso in produzione?** Sì, è richiesta una licenza commerciale di Aspose.Tasks per le distribuzioni non‑trial.

## Che cos'è la disponibilità delle risorse di progetto?
La disponibilità delle risorse di progetto definisce le date e le unità (percentuale di capacità) in cui una risorsa può essere assegnata a attività. Controllando questi periodi si evita il sovraccarico e si migliora la precisione del programma.

## Perché usare Aspose.Tasks per gestire i periodi di disponibilità?
- **Integrazione completa con .NET** – nessun interop COM, codice puramente gestito.  
- **Controllo fine‑grained** – imposta date di inizio/fine esatte e unità frazionarie.  
- **Copia facile** – sposta i dati di disponibilità tra risorse senza parsing manuale.  
- **Ottimizzato per le prestazioni** – funziona in modo efficiente con file MPP di grandi dimensioni.

## Prerequisiti
1. **Visual Studio** – qualsiasi versione recente (2019, 2022 o successive).  
2. **Aspose.Tasks per .NET** – scaricalo da [here](https://releases.aspose.com/tasks/net/).  
3. **Conoscenza di base di C#** – dovresti sentirti a tuo agio con classi, collezioni e LINQ.

## Importare gli spazi dei nomi

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importiamo lo spazio dei nomi principale di Aspose.Tasks insieme alle collezioni standard di .NET di cui avremo bisogno più avanti.

## Passo 1: Inizializzare il progetto e la risorsa

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Qui carichiamo un file MPP esistente e recuperiamo la risorsa la cui disponibilità vogliamo modificare (ID = 1).

## Passo 2: Cancellare i periodi di disponibilità esistenti

```csharp
resource.AvailabilityPeriods.Clear();
```

La cancellazione rimuove tutti i periodi precedentemente definiti, fornendoci una base pulita.

## Passo 3: Aggiungere periodi di disponibilità

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

Recuperiamo una collezione di oggetti `AvailabilityPeriod` (si assume che il metodo di supporto `GetPeriods` sia definito altrove) e aggiungiamo ciascuno, verificando che la collezione sia scrivibile.

## Passo 4: Inserire un nuovo periodo di disponibilità

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Questo crea un periodo personalizzato per l'anno 2013 e lo inserisce nella posizione 1 (secondo slot) se non è già presente.

## Passo 5: Visualizzare i periodi di disponibilità

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

Un rapido dump su console mostra il conteggio totale e i dettagli di ogni periodo – utile per il debug o la verifica.

## Passo 6: Copiare i periodi di disponibilità in un'altra risorsa

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

Copiamo l'intera collezione in un array, cancelliamo i periodi della risorsa di destinazione e poi li ricreiamo. Questo dimostra come duplicare i dati di disponibilità tra risorse.

## Passo 7: Aggiornare e rimuovere i periodi di disponibilità

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Qui modifichiamo `AvailableUnits` per il penultimo periodo e poi rimuoviamo il periodo 2013 aggiunto in precedenza.

## Problemi comuni e soluzioni
- **Errore di collezione read‑only** – Assicurati che il progetto non sia aperto in modalità sola lettura o che tu abbia chiamato `resource.AvailabilityPeriods.Clear()` prima di aggiungere nuovi elementi.  
- **Periodi sovrapposti** – Aspose.Tasks non unisce automaticamente le sovrapposizioni; potresti dover scrivere una logica personalizzata per rilevarle e risolverle.  
- **Formato data errato** – Usa sempre oggetti `DateTime`; il parsing di stringhe può causare bug legati alla locale.

## Domande frequenti

**D: Posso aggiungere campi personalizzati ai periodi di disponibilità?**  
R: No, i periodi di disponibilità in Aspose.Tasks per .NET non supportano campi personalizzati.

**D: I periodi di disponibilità sono collegati a attività specifiche?**  
R: No, sono associati alle risorse e definiscono quando la risorsa è generalmente disponibile per le attività.

**D: Posso importare periodi di disponibilità da fonti esterne?**  
R: Sì, puoi importare periodi da CSV, XML o un database creando oggetti `AvailabilityPeriod` e aggiungendoli alla collezione.

**D: Come gestisco i periodi di disponibilità sovrapposti?**  
R: Le sovrapposizioni non vengono risolte automaticamente; è necessario implementare una validazione personalizzata per unire o rifiutare i periodi conflittuali.

**D: Esiste un limite al numero di periodi di disponibilità che una risorsa può avere?**  
R: Non c'è un limite hard‑coded, ma collezioni molto grandi possono influire sulle prestazioni; considera di consolidare i periodi dove possibile.

## Conclusione

In questa guida abbiamo coperto tutto ciò che serve per gestire la **disponibilità delle risorse di progetto** con Aspose.Tasks per .NET—dall'inizializzare un progetto e cancellare i dati vecchi, all'aggiungere, inserire, copiare, aggiornare e rimuovere i periodi di disponibilità. Padroneggiare questi passaggi ti aiuta a mantenere i calendari delle risorse accurati e i programmi di progetto realistici.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}