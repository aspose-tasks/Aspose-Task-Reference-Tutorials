---
title: Konfigurera visningsalternativ för MS Project i Aspose.Tasks
linktitle: Konfigurera projektvisningsalternativ i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konfigurerar MS Projects visningsalternativ programmatiskt med Aspose.Tasks för .NET. Anpassa ditt projekts utseende utan ansträngning.
weight: 17
url: /sv/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurera visningsalternativ för MS Project i Aspose.Tasks

## Introduktion
Microsoft Project erbjuder en uppsjö av visningsalternativ för att anpassa utseendet på ditt projekt. Aspose.Tasks för .NET tillhandahåller ett robust ramverk för att manipulera dessa alternativ programmatiskt. I den här handledningen kommer vi att utforska hur du konfigurerar MS Project-visningsalternativ med Aspose.Tasks.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande:
1.  Aspose.Tasks för .NET: Ladda ner och installera biblioteket från[här](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Ha en giltig MS Project-fil (.mpp) redo att använda visningsalternativen.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# krävs.

## Importera namnområden
Se först till att importera de nödvändiga namnrymden till din C#-kod:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Steg 1: Ladda projektfilen
 Ladda MS Project-filen med hjälp av`Project` klass tillhandahållen av Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Steg 2: Konfigurera visningsalternativ
Låt oss nu konfigurera olika visningsalternativ som är tillgängliga i MS Project:
### Inaktivera varningar för uppgiftsschema
Så här inaktiverar du varningar för schemaläggningskonflikter med manuellt schemalagda uppgifter (tillgängligt för Project 2010 och senare):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Lägg till utrymme före etikett
Ställ in för att lägga till ett mellanslag före nummervärdet och tidsförkortningen:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Konfigurera etikettvisning för tidsenheter
Anpassa hur olika tidsenheter visas:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Visa projektsammanfattningsuppgift
Visa sammanfattande information om hela projektet på en enda rad:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Aktivera uppgiftsschemaförslag
Tillåt visning av förslag för schemaläggning av konflikter med manuellt schemalagda uppgifter:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Understryka hyperlänkar
Ställ in för att understryka hyperlänkar inom projektet:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Steg 3: Spara projektet
Slutligen, spara projektet med de tillämpade visningsalternativen:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Slutsats
I den här handledningen lärde vi oss hur man konfigurerar MS Project-visningsalternativ med Aspose.Tasks för .NET. Med dessa funktioner kan du effektivt anpassa utseendet på dina projektfiler programmatiskt.
## FAQ's
### F: Kan jag tillämpa dessa visningsalternativ endast på specifika uppgifter?
S: Ja, du kan selektivt tillämpa visningsalternativ på enskilda uppgifter med Aspose.Tasks API.
### F: Påverkar dessa visningsalternativ de underliggande projektdata?
S: Nej, dessa alternativ ändrar bara den visuella representationen av projektet och ändrar inte underliggande data.
### F: Är dessa visningsalternativ kompatibla med alla versioner av Microsoft Project?
S: Nej, vissa alternativ kan vara specifika för vissa versioner av MS Project. Se dokumentationen för kompatibilitetsinformation.
### F: Kan jag återställa visningsalternativen till standardinställningarna?
S: Ja, du kan återställa visningsalternativen till deras standardvärden med Aspose.Tasks API.
### F: Finns det några begränsningar för att anpassa visningsalternativ programmatiskt?
S: Även om Aspose.Tasks tillhandahåller omfattande anpassningsmöjligheter, kanske vissa visningsalternativ inte är tillgängliga programmatiskt på grund av begränsningar i MS Project-filformatet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
