---
date: 2026-04-06
description: Scopri come modificare lo stile delle barre e personalizzare i colori
  delle barre in Aspose.Tasks per .NET per migliorare la visualizzazione del progetto.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Barra di stile in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Come cambiare lo stile delle barre in Aspose.Tasks
url: /it/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come modificare lo stile delle barre in Aspose.Tasks

## Introduzione

Se hai bisogno di **modificare l'aspetto della barra** in un file Microsoft Project, Aspose.Tasks per .NET ti offre il pieno controllo su colori, forme e stili del testo delle barre. Personalizzando i colori delle barre e altri attributi visivi, puoi rendere i piani di progetto molto più facili da leggere e più allineati all'identità visiva della tua organizzazione. In questo tutorial ti guideremo attraverso un esempio completo, passo‑per‑passo, che mostra come modificare lo stile delle barre, dal caricamento di un progetto all'esportazione con le nuove regole visive applicate.

## Risposte rapide
- **Cosa posso stilizzare?** Barre, milestone e testo delle attività nei diagrammi di Gantt.  
- **Quale formato supporta le barre stilizzate?** PDF, XLSX, HTML e MPP nativo quando salvato con `PdfSaveOptions`.  
- **È necessaria una licenza?** È richiesta una licenza commerciale per l'uso in produzione; una versione di prova gratuita è sufficiente per i test.  
- **Posso applicare più stili?** Sì – aggiungi quanti oggetti `BarStyle` desideri.  
- **È compatibile con .NET Core?** Assolutamente – funziona con .NET Framework e .NET Core/5/6+.

## Cos'è lo stile delle barre in Aspose.Tasks?

Lo stile delle barre ti consente di definire regole visive che il motore di Aspose.Tasks applica durante il rendering dei diagrammi di Gantt. Ogni regola (un **BarStyle**) si riferisce a un tipo di elemento specifico — attività, milestone o attività di riepilogo — e permette di impostare colori, forme e persino testo personalizzato.

## Perché personalizzare i colori delle barre?

Personalizzare i colori delle barre aiuta le parti interessate a identificare immediatamente percorsi critici, attività in ritardo o milestone. Inoltre consente di abbinare gli schemi di colore aziendali, rendendo i report professionali e coerenti con il brand.

## Prerequisiti

Prima di iniziare, assicurati di avere:

1. **Aspose.Tasks for .NET** – scaricalo dalla [pagina di download](https://releases.aspose.com/tasks/net/).  
2. Un ambiente di sviluppo che supporti .NET (Framework 4.6+, .NET Core 3.1+ o versioni successive).  
3. Familiarità di base con C# – gli esempi utilizzano codice semplice e autonomo.

## Importare gli spazi dei nomi

Prima, importa gli spazi dei nomi che contengono le classi che utilizzeremo:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Passo 1: Caricare il progetto

Carica un file MPP esistente (o creane uno nuovo) in modo da avere un oggetto progetto con cui lavorare:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Passo 2: Configurare le opzioni di salvataggio

Crea un'istanza di `PdfSaveOptions` e inizializza la collezione `BarStyles` dove memorizzeremo i nostri stili personalizzati:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Passo 3: Definire lo stile della barra

Ora creiamo un oggetto `BarStyle` e impostiamo le proprietà che controllano l'aspetto della barra. Qui è dove **personalizziamo i colori delle barre** e le forme:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Passo 4: Personalizzare il convertitore di testo (Opzionale)

Se vuoi modificare il testo che appare sulla barra, puoi assegnare un convertitore personalizzato. L'esempio aggiunge il prefisso ai nomi delle attività che non iniziano già con “T”:

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

## Passo 5: Aggiungere lo stile della barra alle opzioni

Aggiungi lo stile completamente configurato alla collezione `BarStyles` delle opzioni di salvataggio:

```csharp
options.BarStyles.Add(style);
```

## Passo 6: Salvare il progetto

Infine, esporta il progetto. Il PDF (o altro formato) renderizzerà il diagramma di Gantt utilizzando lo stile della barra che abbiamo definito:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Problemi comuni e soluzioni

| Problema | Motivo | Soluzione |
|----------|--------|-----------|
| **Stile della barra non applicato** | La collezione `BarStyles` era vuota o non collegata alle opzioni di salvataggio. | Assicurati di aggiungere il `BarStyle` a `options.BarStyles` prima di chiamare `Save`. |
| **I colori appaiono diversi nel PDF** | Il rendering PDF potrebbe utilizzare un profilo colore diverso. | Usa valori standard di `System.Drawing.Color` o definisci colori ARGB personalizzati. |
| **Il convertitore di testo genera un riferimento nullo** | La proprietà `Tsk.Name` dell'attività è null per alcune attività. | Aggiungi un controllo null prima di accedere a `task.Get(Tsk.Name)`. |

## FAQ

### Q1: Posso applicare più stili di barra a un singolo progetto?

A1: Sì, è possibile definire e applicare più stili di barra a diversi tipi di attività all'interno dello stesso progetto.

### Q2: È possibile modificare dinamicamente gli stili delle barre durante l'esecuzione?

A2: Sì, è possibile modificare dinamicamente gli stili delle barre in base a determinate condizioni o preferenze dell'utente all'interno della tua applicazione.

### Q3: Aspose.Tasks supporta l'esportazione di progetti con barre stilizzate in diversi formati di file?

A3: Sì, Aspose.Tasks supporta l'esportazione di progetti con barre stilizzate in vari formati come PDF, XLSX e HTML.

### Q4: Esistono stili di barra predefiniti disponibili in Aspose.Tasks?

A4: Sebbene Aspose.Tasks fornisca stili di barra predefiniti, gli sviluppatori possono anche creare stili di barra personalizzati su misura per le esigenze del loro progetto.

### Q5: Posso recuperare e modificare gli stili di barra esistenti in un progetto usando l'API?

A5: Sì, è possibile recuperare e modificare gli stili di barra esistenti programmaticamente usando l'API di Aspose.Tasks per .NET.

## Domande frequenti

**Q: Come modifico il colore della barra per le attività regolari invece delle milestone?**  
A: Imposta `style.ItemType = BarItemType.Task;` e assegna `style.BarColor` al `Color` desiderato.

**Q: Posso usare questo approccio per stilizzare le barre durante l'esportazione in HTML?**  
A: Sì. Usa `HtmlSaveOptions` e popola la sua collezione `BarStyles` allo stesso modo.

**Q: Esiste un limite al numero di stili di barra che posso definire?**  
A: Praticamente no; puoi aggiungerne quanti ne servono, ma tieni presente le prestazioni per collezioni molto grandi.

**Q: Devo chiamare `project.Calculate()` dopo aver modificato gli stili?**  
A: No, gli stili vengono applicati durante l'operazione di salvataggio; il ricalcolo è necessario solo per modifiche alla pianificazione.

---

**Ultimo aggiornamento:** 2026-04-06  
**Testato con:** Aspose.Tasks 24.11 for .NET  
**Autore:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}