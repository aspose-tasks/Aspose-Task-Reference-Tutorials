---
title: Configurazione delle opzioni di visualizzazione di MS Project in Aspose.Tasks
linktitle: Configurazione delle opzioni di visualizzazione del progetto in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come configurare le opzioni di visualizzazione di MS Project a livello di codice utilizzando Aspose.Tasks per .NET. Personalizza l'aspetto del tuo progetto senza sforzo.
weight: 17
url: /it/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Configurazione delle opzioni di visualizzazione di MS Project in Aspose.Tasks

## introduzione
Microsoft Project offre numerose opzioni di visualizzazione per personalizzare l'aspetto del tuo progetto. Aspose.Tasks per .NET fornisce un framework robusto per manipolare queste opzioni a livello di codice. In questo tutorial, esploreremo come configurare le opzioni di visualizzazione di MS Project utilizzando Aspose.Tasks.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
1.  Aspose.Tasks per .NET: scarica e installa la libreria da[Qui](https://releases.aspose.com/tasks/net/).
2. File Microsoft Project: disporre di un file MS Project valido (.mpp) pronto per applicare le opzioni di visualizzazione.
3. Conoscenza di base di C#: è richiesta familiarità con il linguaggio di programmazione C#.

## Importazione di spazi dei nomi
Innanzitutto, assicurati di importare gli spazi dei nomi necessari nel tuo codice C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Passaggio 1: caricare il file di progetto
 Caricare il file MS Project utilizzando il file`Project` classe fornita da Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Passaggio 2: configura le opzioni di visualizzazione
Ora configuriamo le varie opzioni di visualizzazione disponibili in MS Project:
### Disabilita gli avvisi di pianificazione delle attività
Per disabilitare gli avvisi relativi ai conflitti di pianificazione con le attività pianificate manualmente (disponibile per Project 2010 e versioni successive):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Aggiungi spazio prima dell'etichetta
Impostare per aggiungere uno spazio prima del valore numerico e dell'abbreviazione dell'ora:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configura la visualizzazione delle etichette per le unità di tempo
Personalizza la modalità di visualizzazione delle diverse unità di tempo:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Mostra attività di riepilogo del progetto
Visualizza informazioni di riepilogo sull'intero progetto su una singola riga:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Abilita suggerimenti per la pianificazione delle attività
Consenti la visualizzazione di suggerimenti per i conflitti di pianificazione con le attività pianificate manualmente:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Sottolinea i collegamenti ipertestuali
Imposta per sottolineare i collegamenti ipertestuali all'interno del progetto:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Passaggio 3: salva il progetto
Infine, salva il progetto con le opzioni di visualizzazione applicate:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusione
In questo tutorial, abbiamo imparato come configurare le opzioni di visualizzazione di MS Project utilizzando Aspose.Tasks per .NET. Con queste funzionalità, puoi personalizzare in modo efficiente l'aspetto dei file di progetto a livello di codice.
## Domande frequenti
### D: Posso applicare queste opzioni di visualizzazione solo ad attività specifiche?
R: Sì, puoi applicare selettivamente le opzioni di visualizzazione alle singole attività utilizzando l'API Aspose.Tasks.
### D: Queste opzioni di visualizzazione influiscono sui dati del progetto sottostante?
R: No, queste opzioni modificano solo la rappresentazione visiva del progetto e non alterano i dati sottostanti.
### D: queste opzioni di visualizzazione sono compatibili con tutte le versioni di Microsoft Project?
R: No, alcune opzioni potrebbero essere specifiche per determinate versioni di MS Project. Fare riferimento alla documentazione per i dettagli sulla compatibilità.
### D: Posso ripristinare le opzioni di visualizzazione alle impostazioni predefinite?
R: Sì, puoi ripristinare le opzioni di visualizzazione sui valori predefiniti utilizzando l'API Aspose.Tasks.
### D: Esistono limitazioni alla personalizzazione delle opzioni di visualizzazione a livello di codice?
R: Sebbene Aspose.Tasks offra ampie funzionalità di personalizzazione, alcune opzioni di visualizzazione potrebbero non essere accessibili a livello di programmazione a causa delle limitazioni nel formato di file MS Project.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
