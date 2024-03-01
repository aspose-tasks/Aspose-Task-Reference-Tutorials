---
title: Barra di stile in Aspose.Tasks
linktitle: Barra di stile in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come definire lo stile delle barre in Aspose.Tasks per .NET per migliorare la visualizzazione del progetto.
type: docs
weight: 19
url: /it/net/advanced-features/styling-bar/
---
## introduzione

Le barre di stile in Aspose.Tasks sono un aspetto essenziale della creazione di piani di progetto visivamente accattivanti. Con la flessibilità offerta dall'API Aspose.Tasks, gli sviluppatori possono personalizzare vari aspetti delle barre, come colore, forma e stile del testo, per migliorare la visualizzazione del progetto. In questo tutorial esploreremo come definire lo stile delle barre utilizzando Aspose.Tasks per .NET, suddividendo ogni esempio in passaggi gestibili.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

1.  Aspose.Tasks for .NET Library: Scarica e installa la libreria Aspose.Tasks for .NET dal[pagina di download](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo: configura un ambiente di sviluppo con il supporto del framework .NET.
3. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importa spazi dei nomi

Innanzitutto, importiamo gli spazi dei nomi necessari per accedere alle classi e ai metodi Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Passaggio 1: caricare il progetto

Per iniziare, carica il file di progetto utilizzando l'API Aspose.Tasks:

```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Passaggio 2: configura le opzioni di salvataggio

Definire le opzioni di salvataggio, specificando gli stili di barra da applicare:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Passaggio 3: definire lo stile della barra

Crea un nuovo stile di barra e personalizza le sue proprietà:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Imposta il tipo di elemento della barra
style.BarColor = Color.Green; // Imposta il colore della barra
style.BarShape = BarShape.HalfHeight; // Imposta la forma della barra
style.StartShape = Shape.LeftBracket; // Imposta la forma all'inizio della barra
style.StartShapeColor = Color.Aqua; // Imposta il colore della forma iniziale
style.EndShape = Shape.RightBracket; // Imposta la forma all'estremità della barra
style.EndShapeColor = Color.Aquamarine; // Imposta il colore della forma finale
style.TextStyle = new TextStyle(); // Imposta lo stile del testo
style.TextStyle.BackgroundColor = Color.Black; // Imposta il colore di sfondo per il testo
```

## Passaggio 4: personalizza il convertitore di testo

Facoltativamente, personalizza il convertitore di testo per modificare il rendering del testo:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Passaggio 5: aggiungi lo stile della barra alle opzioni

Aggiungi lo stile della barra configurato alle opzioni di salvataggio:

```csharp
options.BarStyles.Add(style);
```

## Passaggio 6: salva il progetto

Infine, salva il progetto con gli stili di barra applicati:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusione

La personalizzazione degli stili della barra in Aspose.Tasks per .NET offre agli sviluppatori la possibilità di creare piani di progetto visivamente accattivanti. Seguendo i passaggi descritti in questo tutorial, puoi definire in modo efficiente le barre di stile per soddisfare requisiti specifici di visualizzazione del progetto.

## Domande frequenti

### Q1: Posso applicare più stili di barre a un singolo progetto?

R1: Sì, puoi definire e applicare più stili di barre a diversi tipi di attività all'interno dello stesso progetto.
   
### Q2: È possibile modificare dinamicamente gli stili delle barre durante il runtime?

R2: Sì, puoi modificare dinamicamente gli stili delle barre in base a determinate condizioni o preferenze dell'utente all'interno della tua applicazione.
   
### Q3: Aspose.Tasks supporta l'esportazione di progetti con barre in stile in diversi formati di file?

A3: Sì, Aspose.Tasks supporta l'esportazione di progetti con barre in stile in vari formati come PDF, XLSX e HTML.
   
### Q4: Sono disponibili stili di barra predefiniti in Aspose.Tasks?

A4: Sebbene Aspose.Tasks fornisca stili di barra predefiniti, gli sviluppatori possono anche creare stili di barra personalizzati su misura per i requisiti del progetto.
   
### Q5: Posso recuperare e modificare gli stili di barre esistenti all'interno di un progetto utilizzando l'API?

A5: Sì, è possibile recuperare e modificare gli stili di barra esistenti a livello di codice utilizzando Aspose.Tasks per l'API .NET.