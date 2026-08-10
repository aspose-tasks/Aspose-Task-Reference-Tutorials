---
date: 2026-03-21
description: Scopri come esportare un'immagine e gestire l'eccezione BitmapInvalidSizeException
  durante il salvataggio di un progetto come immagine in Aspose.Tasks per .NET. Include
  i passaggi per salvare il progetto come immagine ed esportarlo in PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come esportare l'immagine e gestire l'eccezione di dimensione non valida
url: /it/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come esportare un'immagine – Gestione dell'eccezione Invalid Size per Bitmap in Aspose.Tasks

In questo tutorial imparerai **come esportare un'immagine** da un file Microsoft Project usando Aspose.Tasks per .NET e, soprattutto, come intercettare la `BitmapInvalidSizeException` che può verificarsi durante il processo. Esportare un progetto come immagine è una necessità comune per dashboard di reporting, documentazione, o semplicemente per condividere un'istantanea visiva di un programma. Alla fine di questa guida sarai in grado di **salvare il progetto come immagine** in modo affidabile e persino **esportare il progetto in formato PNG** senza crash inaspettati.

## Risposte rapide
- **Quale eccezione può verificarsi durante l'esportazione di un'immagine?** `BitmapInvalidSizeException`  
- **Quale formato è usato nell'esempio?** PNG (`SaveFileFormat.Png`)  
- **Ho bisogno di una licenza speciale?** È necessaria una licenza valida di Aspose.Tasks per l'uso in produzione.  
- **Posso cambiare la scala temporale?** Sì – è possibile impostare l'unità della scala temporale (minuti, ore, giorni, ecc.).  
- **Il codice è compatibile con .NET Core?** Assolutamente – la stessa API funziona su .NET Framework e .NET Core.

## Cos'è la BitmapInvalidSizeException?
`BitmapInvalidSizeException` viene sollevata quando le dimensioni del bitmap calcolate per l'immagine sono al di fuori dell'intervallo supportato (ad esempio, larghezza o altezza pari a zero o che supera i limiti interni). Questo di solito accade quando la scala temporale o le impostazioni della vista producono un'immagine troppo grande o troppo piccola.

## Perché esportare un progetto come immagine?
- **Reporting visivo** – incorpora un diagramma di Gantt in PDF, documenti Word o pagine web.  
- **Condivisione cross‑platform** – i file PNG possono essere visualizzati su qualsiasi dispositivo senza necessità di Microsoft Project.  
- **Prestazioni** – le immagini sono leggere rispetto ai file di progetto completi per anteprime rapide.

## Prerequisiti
1. Conoscenza di base di C# e sviluppo .NET.  
2. Aspose.Tasks per .NET installato (pacchetto NuGet `Aspose.Tasks`).  
3. Un file di esempio Microsoft Project (ad es., `Blank2010.mpp`).  

## Importare gli spazi dei nomi
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Guida passo‑passo

### Passo 1: Inizializzare il progetto e scegliere una vista
Per prima cosa, crea un'istanza di `Project` e scegli la vista che desideri renderizzare (qui usiamo la prima vista Gantt).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Passo 2: Configurare le opzioni di salvataggio immagine (Esportare il progetto in PNG)
Imposta il formato immagine desiderato e indica ad Aspose.Tasks di utilizzare la scala temporale definita nella vista.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Passo 3: Regolare l'unità della scala temporale (Controllare la dimensione dell'immagine)
Modificare la scala temporale influisce sulle dimensioni del bitmap. In questo esempio usiamo i **minuti** per mantenere la dimensione dell'immagine gestibile.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Passo 4: Tentare di salvare il progetto come immagine
Questa riga esegue l'effettiva operazione di **salvataggio del progetto come immagine**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Passo 5: Catturare e gestire la BitmapInvalidSizeException
Avvolgi la chiamata di salvataggio in un blocco `try / catch` in modo che la tua applicazione possa reagire in modo corretto se la dimensione del bitmap è invalida.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Problemi comuni e soluzioni
| Problema | Causa | Soluzione |
|----------|-------|-----------|
| Eccezione ancora lanciata dopo aver regolato la scala temporale | La scala temporale produce ancora un bitmap troppo grande | Riduci `view.MiddleTimescaleTier.Count` o passa a un `TimescaleUnit` più grossolano (ad es., Hours). |
| Il file di output è vuoto | Percorso file errato o permessi di scrittura mancanti | Verifica che `DataDir` punti a una cartella scrivibile e che il nome file termini con `.png` se cambi il formato. |
| Qualità dell'immagine scarsa | Il DPI predefinito può essere basso | Imposta `options.DpiX` e `options.DpiY` a valori più alti (ad es., 300). |

## Domande frequenti

**D: Cosa causa la BitmapInvalidSizeException in Aspose.Tasks?**  
R: Si verifica quando le dimensioni calcolate del bitmap sono invalide—tipicamente perché la scala temporale crea un'immagine troppo grande o con larghezza/altezza pari a zero.

**D: Posso personalizzare la scala temporale durante l'esportazione di un'immagine?**  
R: Sì. È possibile modificare `view.MiddleTimescaleTier.Unit` e `Count` secondo le proprie esigenze, come mostrato nel tutorial.

**D: Aspose.Tasks supporta altri formati immagine oltre al PNG?**  
R: Assolutamente. `SaveFileFormat` include anche JPEG, BMP, GIF e TIFF. Basta cambiare il valore enum in `ImageSaveOptions`.

**D: È necessaria una licenza per esportare immagini in un ambiente di produzione?**  
R: Sì. Sebbene la libreria funzioni in modalità di valutazione, una licenza commerciale rimuove le limitazioni di valutazione e fornisce supporto completo.

**D: Come posso migliorare la qualità del PNG esportato?**  
R: Aumenta le impostazioni DPI (`options.DpiX` e `options.DpiY`) o regola la scala temporale della vista per produrre un bitmap più grande.

## Conclusione
Seguendo i passaggi sopra, ora sai **come esportare un'immagine** da un file Project, come **salvare il progetto come immagine**, e come gestire in modo corretto la `BitmapInvalidSizeException`. Queste tecniche rendono le tue pipeline di reporting più robuste e garantiscono che le esportazioni visive funzionino in modo affidabile su progetti di diverse dimensioni e scale temporali.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ultimo aggiornamento:** 2026-03-21  
**Testato con:** Aspose.Tasks 24.12 per .NET  
**Autore:** Aspose