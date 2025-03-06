---
title: Padroneggiare le visualizzazioni del diagramma di Gantt in Aspose.Tasks
linktitle: Visualizzazioni del diagramma di Gantt in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come personalizzare le visualizzazioni del diagramma di Gantt nei file di Microsoft Project utilizzando Aspose.Tasks per .NET. Guida passo passo per una gestione efficiente dei progetti.
weight: 22
url: /it/net/tasks-project-management/gantt-chart-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare le visualizzazioni del diagramma di Gantt in Aspose.Tasks

## introduzione
I diagrammi di Gantt sono potenti strumenti utilizzati nella gestione dei progetti per visualizzare attività, sequenze temporali e dipendenze. Aspose.Tasks per .NET fornisce solide funzionalità per lavorare con le visualizzazioni del diagramma di Gantt nei file di Microsoft Project. In questo tutorial esploreremo come utilizzare Aspose.Tasks per manipolare le visualizzazioni del diagramma di Gantt, personalizzarne l'aspetto e salvarle come file PDF.
## Prerequisiti
Prima di procedere, assicurati di avere i seguenti prerequisiti:
### 1. Installazione di Aspose.Tasks per .NET
 Assicurati di aver installato Aspose.Tasks per .NET. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/tasks/net/) e seguire le istruzioni di installazione fornite nella documentazione[Qui](https://reference.aspose.com/tasks/net/).
### 2. File di progetto Microsoft
Preparare un file Microsoft Project (`Project2.mpp`) che utilizzerai per lavorare con le visualizzazioni del diagramma di Gantt.
### 3. Conoscenza di base di C# e .NET Framework
Questo tutorial presuppone che tu abbia una conoscenza di base del linguaggio di programmazione C# e del framework .NET.
## Importa spazi dei nomi
Prima di iniziare a lavorare con le visualizzazioni del diagramma di Gantt in Aspose.Tasks, è necessario importare gli spazi dei nomi necessari nel codice C#. Ecco come puoi farlo:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Suddividiamo il codice di esempio fornito in più passaggi e spieghiamo ogni passaggio in dettaglio:
## Passaggio 1: caricare il file di progetto
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Questo passaggio prevede il caricamento del file Microsoft Project (`Project2.mpp` ) in un'istanza di`Project` classe.
## Passaggio 2: impostare la data dello stato
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Qui impostiamo la data di stato del progetto sulla sua data di inizio.
## Passaggio 3: accedi alla visualizzazione del diagramma di Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Accediamo alla visualizzazione del diagramma di Gantt dal progetto. Aspose.Tasks consente di accedere a visualizzazioni come diagramma di Gantt, diagramma di rete e utilizzo delle attività.
## Passaggio 4: personalizza la visualizzazione del diagramma di Gantt
Ora personalizziamo vari aspetti della visualizzazione del diagramma di Gantt:
### Imposta l'arrotondamento della barra
```csharp
view.BarRounding = false;
```
Imposta se le barre del diagramma di Gantt verranno arrotondate al giorno più vicino.
### Imposta la dimensione della barra
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Ciò determina l'altezza delle barre di Gantt nel grafico.
### Nascondi le barre di rollup
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Specifica se le barre di rollup verranno nascoste durante l'espansione delle attività di riepilogo.
### Imposta il colore del tempo non lavorativo
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Definisce il colore per il tempo non lavorativo nel diagramma di Gantt.
### Barre Gantt arrotolabili
```csharp
view.RollUpGanttBars = true;
```
Specifica se le barre del diagramma di Gantt devono essere raggruppate.
### Mostra le divisioni della barra
```csharp
view.ShowBarSplits = true;
```
Determina se è necessario visualizzare le suddivisioni delle attività nel diagramma di Gantt.
### Mostra disegni
```csharp
view.ShowDrawings = true;
```
Specifica se devono essere visualizzati i disegni nel diagramma di Gantt.
### Percentuale dimensione scala temporale
```csharp
view.TimescaleSizePercentage = 10;
```
Imposta una percentuale per regolare la spaziatura tra le unità sul livello della scala cronologica.
## Passaggio 5: salva la visualizzazione del diagramma di Gantt come PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Infine, salviamo la visualizzazione del diagramma di Gantt personalizzata come file PDF.
## Conclusione
In questo tutorial, abbiamo imparato come lavorare con le visualizzazioni del diagramma di Gantt in Aspose.Tasks per .NET. Seguendo i passaggi forniti, puoi manipolare e personalizzare in modo efficiente i diagrammi di Gantt in base ai requisiti del tuo progetto.
## Domande frequenti
### D: Posso personalizzare ulteriormente l'aspetto delle barre del diagramma di Gantt?
R: Sì, Aspose.Tasks offre ampie opzioni per personalizzare l'aspetto delle barre del diagramma di Gantt, inclusi colori, forme e dimensioni.
### D: Aspose.Tasks è compatibile con diverse versioni dei file Microsoft Project?
R: Sì, Aspose.Tasks supporta varie versioni di file Microsoft Project, inclusi i formati MPP, MPT e XML.
### D: Posso esportare le visualizzazioni del diagramma di Gantt in formati diversi dal PDF?
R: Assolutamente, Aspose.Tasks supporta l'esportazione delle visualizzazioni del diagramma di Gantt in più formati, inclusi PNG, JPEG e XPS.
### D: Aspose.Tasks offre supporto per algoritmi di pianificazione di progetti complessi?
R: Sì, Aspose.Tasks fornisce algoritmi di pianificazione avanzati per gestire in modo efficace pianificazioni di progetti complessi.
### D: Esiste un forum della community in cui posso cercare aiuto o condividere le mie esperienze con Aspose.Tasks?
 R: Sì, puoi visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per interagire con altri utenti, porre domande e trovare soluzioni alle tue domande.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
