---
title: Anpassa Gantt-diagramkolumner med Aspose.Tasks
linktitle: Gantt-diagramkolumner i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du skräddarsyr Gantt-diagramkolumner i Aspose.Tasks för .NET för att visa specifik uppgiftsinformation effektivt.
type: docs
weight: 21
url: /sv/net/tasks-project-management/gantt-chart-columns/
---
## Introduktion
Gantt-diagram är ett grundläggande verktyg i projektledning och ger en visuell representation av uppgifter, tidslinjer och resurser. Aspose.Tasks för .NET erbjuder kraftfulla funktioner för att manipulera Gantt-diagram, inklusive anpassning av kolumner för att visa specifik uppgiftsinformation. I den här handledningen kommer vi att utforska hur man arbetar med Gantt-diagramkolumner med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Installation: Aspose.Tasks för .NET installerat på ditt system. Om inte, ladda ner och installera den från[här](https://releases.aspose.com/tasks/net/).
2. .NET-utvecklingsmiljö: En praktisk kunskap om C# och .NET-ramverket.
3. Exempel på projektfil: Ha ett exempel på Microsoft Project-fil (`.mpp`) praktiskt att experimentera med. Om du inte har ett, kan du skapa ett enkelt projekt i MS Project och spara det.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks för .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Steg 1: Ladda projektfilen
 Ladda projektfilen med hjälp av`Project` klass tillhandahållen av Aspose.Tasks:
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Steg 2: Definiera Gantt-diagramkolumner
Definiera de kolumner du vill visa i Gantt-diagrammet. Du kan ange inbyggda fält eller skapa anpassade:
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
## Steg 3: Iterera över kolumner
Iterera över de definierade kolumnerna för att komma åt deras egenskaper och visa information:
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
## Steg 4: Spara Gantt-diagrammet till CSV
Spara Gantt-diagrammet med definierade kolumner till en CSV-fil:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Genom att följa dessa steg kan du effektivt arbeta med Gantt-diagramkolumner i Aspose.Tasks för .NET, så att du kan anpassa och visa uppgiftsinformation efter behov.

## Slutsats
Att bemästra manipuleringen av Gantt-diagramkolumner i Aspose.Tasks för .NET öppnar upp för oändliga möjligheter för att skräddarsy projektledningsvisualer efter dina specifika behov. Genom att följa stegen som beskrivs i den här handledningen kan du effektivt hantera uppgiftsinformation och förbättra projektets tydlighet och organisation.
## FAQ's
### F: Kan jag skapa anpassade kolumner i Aspose.Tasks för .NET?
S: Ja, du kan definiera anpassade kolumner för att visa specifika uppgiftsattribut enligt dina projektkrav.
### F: Är Aspose.Tasks för .NET kompatibelt med alla versioner av Microsoft Project-filer?
S: Aspose.Tasks för .NET stöder olika versioner av Microsoft Project-filer, vilket säkerställer kompatibilitet mellan olika projektmiljöer.
### F: Hur kan jag hantera komplexa projektstrukturer med Aspose.Tasks för .NET?
S: Aspose.Tasks för .NET tillhandahåller omfattande API:er och funktioner för att hantera komplexa projektstrukturer, vilket erbjuder flexibilitet och skalbarhet.
### F: Finns det några begränsningar för antalet kolumner jag kan lägga till i ett Gantt-diagram?
S: Aspose.Tasks för .NET erbjuder omfattande anpassningsalternativ, så att du kan lägga till ett betydande antal kolumner till Gantt-diagram utan begränsningar.
### F: Var kan jag hitta ytterligare support och resurser för Aspose.Tasks för .NET?
S: Du kan utforska dokumentationen, gemenskapsforum och supportkanaler som tillhandahålls av Aspose.Tasks för .NET för att få tillgång till omfattande resurser och hjälp.