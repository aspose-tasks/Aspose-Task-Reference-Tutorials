---
date: 2026-04-06
description: Scopri come aggiungere una risorsa al progetto e impostare i periodi
  di disponibilità della risorsa utilizzando Aspose.Tasks per .NET. Guida passo‑passo
  per la gestione dei calendari delle risorse.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Lavorare con i periodi di disponibilità in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aggiungi risorsa al progetto e imposta la disponibilità in Aspose.Tasks
url: /it/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi risorsa al progetto e imposta la disponibilità in Aspose.Tasks

## Introduzione

In questo tutorial imparerai **come aggiungere una risorsa al progetto** e poi definire i suoi periodi di disponibilità usando la libreria Aspose.Tasks per .NET. Gestire i calendari delle risorse è essenziale per pianificazioni di progetto realistiche, e i passaggi seguenti ti guideranno attraverso l'intero processo—dalla creazione di un'istanza del progetto alla stampa dei dettagli di ogni periodo.

## Risposte rapide
- **Qual è l'obiettivo principale?** Aggiungere una risorsa a un progetto e configurare i suoi periodi di disponibilità.  
- **Quale libreria è necessaria?** Aspose.Tasks per .NET.  
- **È necessaria una licenza per la produzione?** Sì, è richiesta una licenza commerciale.  
- **Versioni .NET supportate?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Tempo di implementazione?** Tipicamente meno di 15 minuti per scenari di base.

## Che cosa significa “add resource to project”?

Aggiungere una risorsa a un progetto crea un segnaposto per una persona, attrezzatura o materiale che può essere assegnato alle attività. Una volta che la risorsa esiste, puoi **impostare la disponibilità della risorsa**, definire il suo calendario di lavoro e far sì che il pianificatore rispetti tali vincoli.

## Perché configurare il programma di lavoro e i periodi di disponibilità?

- **Pianificazione accurata:** Le attività vengono programmate solo quando la risorsa è effettivamente libera.  
- **Controllo dei costi:** Le unità di disponibilità riflettono l'impegno part‑time, aiutandoti a calcolare correttamente i costi del lavoro.  
- **Livellamento delle risorse:** Il motore può livellare automaticamente le sovrallocazioni quando conosce il calendario di ciascuna risorsa.

## Prerequisiti

1. Visual Studio (o qualsiasi IDE compatibile con .NET).  
2. Aspose.Tasks per .NET – scarica da [qui](https://releases.aspose.com/tasks/net/).  
3. Conoscenze di base di C#.

## Importa gli spazi dei nomi

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Come aggiungere una risorsa al progetto?

### Passo 1: Crea una nuova istanza `Project`

```csharp
var project = new Project();
```

Questo oggetto rappresenta l'intero file di progetto in memoria.

### Passo 2: Aggiungi una risorsa al progetto

```csharp
var resource = project.Resources.Add("Work Resource");
```

La chiamata crea una **risorsa** denominata *Work Resource* che potrai successivamente collegare alle attività.

### Passo 3: Definisci i periodi di disponibilità

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` è un metodo di supporto (implementazione non mostrata) che restituisce una collezione di oggetti `AvailabilityPeriod`. Ogni periodo specifica una data di inizio, una data di fine e le unità (percentuale dell'impegno a tempo pieno) in cui la risorsa è disponibile.

### Passo 4: Aggiungi i periodi alla risorsa

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Qui **impostiamo la disponibilità della risorsa** iterando sulla collezione e aggiungendo ogni periodo al calendario della risorsa.

### Passo 5: Visualizza i dettagli della disponibilità

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

L'output della console ti consente di verificare che i periodi siano stati memorizzati correttamente.

## Problemi comuni e consigli

- **Precisione delle date:** `AvailableFrom` e `AvailableTo` sono valori `DateTime`; assicurati che siano impostati a mezzanotte se desideri periodi di un’intera giornata.  
- **Intervallo delle unità:** I valori validi sono 0‑100 %; valori al di fuori di questo intervallo genereranno un'eccezione.  
- **Periodi sovrapposti:** I periodi sovrapposti vengono uniti automaticamente, ma è più chiaro mantenerli distinti.

## Domande frequenti

### Q1: Posso usare Aspose.Tasks per .NET in progetti commerciali?
A1: Sì, Aspose.Tasks per .NET può essere usato in progetti commerciali. Puoi acquistare una licenza [qui](https://purchase.aspose.com/buy).

### Q2: È disponibile una versione di prova gratuita per Aspose.Tasks per .NET?
A2: Sì, puoi ottenere una prova gratuita di Aspose.Tasks per .NET [qui](https://releases.aspose.com/).

### Q3: Dove posso trovare la documentazione per Aspose.Tasks per .NET?
A3: Puoi trovare la documentazione [qui](https://reference.aspose.com/tasks/net/).

### Q4: Come posso ottenere supporto per Aspose.Tasks per .NET?
A4: Puoi ottenere supporto dal forum della community [qui](https://forum.aspose.com/c/tasks/15).

### Q5: Offrite licenze temporanee per Aspose.Tasks per .NET?
A5: Sì, le licenze temporanee sono disponibili [qui](https://purchase.aspose.com/temporary-license/).

---

**Ultimo aggiornamento:** 2026-04-06  
**Testato con:** Aspose.Tasks per .NET (ultima versione stabile)  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}