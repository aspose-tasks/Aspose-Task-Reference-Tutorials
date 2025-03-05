---
title: Intervalli ricorrenti senza sforzo del progetto MS in Aspose.Tasks
linktitle: Gestione degli intervalli ricorrenti in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come gestire senza sforzo gli intervalli ricorrenti in MS Project utilizzando Aspose.Tasks per .NET.
type: docs
weight: 12
url: /it/net/rate-recurring-tasks/recurring-intervals/
---
## introduzione
Stai cercando di gestire gli intervalli ricorrenti in modo efficiente nei file di Microsoft Project utilizzando Aspose.Tasks per .NET? Questo tutorial completo ti guiderà attraverso il processo passo dopo passo, assicurandoti di poter gestire senza sforzo gli intervalli ricorrenti nei tuoi progetti. Prima di immergerci nel tutorial, esaminiamo alcuni prerequisiti per assicurarci di essere pronti per iniziare.
## Prerequisiti
Prima di procedere con questo tutorial, assicurati di avere quanto segue:
1. Conoscenza della programmazione C#: è richiesta una conoscenza di base del linguaggio di programmazione C# e della sua sintassi.
2. Visual Studio installato: assicurati di avere Visual Studio installato sul tuo sistema per codificare e compilare le applicazioni .NET.
3. Aspose.Tasks per .NET Library: scarica e installa la libreria Aspose.Tasks per .NET. Puoi ottenerlo da[Qui](https://releases.aspose.com/tasks/net/).

## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari per accedere alle funzionalità fornite dalla libreria Aspose.Tasks per .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Ora suddividiamo ciascun esempio in più passaggi e spieghiamoli in dettaglio.
## Passaggio 1: inizializzare l'oggetto del progetto:
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Qui inizializziamo una nuova istanza di`Project` class fornendo il percorso del file Microsoft Project.
## Passaggio 2: impostare la data dello stato:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Questo passaggio imposta la data di stato del progetto sulla data di inizio.
## Passaggio 3: accedere alla visualizzazione del diagramma di Gantt:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Accediamo alla visualizzazione Diagramma di Gantt del progetto.
## Passaggio 4: leggere la riga di avanzamento:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Questo passaggio recupera l'intervallo ricorrente per le linee di avanzamento dalla visualizzazione del diagramma di Gantt.
## Passaggio 5: visualizzare le informazioni sull'intervallo:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Qui vengono visualizzate le informazioni sull'intervallo, il numero della settimana settimanale e i giorni settimanali.
## Passaggio 6: ridefinire l'intervallo ricorrente:
```csharp
var newInterval = new RecurringInterval();
```
 Creiamo una nuova istanza di`RecurringInterval` per ridefinire l'intervallo ricorrente.
## Passaggio 7: imposta le linee di avanzamento mensili:
```csharp
// Imposta le linee di avanzamento mensili per giorno.
interval.MonthlyDay = true;
// Imposta il numero giornaliero delle linee di avanzamento mensili.
interval.MonthlyDayDayNumber = 1;
// Imposta il numero mensile delle linee di avanzamento mensili.
interval.MonthlyDayMonthNumber = 1;
// Imposta le linee di avanzamento in base al primo o all'ultimo giorno predefinito.
interval.MonthlyFirstLast = true;
// Imposta il tipo del primo o dell'ultimo giorno delle linee di avanzamento mensili.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Imposta il numero mensile di linee di avanzamento.
interval.MonthlyFirstLastMonthNumber = 1;
```
Questi passaggi configurano le linee di avanzamento mensili in base ai parametri specificati.
## Passaggio 8: aggiornamento delle linee di avanzamento:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Aggiorniamo le linee di avanzamento nella visualizzazione del diagramma di Gantt con l'intervallo ricorrente appena definito.
## Passaggio 9: salva il progetto come PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Infine, salviamo il progetto con l'intervallo ricorrente aggiornato come file PDF.

## Conclusione
In conclusione, la gestione degli intervalli ricorrenti nei file Microsoft Project utilizzando Aspose.Tasks per .NET è resa semplice grazie alle funzionalità complete fornite dalla libreria. Seguendo la guida passo passo delineata in questo tutorial, puoi gestire in modo efficiente gli intervalli ricorrenti nei tuoi progetti, migliorando la produttività e l'organizzazione.
### Domande frequenti
### Posso utilizzare Aspose.Tasks per .NET con altri linguaggi di programmazione?
Sì, Aspose.Tasks per .NET può essere utilizzato con qualsiasi linguaggio supportato da .NET come C# e VB.NET.
### È disponibile una versione di prova per Aspose.Tasks per .NET?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Tasks per .NET?
 È possibile ottenere supporto dal forum Aspose.Tasks[Qui](https://forum.aspose.com/c/tasks/15).
### Posso acquistare una licenza temporanea per Aspose.Tasks per .NET?
 Sì, puoi acquistare una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare la documentazione completa per Aspose.Tasks per .NET?
 La documentazione completa è reperibile[Qui](https://reference.aspose.com/tasks/net/).