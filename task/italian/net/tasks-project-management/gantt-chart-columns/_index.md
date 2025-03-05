---
title: Personalizza le colonne del diagramma di Gantt con Aspose.Tasks
linktitle: Colonne del diagramma di Gantt in Aspose.Tasks
second_title: Aspose.Tasks API .NET
description: Scopri come personalizzare le colonne del diagramma di Gantt in Aspose.Tasks per .NET per visualizzare in modo efficiente informazioni su attività specifiche.
type: docs
weight: 21
url: /it/net/tasks-project-management/gantt-chart-columns/
---
## introduzione
I diagrammi di Gantt sono uno strumento fondamentale nella gestione dei progetti, poiché forniscono una rappresentazione visiva di attività, tempistiche e risorse. Aspose.Tasks per .NET offre potenti funzionalità per manipolare i diagrammi di Gantt, inclusa la personalizzazione delle colonne per visualizzare informazioni su attività specifiche. In questo tutorial esploreremo come lavorare con le colonne del diagramma di Gantt utilizzando Aspose.Tasks per .NET.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Installazione: Aspose.Tasks per .NET installato sul tuo sistema. In caso contrario, scaricalo e installalo da[Qui](https://releases.aspose.com/tasks/net/).
2. Ambiente di sviluppo .NET: conoscenza pratica di C# e del framework .NET.
3. File di progetto di esempio: disporre di un file di Microsoft Project di esempio (`.mpp`) utile per sperimentare. Se non ne hai uno, puoi creare un semplice progetto in MS Project e salvarlo.

## Importa spazi dei nomi
Innanzitutto, devi importare gli spazi dei nomi necessari per lavorare con Aspose.Tasks per .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Passaggio 1: caricare il file di progetto
 Caricare il file di progetto utilizzando il file`Project` classe fornita da Aspose.Tasks:
```csharp
// Il percorso della directory dei documenti.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Passaggio 2: definire le colonne del diagramma di Gantt
Definisci le colonne che desideri visualizzare nel diagramma di Gantt. Puoi specificare campi integrati o crearne di personalizzati:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Passaggio 3: ripetizione delle colonne
Scorrere sulle colonne definite per accedere alle relative proprietà e visualizzare le informazioni:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Passaggio 4: salva il diagramma di Gantt in CSV
Salva il diagramma di Gantt con le colonne definite in un file CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Seguendo questi passaggi, puoi lavorare in modo efficace con le colonne del diagramma di Gantt in Aspose.Tasks per .NET, consentendoti di personalizzare e visualizzare le informazioni sulle attività secondo necessità.

## Conclusione
Padroneggiare la manipolazione delle colonne del diagramma di Gantt in Aspose.Tasks per .NET apre infinite possibilità per personalizzare le immagini di gestione dei progetti in base alle tue esigenze specifiche. Seguendo i passaggi descritti in questo tutorial, puoi gestire in modo efficiente le informazioni sulle attività e migliorare la chiarezza e l'organizzazione del progetto.
## Domande frequenti
### D: Posso creare colonne personalizzate in Aspose.Tasks per .NET?
R: Sì, puoi definire colonne personalizzate per visualizzare attributi specifici dell'attività in base ai requisiti del tuo progetto.
### D: Aspose.Tasks per .NET è compatibile con tutte le versioni dei file Microsoft Project?
R: Aspose.Tasks per .NET supporta varie versioni di file Microsoft Project, garantendo la compatibilità tra diversi ambienti di progetto.
### D: Come posso gestire strutture di progetto complesse con Aspose.Tasks per .NET?
R: Aspose.Tasks per .NET fornisce API e funzionalità complete per gestire strutture di progetti complessi, offrendo flessibilità e scalabilità.
### D: Esistono limitazioni al numero di colonne che posso aggiungere a un diagramma di Gantt?
R: Aspose.Tasks per .NET offre ampie opzioni di personalizzazione, consentendo di aggiungere un numero significativo di colonne ai diagrammi di Gantt senza limitazioni.
### D: Dove posso trovare supporto e risorse aggiuntivi per Aspose.Tasks per .NET?
R: È possibile esplorare la documentazione, i forum della community e i canali di supporto forniti da Aspose.Tasks per .NET per accedere a risorse e assistenza complete.