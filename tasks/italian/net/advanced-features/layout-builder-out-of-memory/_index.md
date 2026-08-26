---
date: 2026-03-24
description: Impara la gestione fuori memoria e come salvare l'immagine del progetto
  usando Aspose.Tasks Layout Builder in .NET. Guida passo‑passo con esempi di codice.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Gestione della memoria insufficiente con Aspose.Tasks Layout Builder (C#)
url: /it/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione della Memoria Esaurita con Aspose.Tasks Layout Builder

## Introduzione

La gestione della memoria esaurita è una parte critica per costruire applicazioni .NET affidabili che lavorano con file di progetto di grandi dimensioni. Quando generi visualizzazioni con Aspose.Tasks Layout Builder, puoi rapidamente incorrere in eccezioni legate alla memoria, soprattutto su diagrammi di Gantt complessi. In questo tutorial ti guideremo su come **gestire le eccezioni di memoria**, **personalizzare la vista Gantt** e **salvare l'immagine del progetto** in modo sicuro, così la tua applicazione rimarrà reattiva anche con pianificazioni massicce.

## Risposte Rapide
- **Che cos'è la gestione della memoria esaurita?** Gestire l'utilizzo della memoria e intercettare errori di tipo `OutOfMemoryException` durante l'elaborazione di grandi quantità di dati.
- **Quale API aiuta?** Aspose.Tasks Layout Builder per .NET.
- **Scenario tipico?** Rendering di un diagramma di Gantt ad alta risoluzione in PNG.
- **Prerequisito chiave?** .NET (Framework 4.5+ o .NET 6) con Aspose.Tasks installato.
- **Come intercettare gli errori?** Usa blocchi `try…catch` per `ApsLayoutBuilderOutOfMemoryException` e le eccezioni correlate.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere:

1. **Nozioni di base su C#** – dovresti sentirti a tuo agio con la sintassi standard di C#.
2. **Aspose.Tasks per .NET** installato. Se non lo hai ancora aggiunto, scaricalo da [qui](https://releases.aspose.com/tasks/net/).
3. **Un IDE** come Visual Studio (o VS Code con l'estensione C#) per compilare ed eseguire il campione.

## Importare gli Spazi dei Nomi

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guida Passo‑Passo

### Passo 1: Caricare il Progetto

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Questa riga carica **Blank2010.mpp** in un'istanza `Project`, preparandola per la visualizzazione.

### Passo 2: Personalizzare la Vista del Diagramma di Gantt

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Qui **personalizziamo la vista Gantt** regolando i livelli medio e inferiore della scala temporale. Modificare questi livelli riduce la quantità di dati renderizzati contemporaneamente, il che può aiutare a mitigare la pressione sulla memoria.

### Passo 3: Configurare le Opzioni di Salvataggio dell'Immagine

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` indica ad Aspose.Tasks come renderizzare il diagramma. Scegliamo PNG come formato di output e associamo la scala temporale alla vista appena personalizzata.

### Passo 4: Salvare il Progetto come Immagine

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

La chiamata `Save` **salva l'immagine del progetto** usando le opzioni definite sopra. Se il progetto è molto grande, è qui che una condizione di out‑of‑memory è più probabile che si manifesti.

### Passo 5: Gestire le Eccezioni

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Catturando `ApsLayoutBuilderOutOfMemoryException` **gestisci l'eccezione di memoria** in modo elegante, fornendo un messaggio chiaro invece di far crashare l'applicazione. Il secondo `catch` si occupa dei problemi di dimensione del bitmap che possono sorgere durante il rendering di diagrammi enormi.

## Problemi Comuni e Soluzioni

| Problema | Perché si Verifica | Soluzione |
|----------|--------------------|-----------|
| **OutOfMemoryException** | Il rendering di un'immagine ad altissima risoluzione consuma più RAM di quella che il processo può allocare. | Riduci le dimensioni dell'immagine, semplifica i livelli della scala temporale o suddividi il diagramma in più immagini. |
| **BitmapInvalidSizeException** | La dimensione del bitmap richiesta supera il massimo consentito dalla piattaforma. | Limita larghezza/altezza in `ImageSaveOptions` o renderizza a segmenti. |
| **Prestazioni lente** | I file di progetto di grandi dimensioni richiedono molta elaborazione. | Abilita `project.Set(Prj.SaveToCache, true)` prima del rendering, oppure utilizza un thread in background. |

## FAQ

### Q1: Che cos'è Aspose.Tasks per .NET?

A1: Aspose.Tasks per .NET è una potente API che consente agli sviluppatori di manipolare i file Microsoft Project programmaticamente nelle applicazioni .NET.

### Q2: Come posso ottenere una licenza temporanea per Aspose.Tasks?

A2: Puoi ottenere una licenza temporanea per Aspose.Tasks visitando [questo link](https://purchase.aspose.com/temporary-license/).

### Q3: Aspose.Tasks è adatto alla gestione di file di progetto di grandi dimensioni?

A3: Sì, Aspose.Tasks offre funzionalità e ottimizzazioni per gestire file di progetto di grandi dimensioni in modo efficiente, ma gli sviluppatori devono comunque considerare strategie di gestione della memoria.

### Q4: Posso personalizzare l'aspetto dei diagrammi di Gantt usando Aspose.Tasks?

A4: Assolutamente! Aspose.Tasks fornisce ampie capacità per personalizzare l'aspetto e il layout dei diagrammi di Gantt secondo le tue esigenze.

### Q5: Dove posso trovare ulteriore aiuto e supporto per Aspose.Tasks?

A5: Puoi trovare ulteriore aiuto e supporto, oltre a interagire con la community, sul [forum di Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Domande Frequenti

**D: Come posso ridurre l'utilizzo della memoria durante il salvataggio di un'immagine del progetto?**  
R: Abbassa la risoluzione dell'immagine, limita l'intervallo della scala temporale o salva il diagramma in più segmenti più piccoli.

**D: È possibile trasmettere l'immagine direttamente a una risposta web?**  
R: Sì, puoi usare `project.Save(stream, options)` e scrivere lo stream nella risposta HTTP.

**D: Aspose.Tasks supporta .NET Core e .NET 5/6?**  
R: La libreria è pienamente compatibile con .NET Core, .NET 5 e .NET 6.

**D: Cosa devo fare se continuo a ricevere un errore di out‑of‑memory dopo l'ottimizzazione?**  
R: Considera di elaborare il progetto su una macchina con più RAM o di delegare il rendering a un servizio in background.

**D: Posso esportare il diagramma di Gantt in formati diversi da PNG?**  
R: Sì, `ImageSaveOptions` supporta JPEG, BMP e TIFF oltre a PNG.

---

**Ultimo Aggiornamento:** 2026-03-24  
**Testato Con:** Aspose.Tasks 24.11 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}