---
date: 2026-03-08
description: Impara come impostare la visualizzazione delle etichette e personalizzare
  l’etichetta del giorno nella gestione dei progetti usando Aspose.Tasks per .NET,
  migliorando la leggibilità e la chiarezza.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come impostare la visualizzazione dell'etichetta in Aspose.Tasks per .NET
url: /it/net/advanced-concepts/label-display/
weight: 14
---

.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come impostare la visualizzazione delle etichette in Aspose.Tasks per .NET

## Introduzione

Quando si costruisce una soluzione di gestione progetti con **Aspose.Tasks for .NET**, la possibilità di **impostare le etichette** è fondamentale per rendere i programmi facili da leggere. Che tu abbia bisogno di precisione al minuto o di una vista annuale di alto livello, personalizzare la visualizzazione delle etichette ti consente di presentare la timeline esattamente nel modo in cui i tuoi stakeholder si aspettano. In questo tutorial percorreremo passo dopo passo il processo di impostazione delle visualizzazioni delle etichette per minuti, ore, giorni, settimane, mesi e anni, e ti mostreremo anche come **personalizzare la formattazione dell'etichetta del giorno** per la massima chiarezza.

## Risposte rapide
- **Cosa significa “impostare le etichette”?** Si riferisce alla configurazione delle proprietà `DisplayOptions` che controllano come le unità di tempo appaiono in un file di progetto.  
- **Quali etichette posso modificare?** Minuti, ore, giorni, settimane, mesi e anni sono tutti configurabili.  
- **È necessaria una licenza?** È richiesta una licenza valida di Aspose.Tasks per l'uso in produzione; una versione di prova gratuita è sufficiente per i test.  
- **È supportato su .NET Core?** Sì, l'API funziona con .NET Core, .NET 5/6 e il .NET Framework completo.  
- **Posso cambiare l'etichetta a runtime?** Assolutamente – puoi modificare le opzioni di visualizzazione in qualsiasi momento prima di salvare il progetto.

## Che cos'è la visualizzazione delle etichette in Aspose.Tasks?

La visualizzazione delle etichette determina la rappresentazione testuale delle unità di tempo (minuto, ora, giorno, ecc.) sul diagramma di Gantt e sulla scala temporale. Impostando la proprietà `DisplayOptions` appropriata, istruisci Aspose.Tasks su come renderizzare quelle unità, il che può migliorare notevolmente la leggibilità del progetto.

## Perché personalizzare le visualizzazioni delle etichette?

- **Migliore leggibilità:** gli stakeholder possono cogliere immediatamente la granularità del programma.  
- **Reportistica coerente:** allinea l'output visivo agli standard aziendali (ad esempio, usando “Mo” per i mesi).  
- **Flessibilità:** passa da viste dettagliate a viste di alto livello senza alterare i dati di programma sottostanti.

## Prerequisiti

1. **Conoscenza di C#** – familiarità di base con la sintassi C# e la struttura di un progetto .NET.  
2. **Aspose.Tasks for .NET** – scarica e installa la libreria da [qui](https://releases.aspose.com/tasks/net/).  
3. **Ambiente di sviluppo** – Visual Studio, VS Code o qualsiasi IDE che supporti lo sviluppo .NET.

## Importare gli spazi dei nomi

Prima di iniziare, importa gli spazi dei nomi richiesti:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Come impostare la visualizzazione delle etichette per i minuti

### 1. Visualizzare le etichette dei minuti

Per impostare l'etichetta dei minuti, utilizza la proprietà `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Come impostare la visualizzazione delle etichette per le ore

### 2. Visualizzare le etichette delle ore

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Personalizzare la visualizzazione dell'etichetta del giorno

### 3. Visualizzare le etichette dei giorni

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Come impostare la visualizzazione delle etichette per le settimane

### 4. Visualizzare le etichette delle settimane

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Come impostare la visualizzazione delle etichette per i mesi

### 5. Visualizzare le etichette dei mesi

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Come impostare la visualizzazione delle etichette per gli anni

### 6. Visualizzare le etichette degli anni

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Problemi comuni e consigli

- **Consiglio:** imposta sempre la visualizzazione delle etichette *prima* di salvare il progetto; le modifiche effettuate dopo il salvataggio non saranno riflesse nel file.  
- **Problema:** utilizzare un valore enum non supportato genererà un `ArgumentException`. Attieniti agli enum `*LabelDisplay` forniti.  
- **Consiglio:** se hai bisogno di stili di etichetta diversi per viste separate, crea istanze `Project` separate o clona l'oggetto `DisplayOptions`.

## Conclusione

Padroneggiando le opzioni di **impostazione delle etichette** in Aspose.Tasks, ottieni un controllo granulare sulla presentazione visiva dei tuoi programmi di progetto. Che tu stia personalizzando l'etichetta del giorno per una board scrum quotidiana o regolando l'etichetta dell'anno per una roadmap pluriennale, queste impostazioni ti aiutano a fornire documentazione di progetto più chiara e professionale.

## FAQ

### Q1: Posso personalizzare le visualizzazioni delle etichette per sezioni specifiche di un progetto?

A1: Sì, Aspose.Tasks for .NET consente un controllo granulare delle visualizzazioni delle etichette, permettendo la personalizzazione per sezioni specifiche del progetto secondo le necessità.

### Q2: Aspose.Tasks è compatibile con i framework .NET più diffusi?

A2: Sì, Aspose.Tasks for .NET è compatibile con vari framework .NET, inclusi .NET Core e .NET Framework.

### Q3: Posso modificare dinamicamente le visualizzazioni delle etichette in base ai requisiti del progetto?

A3: Assolutamente, la flessibilità di Aspose.Tasks for .NET permette aggiustamenti dinamici delle visualizzazioni delle etichette in base all'evoluzione dei requisiti del progetto.

### Q4: Ci sono limitazioni alla personalizzazione delle visualizzazioni delle etichette?

A4: Aspose.Tasks for .NET offre ampie opzioni di personalizzazione per le visualizzazioni delle etichette, con limitazioni minime, fornendo agli utenti una notevole flessibilità.

### Q5: Aspose.Tasks supporta l'integrazione con altri strumenti di gestione progetti?

A5: Sì, Aspose.Tasks offre capacità di integrazione senza soluzione di continuità, facilitando l'interoperabilità con altri strumenti e piattaforme di gestione progetti.

---

**Ultimo aggiornamento:** 2026-03-08  
**Testato con:** Aspose.Tasks 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}