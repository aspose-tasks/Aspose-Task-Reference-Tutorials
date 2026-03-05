---
date: 2026-03-05
description: Impara come salvare le immagini, generare HTML con immagini e personalizzare
  l'esportazione delle immagini usando Aspose.Tasks per .NET. Guida passo‑passo per
  salvare il progetto come HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Come salvare le immagini con Aspose.Tasks per .NET
url: /it/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come salvare immagini con Aspose.Tasks per .NET

## Introduzione

In questo tutorial scoprirai **come salvare immagini** dai file Microsoft Project utilizzando l'API Aspose.Tasks per .NET. Che tu abbia bisogno di incorporare grafici nei report, generare pagine HTML che contengono visualizzazioni del progetto, o semplicemente esportare risorse diagrammatiche, i passaggi seguenti ti guideranno attraverso l'intero processo—dalla configurazione dell'oggetto progetto alla personalizzazione dei callback di esportazione delle immagini.

## Risposte rapide
- **Cosa significa “come salvare immagini” in Aspose.Tasks?**  
  Si riferisce all'utilizzo dell'interfaccia `IImageSavingCallback` per controllare dove e come le risorse visive vengono scritte su disco.
- **Posso salvare un progetto come HTML con immagini incorporate?**  
  Sì, utilizzando `HtmlSaveOptions` insieme ai callback di salvataggio delle immagini è possibile **salvare il progetto come HTML** che include tutte le immagini generate.
- **È necessaria una licenza per l'esportazione delle immagini?**  
  Una licenza di valutazione temporanea funziona per i test; è necessaria una licenza completa per l'uso in produzione.
- **Quali versioni di .NET sono supportate?**  
  Aspose.Tasks per .NET supporta .NET Framework 4.5+, .NET Core 3.1+ e .NET 5/6+.
- **È possibile personalizzare l'esportazione delle immagini (formato, cartella, denominazione)?**  
  Assolutamente – il callback ti offre il pieno controllo sul nome file, sul formato e sulla destinazione.

## Cos'è “come salvare immagini” nel contesto di Aspose.Tasks?

Salvare immagini significa estrarre elementi visivi (grafici, barre Gantt, grafici delle risorse) da un file Project e scriverli in file immagine (PNG, JPEG, ecc.). Aspose.Tasks fornisce un meccanismo di callback flessibile che ti consente di decidere la posizione esatta, la convenzione di denominazione e persino il formato dell'immagine.

## Perché usare Aspose.Tasks per salvare immagini?
- **Controllo programmatico completo** – non è necessaria alcuna interazione manuale con l'interfaccia utente.  
- **Cross‑platform** – funziona su Windows, Linux e macOS tramite .NET Core.  
- **Rendering ad alta fedeltà** – le immagini mantengono la stessa qualità della vista originale del Project.  
- **Generazione HTML semplificata** – combina `HtmlSaveOptions` con i callback delle immagini per **generare HTML con immagini** automaticamente.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. Visual Studio installato sulla tua macchina di sviluppo.  
2. Aspose.Tasks per .NET scaricato da [qui](https://releases.aspose.com/tasks/net/).  
3. Familiarità di base con C# e la struttura dei progetti .NET.

## Importare gli spazi dei nomi

Per prima cosa, importa gli spazi dei nomi richiesti nel tuo file sorgente:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Passo 1: Creare un oggetto Project

Carica il file Microsoft Project con cui desideri lavorare:

```csharp
var project = new Project("Project1.mpp");
```

## Passo 2: Definire le opzioni di salvataggio

Crea le opzioni di salvataggio HTML che conterranno anche i nostri callback di salvataggio delle immagini:

```csharp
var options = GetSaveOptions(1);
```

## Passo 3: Salvare il progetto come HTML (save project as html)

Ora esporta il progetto in un file HTML. Le immagini referenziate nell'HTML saranno generate dal callback che definiremo nel passo successivo:

```csharp
project.Save("document_out.html", options);
```

## Passo 4: Implementare il callback di salvataggio delle immagini (customize image export)

Implementa l'interfaccia `IImageSavingCallback`. Qui è dove **personalizzi il comportamento di esportazione delle immagini**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Passo 5: Salvare le immagini nella directory specificata

All'interno del metodo `ImageSaving`, decidi dove deve essere archiviata ciascuna immagine. L'esempio seguente distingue le risorse PNG dagli altri formati:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Passo 6: Specificare le opzioni di salvataggio (including callbacks)

Collega i callback per i font, i CSS e le immagini. Questo garantisce che ogni elemento visivo venga gestito in modo coerente:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Problemi comuni e soluzioni

| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Le immagini non compaiono nell'HTML generato | Il callback non assegna un percorso file valido | Assicurati che `args.Path` punti a una cartella scrivibile e imposta correttamente `args.ImageStream`. |
| I file PNG vengono salvati con estensione errata | La logica condizionale controlla solo il suffisso “png” | Usa `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` per un rilevamento più robusto. |
| I riferimenti HTML si rompono dopo lo spostamento dei file | I percorsi relativi sono cambiati dopo lo spostamento della cartella di output | Mantieni le cartelle HTML e immagini insieme o aggiorna `options.ImageFolder` di conseguenza. |

## Conclusione

Seguendo questi passaggi ora sai **come salvare immagini** da un file Project, **salvare il progetto come HTML** e **personalizzare l'esportazione delle immagini** per adattarla alla struttura delle cartelle della tua applicazione. Questo approccio ti consente di **generare HTML con immagini** che possono essere incorporati in report, portali di documentazione o dashboard web in modo fluido.

## Domande frequenti

**Q1: Posso usare Aspose.Tasks per manipolare file di progetto in altri formati oltre a HTML?**  
A1: Sì, Aspose.Tasks supporta vari formati come PDF, XLSX e MPP.

**Q2: Aspose.Tasks fornisce supporto per l'integrazione con lo storage cloud?**  
A2: Sì, Aspose.Tasks offre API per lavorare con i più popolari servizi di storage cloud come Amazon S3 e Google Drive.

**Q3: Aspose.Tasks è compatibile con .NET Core?**  
A3: Sì, Aspose.Tasks è compatibile con .NET Core, consentendo di sviluppare applicazioni cross‑platform.

**Q4: Posso personalizzare l'aspetto delle immagini salvate?**  
A4: Sì, puoi personalizzare l'aspetto delle immagini salvate modificando la logica di salvataggio delle immagini nei metodi di callback.

**Q5: Aspose.Tasks offre versioni di prova per scopi di valutazione?**  
A5: Sì, puoi ottenere una prova gratuita di Aspose.Tasks da [qui](https://releases.aspose.com/).

---

**Ultimo aggiornamento:** 2026-03-05  
**Testato con:** Aspose.Tasks 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}