---
title: MS Project med Spreadsheet 2003-alternativ för Aspose.Tasks
linktitle: Kalkylblad 2003 Spara alternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Master Spreadsheet 2003 Spara MS Project Options med Aspose.Tasks för .NET. Sömlöst anpassa och spara MS Project-filer programmatiskt.
weight: 19
url: /sv/net/saving-options/spreadsheet-2003-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project med Spreadsheet 2003-alternativ för Aspose.Tasks

## Introduktion
I den här handledningen kommer vi att fördjupa oss i att utnyttja Aspose.Tasks för .NET för att använda Spreadsheet 2003 Save MS Project Options. Detta kraftfulla verktyg möjliggör sömlös manipulation och anpassning av MS Project-filer i .NET-miljön. Låt oss bryta ner processen steg för steg.
## Förutsättningar
Innan vi börjar med den här handledningen, se till att du har följande förutsättningar:
1.  Installation av Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[nedladdningslänk](https://releases.aspose.com/tasks/net/).
2. Bekantskap med C#-programmering: Grundläggande förståelse för programmeringsspråket C# är nödvändig för att förstå de begrepp som diskuteras i denna handledning.

## Importera namnområden
Börja med att importera de nödvändiga namnrymden till ditt C#-projekt:
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Dessa namnrymder ger tillgång till de funktioner som behövs för att spara MS Project-filer med Spreadsheet 2003-format och anpassa visningsalternativen.
## Steg 1: Ladda projektet
Först laddar du MS Project-filen med Aspose.Tasks:
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
 Byta ut`"Your Document Directory"`med den faktiska katalogsökvägen där din MS Project-fil finns.
## Steg 2: Definiera sparalternativ
 Definiera Spreadsheet 2003 Spara alternativ genom att skapa en instans av`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Steg 3: Anpassa vykolumner
Anpassa vykolumnerna för Gantt-diagram, Resursvy och Tilldelningsvy:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
Dessa steg lägger till anpassade kolumner till respektive vy, vilket förbättrar visualiserings- och analysmöjligheterna för MS Project-filen.
## Steg 4: Spara projektet
Slutligen, spara projektet med de angivna alternativen:
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
Detta kommando sparar det modifierade projektet med Spreadsheet 2003-format och de anpassade vykolumnerna.

## Slutsats
Genom att använda Aspose.Tasks för .NET, särskilt Spreadsheet 2003 Save MS Project Options, ger utvecklare möjlighet att effektivt hantera och anpassa MS Project-filer programmatiskt. Genom att följa den steg-för-steg-guide som beskrivs i den här handledningen kan du sömlöst integrera dessa funktioner i dina .NET-applikationer, vilket ökar produktiviteten och flexibiliteten.

## FAQ's
### F: Kan Aspose.Tasks för .NET användas i både webb- och skrivbordsapplikationer?
S: Ja, Aspose.Tasks för .NET kan sömlöst integreras i både webb- och stationära applikationer, vilket ger konsekvent funktionalitet på alla plattformar.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
S: Ja, du kan få tillgång till en gratis testversion av Aspose.Tasks för .NET från[hemsida](https://releases.aspose.com/), så att du kan utforska dess funktioner innan du gör ett köp.
### F: Finns det några begränsningar för att anpassa vykolumner med Aspose.Tasks för .NET?
S: Aspose.Tasks för .NET erbjuder omfattande anpassningsalternativ för vykolumner, med minimala begränsningar. Komplexa anpassningar kan dock kräva avancerad kunskap om biblioteket.
### F: Kan jag söka hjälp om jag stöter på problem när jag använder Aspose.Tasks för .NET?
 A: Absolut! Du kan hitta omfattande support och resurser på Aspose.Tasks-forumet på[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15), där experter och communitymedlemmar är tillgängliga för att hjälpa dig att lösa alla frågor eller utmaningar du kan möta.
### F: Hur kan jag få en tillfällig licens för Aspose.Tasks för .NET?
 S: Du kan skaffa en tillfällig licens för Aspose.Tasks för .NET från[köpsidan](https://purchase.aspose.com/temporary-license/), så att du kan utvärdera bibliotekets fulla kapacitet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
