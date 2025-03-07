---
title: Configurazione dei livelli di scala cronologica del diagramma di Gantt in Aspose.Tasks
linktitle: Configurazione dei livelli di scala cronologica in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora Aspose.Tasks per .NET per configurare i livelli di scala temporale nella visualizzazione del diagramma di Gantt per una visualizzazione precisa della sequenza temporale del progetto. #Aspose.Tasks #Progetto MS
weight: 16
url: /it/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurazione dei livelli di scala cronologica del diagramma di Gantt in Aspose.Tasks

## introduzione
Nel panorama dinamico della gestione dei progetti, una visualizzazione efficace è fondamentale per comprendere tempistiche e scadenze. Aspose.Tasks per .NET fornisce un potente set di strumenti e in questo tutorial esploreremo come configurare i livelli di scala temporale per una rappresentazione ottimale nella visualizzazione del diagramma di Gantt. Segui queste istruzioni passo passo per migliorare la visualizzazione del tuo progetto.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
- Conoscenza base di C# e .NET.
-  Aspose.Tasks per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
- Un ambiente di sviluppo configurato per lo sviluppo di applicazioni .NET.
## Importa spazi dei nomi
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Ora analizziamo ogni passaggio dell'esempio fornito.
## Passaggio 1: inizializza il progetto e aggiungi collegamenti alle attività
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Qui creiamo un progetto e stabiliamo collegamenti di attività tra "Attività 1" e "Attività 2".
## Passaggio 2: configura la visualizzazione del diagramma di Gantt
```csharp
var view = (GanttChartView)project.DefaultView;
```
Accedi alla visualizzazione del diagramma di Gantt per la personalizzazione.
## Passaggio 3: ottimizzare il livello della scala temporale media
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Personalizza il livello della scala temporale intermedia per visualizzare le settimane con etichette e allineamenti specifici.
## Passaggio 4: aggiungi il livello di scala cronologica superiore
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Aggiungi un livello di scala temporale superiore per rappresentare i mesi.
## Passaggio 5: personalizza le date del livello intermedio
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Personalizza le etichette dei mesi per una migliore visualizzazione.
## Passaggio 6: impostare la scala temporale del progetto
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Definire la scala temporale del progetto per controllare la sequenza temporale complessiva.
## Passaggio 7: salva il progetto con una scala temporale personalizzata
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Salvare il progetto con le impostazioni della scala temporale definite.
## Conclusione
In conclusione, la configurazione dei livelli di scala temporale in Aspose.Tasks per .NET consente una rappresentazione più personalizzata e visivamente accattivante delle tempistiche del progetto. Questi passaggi ti consentono di creare una visualizzazione del diagramma di Gantt che soddisfa esattamente le tue esigenze di gestione del progetto.
## Domande frequenti
### Posso utilizzare Aspose.Tasks con altre librerie .NET?
Sì, Aspose.Tasks si integra perfettamente con altre librerie .NET, offrendo flessibilità nel tuo stack di sviluppo.
### È disponibile una licenza temporanea a scopo di test?
 Sì, puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/) Per la valutazione.
### Sono disponibili ulteriori opzioni di personalizzazione per la visualizzazione del diagramma di Gantt?
Assolutamente, Aspose.Tasks offre ampie opzioni di personalizzazione per la visualizzazione del diagramma di Gantt per soddisfare le diverse esigenze del progetto.
### Posso eseguire il rendering delle scale temporali in diversi formati?
Certamente, puoi esplorare vari formati e stili per la rappresentazione della scala temporale per adattarla al meglio al contesto del tuo progetto.
### Esiste un forum della community per il supporto di Aspose.Tasks?
 Sì, visita il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e le discussioni della comunità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
