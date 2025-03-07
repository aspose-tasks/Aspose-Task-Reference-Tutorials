---
title: Pas Gantt-diagramkolommen aan met Aspose.Tasks
linktitle: Gantt-diagramkolommen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Gantt-diagramkolommen in Aspose.Tasks voor .NET kunt aanpassen om specifieke taakinformatie efficiënt weer te geven.
weight: 21
url: /nl/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pas Gantt-diagramkolommen aan met Aspose.Tasks

## Invoering
Gantt-diagrammen zijn een fundamenteel hulpmiddel bij projectmanagement en bieden een visuele weergave van taken, tijdlijnen en bronnen. Aspose.Tasks voor .NET biedt krachtige mogelijkheden om Gantt-diagrammen te manipuleren, inclusief het aanpassen van kolommen om specifieke taakinformatie weer te geven. In deze zelfstudie onderzoeken we hoe u met Gantt-diagramkolommen kunt werken met behulp van Aspose.Tasks voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Installatie: Aspose.Tasks voor .NET geïnstalleerd op uw systeem. Als dit niet het geval is, downloadt en installeert u het vanaf[hier](https://releases.aspose.com/tasks/net/).
2. .NET-ontwikkelomgeving: praktische kennis van C# en het .NET-framework.
3. Voorbeeldprojectbestand: Zorg voor een voorbeeld van een Microsoft Project-bestand (`.mpp`) handig om mee te experimenteren. Als u er geen heeft, kunt u in MS Project een eenvoudig project maken en opslaan.

## Naamruimten importeren
Eerst moet u de benodigde naamruimten importeren om met Aspose.Tasks voor .NET te kunnen werken:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Stap 1: Laad het projectbestand
 Laad het projectbestand met behulp van de`Project` klasse aangeboden door Aspose.Taken:
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Stap 2: Definieer Gantt-diagramkolommen
Definieer de kolommen die u wilt weergeven in het Gantt-diagram. U kunt ingebouwde velden opgeven of aangepaste velden maken:
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
## Stap 3: Herhaal de kolommen
Herhaal de gedefinieerde kolommen om toegang te krijgen tot hun eigenschappen en informatie weer te geven:
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
## Stap 4: Sla het Gantt-diagram op in CSV
Sla het Gantt-diagram met gedefinieerde kolommen op in een CSV-bestand:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Door deze stappen te volgen, kunt u effectief werken met Gantt-diagramkolommen in Aspose.Tasks voor .NET, zodat u taakinformatie indien nodig kunt aanpassen en weergeven.

## Conclusie
Het beheersen van de manipulatie van Gantt-diagramkolommen in Aspose.Tasks voor .NET opent eindeloze mogelijkheden voor het afstemmen van projectmanagementvisuals op uw specifieke behoeften. Door de stappen in deze zelfstudie te volgen, kunt u taakinformatie efficiënt verwerken en de duidelijkheid en organisatie van het project verbeteren.
## Veelgestelde vragen
### Vraag: Kan ik aangepaste kolommen maken in Aspose.Tasks voor .NET?
A: Ja, u kunt aangepaste kolommen definiëren om specifieke taakkenmerken weer te geven op basis van uw projectvereisten.
### Vraag: Is Aspose.Tasks voor .NET compatibel met alle versies van Microsoft Project-bestanden?
A: Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project-bestanden, waardoor compatibiliteit tussen verschillende projectomgevingen wordt gegarandeerd.
### Vraag: Hoe kan ik omgaan met complexe projectstructuren met Aspose.Tasks voor .NET?
A: Aspose.Tasks voor .NET biedt uitgebreide API's en functies voor het beheren van complexe projectstructuren en biedt flexibiliteit en schaalbaarheid.
### Vraag: Zijn er beperkingen aan het aantal kolommen dat ik aan een Gantt-diagram kan toevoegen?
A: Aspose.Tasks voor .NET biedt uitgebreide aanpassingsopties, waardoor u zonder beperkingen een aanzienlijk aantal kolommen aan Gantt-diagrammen kunt toevoegen.
### Vraag: Waar kan ik aanvullende ondersteuning en bronnen vinden voor Aspose.Tasks voor .NET?
A: U kunt de documentatie, communityforums en ondersteuningskanalen van Aspose.Tasks voor .NET verkennen om toegang te krijgen tot uitgebreide bronnen en hulp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
