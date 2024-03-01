---
title: Gestione delle linee di avanzamento del progetto MS con Aspose.Tasks
linktitle: Gestione delle linee di avanzamento in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come manipolare le linee di avanzamento nei file MS Project utilizzando Aspose.Tasks per .NET, migliorando la visualizzazione e la gestione del progetto.
type: docs
weight: 15
url: /it/net/project-management-integration/progress-lines/
---
## introduzione
Microsoft Project (MS Project) è un potente strumento per la gestione dei progetti, che consente agli utenti di tenere traccia di vari aspetti dei loro progetti. Una caratteristica cruciale di MS Project è la capacità di visualizzare le linee di avanzamento, che aiutano le parti interessate a comprendere lo stato e la traiettoria del progetto. In questo tutorial esploreremo come gestire le linee di avanzamento in MS Project utilizzando la libreria Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Visual Studio: installa Visual Studio o qualsiasi altro ambiente di sviluppo .NET preferito.
2.  Aspose.Tasks per .NET: Scarica e installa Aspose.Tasks per .NET da[Qui](https://releases.aspose.com/tasks/net/).
3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile.

## Importazione di spazi dei nomi
Per iniziare, importiamo gli spazi dei nomi necessari:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Ora analizziamo ogni passaggio nella gestione delle linee di avanzamento:
## Passaggio 1: caricare il file di progetto
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Qui carichiamo il file MS Project`Project2.mpp` e impostarne la data di stato.
## Passaggio 2: definire la visualizzazione del diagramma di Gantt
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Trasformiamo la vista del progetto in una vista del diagramma di Gantt per un'ulteriore manipolazione.
## Passaggio 3: definire le linee di avanzamento
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Inizializziamo le linee di avanzamento per la visualizzazione del diagramma di Gantt.
## Passaggio 4: configura le impostazioni della linea di avanzamento
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Qui impostiamo varie proprietà per le linee di avanzamento, come il colore della linea, il motivo, il carattere, ecc.
## Passaggio 5: verificare la configurazione delle linee di avanzamento
```csharp
// Impostazioni delle linee di avanzamento dell'output
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Emetti altre impostazioni...
```
Produciamo le impostazioni delle linee di avanzamento configurate per la verifica.
## Passaggio 6: salva il file di progetto
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Infine, salviamo il file di progetto modificato con le linee di avanzamento.

## Conclusione
In questo tutorial, abbiamo imparato come gestire le linee di avanzamento di MS Project utilizzando Aspose.Tasks per .NET. Seguendo questi passaggi, puoi personalizzare e visualizzare in modo efficace le linee di avanzamento nei file MS Project a livello di codice.
## Domande frequenti
### D: Posso personalizzare ulteriormente l'aspetto delle linee di avanzamento?
R: Sì, puoi regolare varie proprietà come il colore della linea, il motivo e il carattere in base alle tue esigenze.
### D: Aspose.Tasks supporta altre funzionalità di gestione dei progetti?
R: Sì, Aspose.Tasks fornisce ampio supporto per la manipolazione di vari aspetti dei file MS Project, incluse attività, risorse e calendari.
### D: Posso integrare Aspose.Tasks con altre librerie .NET?
R: Assolutamente, Aspose.Tasks è progettato per integrarsi perfettamente con altre librerie .NET, consentendoti di migliorare ulteriormente le tue applicazioni di gestione dei progetti.
### D: Esiste un forum della community per il supporto di Aspose.Tasks?
 R: Sì, puoi trovare risorse utili e chiedere assistenza nel forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### D: Aspose.Tasks offre licenze temporanee a scopo di valutazione?
 R: Sì, puoi ottenere una licenza temporanea per la valutazione[Qui](https://purchase.aspose.com/temporary-license/).