---
title: Bemästra Gantt-diagramvyer i Aspose.Tasks
linktitle: Gantt-diagramvyer i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du anpassar Gantt-diagramvyer i Microsoft Project-filer med Aspose.Tasks för .NET. Steg-för-steg-guide för effektiv projektledning.
weight: 22
url: /sv/net/tasks-project-management/gantt-chart-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra Gantt-diagramvyer i Aspose.Tasks

## Introduktion
Gantt-diagram är kraftfulla verktyg som används i projektledning för att visualisera uppgifter, tidslinjer och beroenden. Aspose.Tasks för .NET ger robusta funktioner för att arbeta med Gantt-diagramvyer i Microsoft Project-filer. I den här handledningen kommer vi att utforska hur man använder Aspose.Tasks för att manipulera Gantt-diagramvyer, anpassa deras utseende och spara dem som PDF-filer.
## Förutsättningar
Innan du fortsätter, se till att du har följande förutsättningar:
### 1. Installation av Aspose.Tasks för .NET
 Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/tasks/net/) och följ installationsinstruktionerna i dokumentationen[här](https://reference.aspose.com/tasks/net/).
### 2. Microsoft Project File
Förbered en Microsoft Project-fil (`Project2.mpp`) som du kommer att använda för att arbeta med Gantt-diagramvyer.
### 3. Grundläggande kunskaper i C# och .NET Framework
Den här handledningen förutsätter att du har en grundläggande förståelse för programmeringsspråket C# och .NET-ramverket.
## Importera namnområden
Innan du börjar arbeta med Gantt-diagramvyer i Aspose.Tasks måste du importera de nödvändiga namnrymden till din C#-kod. Så här kan du göra det:

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

Låt oss dela upp den medföljande exempelkoden i flera steg och förklara varje steg i detalj:
## Steg 1: Ladda projektfilen
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Detta steg innebär att ladda Microsoft Project-filen (`Project2.mpp` ) till en instans av`Project` klass.
## Steg 2: Ställ in statusdatum
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Här sätter vi statusdatumet för projektet till dess startdatum.
## Steg 3: Öppna Gantt-diagramvy
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Vi kommer åt Gantt-diagramvyn från projektet. Aspose.Tasks tillåter åtkomst till vyer som Gantt-diagram, nätverksdiagram och uppgiftsanvändning.
## Steg 4: Anpassa Gantt-diagramvyn
Låt oss nu anpassa olika aspekter av Gantt-diagramvyn:
### Ställ in stavavrundning
```csharp
view.BarRounding = false;
```
Detta ställer in om staplarna på Gantt-diagrammet ska avrundas till närmaste dag.
### Ställ in stapelstorlek
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Detta bestämmer höjden på Gantt-staplarna i diagrammet.
### Dölj rollup-staplar
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Anger om samlade fält ska döljas när sammanfattningsuppgifter utökas.
### Ställ in färg för icke-arbetstid
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Definierar färgen för icke-arbetstid på Gantt-diagrammet.
### Roll Up Gantt Bars
```csharp
view.RollUpGanttBars = true;
```
Anger om staplar på Gantt-diagrammet måste rullas upp.
### Visa stapeldelningar
```csharp
view.ShowBarSplits = true;
```
Bestämmer om uppgiftsdelningar på Gantt-diagrammet måste visas.
### Visa ritningar
```csharp
view.ShowDrawings = true;
```
Anger om ritningar på Gantt-diagrammet måste visas.
### Tidsskala Storlek Procent
```csharp
view.TimescaleSizePercentage = 10;
```
Ställer in en procentsats för att justera avståndet mellan enheterna på tidsskalenivån.
## Steg 5: Spara Gantt-diagramvy som PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Slutligen sparar vi den anpassade Gantt-diagramvyn som en PDF-fil.
## Slutsats
I den här handledningen har vi lärt oss hur man arbetar med Gantt-diagramvyer i Aspose.Tasks för .NET. Genom att följa de angivna stegen kan du effektivt manipulera och anpassa Gantt-diagram enligt dina projektkrav.
## FAQ's
### F: Kan jag anpassa utseendet på Gantt-diagramstaplar ytterligare?
S: Ja, Aspose.Tasks erbjuder omfattande alternativ för att anpassa utseendet på Gantt-diagramstaplar, inklusive färger, former och storlekar.
### F: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project-filer?
S: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project-filer, inklusive MPP-, MPT- och XML-format.
### F: Kan jag exportera Gantt-diagramvyer till andra format än PDF?
S: Absolut, Aspose.Tasks stöder export av Gantt-diagramvyer till flera format, inklusive PNG, JPEG och XPS.
### F: Erbjuder Aspose.Tasks stöd för komplexa projektschemaläggningsalgoritmer?
S: Ja, Aspose.Tasks tillhandahåller avancerade schemaläggningsalgoritmer för att effektivt hantera komplexa projektscheman.
### F: Finns det ett communityforum där jag kan söka hjälp eller dela mina erfarenheter av Aspose.Tasks?
 A: Ja, du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) att engagera sig med andra användare, ställa frågor och hitta lösningar på dina frågor.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
