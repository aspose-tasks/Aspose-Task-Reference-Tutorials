---
date: 2026-03-16
description: Scopri come implementare il callback di salvataggio delle pagine in Aspose.Tasks
  per .NET, consentendo una gestione personalizzata dei flussi di output dei documenti
  multi‑pagina.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementare il callback di salvataggio della pagina in Aspose.Tasks
url: /it/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementare il callback di salvataggio della pagina in Aspose.Tasks

## Introduzione

In questo tutorial imparerai come **implementare il callback di salvataggio della pagina** in Aspose.Tasks per .NET. Questa potente funzionalità ti consente di indirizzare ogni pagina di un documento multi‑pagina a uno stream a tua scelta, offrendoti il pieno controllo su come l'output viene memorizzato o ulteriormente elaborato.

## Risposte rapide
- **Cosa fa il callback di salvataggio della pagina?** Cattura ogni pagina renderizzata in uno stream separato così puoi gestirle individualmente.  
- **Quale formato posso esportare?** Qualsiasi formato supportato da `ImageSaveOptions`, ad esempio PNG, JPEG, PDF.  
- **Ho bisogno di una licenza?** È necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso usarlo con .NET Core?** Sì, Aspose.Tasks supporta pienamente .NET Core e .NET 5/6+.  
- **Il callback è thread‑safe?** Il callback viene eseguito sullo stesso thread che esegue il rendering, quindi si applicano le normali regole di thread‑safety.

## Che cos'è **implementare il callback di salvataggio della pagina**?
Il pattern **implementare il callback di salvataggio della pagina** consente di inserire logica personalizzata nella pipeline di salvataggio di Aspose.Tasks. Invece di scrivere direttamente su un file, ricevi un oggetto `Stream` per ogni pagina, permettendoti di memorizzarlo in memoria, caricarlo su storage cloud o applicare ulteriori elaborazioni.

## Perché esportare il progetto come PNG con un callback?
Esportare un progetto come PNG ti fornisce un'immagine raster di ogni pagina del diagramma di Gantt, ideale per report, email o incorporamento in pagine web. Usare un callback significa che puoi mantenere ogni pagina in un `MemoryStream` separato senza creare file temporanei su disco.

## Prerequisiti

1. **Conoscenza di C#** – familiarità di base con classi, interfacce e stream.  
2. **Aspose.Tasks per .NET** – scarica e installa da [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider o qualsiasi editor compatibile con .NET.

## Importare gli spazi dei nomi

Per iniziare, importa gli spazi dei nomi richiesti:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Passo 1: Creare un oggetto Project

Carica un file MPP esistente in un'istanza `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Passo 2: Configurare le opzioni di salvataggio immagine

Imposta `ImageSaveOptions` per l'output PNG e collega il callback personalizzato:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Suggerimento professionale:** Impostare `RenderToSinglePage = false` garantisce che ogni pagina del diagramma di Gantt venga renderizzata separatamente, il che è essenziale affinché il callback riceva stream distinti.

## Passo 3: Salvare il progetto con il callback

Invoca il metodo `Save`, passando `Stream.Null` perché gli stream reali sono forniti dal callback:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Passo 4: Elaborare gli stream delle pagine salvate

Dopo il completamento dell'operazione di salvataggio, il callback contiene una collezione di oggetti `MemoryStream`—uno per pagina. Ora puoi iterare su di essi:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Passo 5: Implementare il callback personalizzato di salvataggio pagina

Crea una classe sealed che implementa `IPageSavingCallback`. Questa classe cattura lo stream di ogni pagina e lo memorizza in una lista per un uso successivo.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Problemi comuni e risoluzione

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Nessuna pagina restituita** | `RenderToSinglePage` lasciato su `true`. | Imposta `RenderToSinglePage = false` per generare pagine separate. |
| **Gli stream sono vuoti** | `KeepStreamOpen` impostato su `true` senza rilasciare successivamente. | Mantienilo `false` (predefinito) e lascia che il callback chiuda gli stream automaticamente. |
| **Errori di out‑of‑memory** | Progetti molto grandi generano molti PNG ad alta risoluzione. | Elabora gli stream uno alla volta o aumenta i limiti di memoria della VM. |

## Domande frequenti

**D1: Cos'è un callback di salvataggio della pagina in Aspose.Tasks?**  
R: Un callback di salvataggio della pagina ti consente di intercettare il processo di salvataggio per ogni pagina di un documento multi‑pagina, fornendo uno `Stream` personalizzato per quella pagina.

**D2: Posso usare formati diversi per salvare le pagine usando questo callback?**  
R: Sì. Modificando `SaveFileFormat` è possibile esportare in PNG, JPEG, PDF, SVG, ecc.

**D3: Aspose.Tasks è compatibile con .NET Core?**  
R: Assolutamente. Aspose.Tasks supporta .NET Core, .NET 5 e .NET 6.

**D4: Come posso gestire gli errori durante il processo di salvataggio della pagina?**  
R: Avvolgi la logica del callback in blocchi try/catch e registra le eccezioni. Il metodo `OnFinish` è un buon punto per la pulizia finale.

**D5: Dove posso trovare ulteriori risorse e supporto per Aspose.Tasks?**  
R: Puoi visitare il [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per assistenza, accedere alla documentazione [qui](https://reference.aspose.com/tasks/net/), o esplorare funzionalità aggiuntive e opzioni di licenza sul [sito Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Ultimo aggiornamento:** 2026-03-16  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}