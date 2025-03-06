---
title: Padroneggiare le visualizzazioni di utilizzo delle attività in Aspose.Tasks per .NET
linktitle: Configurazione delle visualizzazioni di utilizzo delle attività in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Esplora Aspose.Tasks per .NET e scopri come configurare le visualizzazioni di utilizzo delle attività. Personalizza le impostazioni della scala temporale e migliora gli elementi visivi della gestione del progetto.
weight: 24
url: /it/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Padroneggiare le visualizzazioni di utilizzo delle attività in Aspose.Tasks per .NET

## introduzione
Nell'ambito della gestione dei progetti, visualizzare l'utilizzo delle attività è fondamentale per una pianificazione ed esecuzione efficaci. Aspose.Tasks per .NET fornisce una soluzione solida per il rendering delle visualizzazioni di utilizzo delle attività, consentendo di personalizzare le impostazioni della scala temporale e i formati di presentazione. In questo tutorial verranno illustrati i passaggi per configurare le visualizzazioni di utilizzo delle attività utilizzando Aspose.Tasks.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
1.  Aspose.Tasks per .NET: assicurati di avere la libreria Aspose.Tasks integrata nel tuo progetto .NET. Puoi scaricarlo[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente .NET: disporre di un ambiente .NET funzionante configurato sul proprio computer.
## Importa spazi dei nomi
Nel tuo progetto .NET, importa gli spazi dei nomi necessari per accedere alle funzionalità Aspose.Tasks. Aggiungi le seguenti righe al tuo codice:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Passaggio 1: impostare il percorso della directory dei documenti
 Prima di lavorare con le funzionalità Aspose.Tasks, imposta il percorso della directory dei tuoi documenti. Sostituire`"Your Document Directory"` con il percorso vero e proprio.
```csharp
String DataDir = "Your Document Directory";
```
## Passaggio 2: caricare il progetto
 Inizializzare Aspose.Tasks`Project` oggetto caricando il file di progetto (ad esempio, TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Passaggio 3: definire le opzioni di salvataggio
 Creare un`SaveOptions`oggetto per specificare le opzioni di rendering. Imposta la scala temporale su "Giorni" e il formato della presentazione su "TaskUsage".
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Passaggio 4: salva con la cronologia dei giorni
Salvare il progetto con le impostazioni di scala temporale predefinite di 'Giorni'.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Passaggio 5: risparmia con la scala cronologica ThirdsOfMonths
Modifica le impostazioni della scala temporale in "ThirdsOfMonths" e salva il progetto.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Passaggio 6: salva con la cronologia dei mesi
Imposta la scala temporale su "Mesi" e salva il progetto con le impostazioni aggiornate.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Conclusione
La configurazione delle visualizzazioni di utilizzo delle attività con Aspose.Tasks per .NET è un processo semplice. Personalizzando le impostazioni della scala temporale, puoi adattare la visualizzazione delle attività del tuo progetto in base alle tue esigenze specifiche.
 Sentiti libero di esplorare più caratteristiche e funzionalità nel[documentazione](https://reference.aspose.com/tasks/net/).
## Domande frequenti
### Posso personalizzare la scala temporale oltre le impostazioni predefinite?
Sì, puoi impostare una scala temporale personalizzata specificando gli intervalli e le unità.
### Sono disponibili altri formati di presentazione?
Aspose.Tasks supporta vari formati di presentazione, tra cui GanttChart, ResourceUsage e altro.
### Aspose.Tasks è compatibile con diversi formati di file di progetto?
Sì, Aspose.Tasks supporta i formati di file di progetto più diffusi come MPP, XML e CSV.
### Posso applicare diverse impostazioni di scala temporale ad attività specifiche?
Assolutamente, puoi personalizzare le impostazioni della scala temporale per le singole attività all'interno del tuo progetto.
### Come posso ottenere supporto o chiedere assistenza per Aspose.Tasks?
 Visitare il[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) per il supporto e l’orientamento della comunità.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
