---
title: Gestione dell'eccezione di dimensione non valida per bitmap in Aspose.Tasks
linktitle: Gestione dell'eccezione di dimensione non valida per bitmap in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire BitmapInvalidSizeException in Aspose.Tasks per .NET durante il salvataggio di progetti come immagini. Tutorial completo con guida passo passo.
weight: 22
url: /it/net/advanced-features/bitmap-invalid-size-exception/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gestione dell'eccezione di dimensione non valida per bitmap in Aspose.Tasks

## introduzione

 In questo tutorial, approfondiremo la gestione del file`BitmapInvalidSizeException` quando si lavora con Aspose.Tasks per .NET. Aspose.Tasks è una potente libreria che consente agli sviluppatori di manipolare i file di Microsoft Project a livello di codice, abilitando attività come il salvataggio di progetti come immagini. Tuttavia, occasionalmente, quando tentiamo di salvare un progetto come immagine, potremmo incontrare un file`Invalid Size Exception`relativo alla bitmap. Questo tutorial ha lo scopo di guidarti attraverso il processo di acquisizione e gestione di questa eccezione in modo efficace.

## Prerequisiti

Prima di procedere con questo tutorial, assicurati di disporre dei seguenti prerequisiti:
1. Conoscenza base del linguaggio di programmazione C#.
2. Aspose.Tasks installato per .NET.
3. Familiarità con l'utilizzo dei file Microsoft Project.

## Importa spazi dei nomi

Prima di iniziare, assicurati di importare gli spazi dei nomi necessari:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Passaggio 1: inizializza il progetto e definisci la vista

 Innanzitutto, inizializza a`Project` oggetto e definire una vista, come ad esempio`GanttChartView`.

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## Passaggio 2: specificare le opzioni di salvataggio dell'immagine

Successivamente, specifica le opzioni per salvare l'immagine, inclusi il formato e la scala temporale.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## Passaggio 3: impostare l'unità e il conteggio della scala cronologica

Regola l'unità di tempo e conta in base alle tue esigenze. In questo esempio, impostiamo la scala temporale su minuti.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Passaggio 4: salva il progetto come immagine

Tentare di salvare il progetto come immagine utilizzando le opzioni specificate.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Passaggio 5: intercettare e gestire l'eccezione

 Implementare la gestione delle eccezioni per catturare il file`BitmapInvalidSizeException` se si verifica durante il processo di salvataggio dell'immagine.

```csharp
try
{
    // Tentativo di salvare il progetto come immagine
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Gestire l'eccezione
    Console.WriteLine(ex.Message);
}
```

## Conclusione

 In conclusione, gestire il`BitmapInvalidSizeException` quando il salvataggio di progetti come immagini in Aspose.Tasks per .NET è fondamentale per garantire un'esecuzione fluida delle applicazioni. Seguendo i passaggi descritti in questo tutorial, puoi rilevare e gestire efficacemente questa eccezione, migliorando così la robustezza delle tue soluzioni di gestione dei progetti.

## Domande frequenti

### Q1: Cosa causa BitmapInvalidSizeException in Aspose.Tasks?

A1: questa eccezione si verifica quando si tenta di salvare un progetto come immagine con parametri di dimensione bitmap non validi.

### Q2: Posso personalizzare la scala temporale quando salvo un progetto come immagine?

R2: Sì, puoi regolare l'unità di scala temporale e contare in base alle tue esigenze, come dimostrato nel tutorial.

### Q3: Dove posso trovare più risorse per lavorare con Aspose.Tasks per .NET?

A3: È possibile esplorare la documentazione e i forum di supporto forniti da Aspose.Tasks per indicazioni e assistenza complete.

### Q4: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?

A4: Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, consentendo una perfetta interoperabilità.

### Q5: Come posso ottenere una licenza temporanea per Aspose.Tasks?

R5: È possibile acquisire una licenza temporanea a scopo di valutazione tramite il collegamento fornito nell'articolo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
