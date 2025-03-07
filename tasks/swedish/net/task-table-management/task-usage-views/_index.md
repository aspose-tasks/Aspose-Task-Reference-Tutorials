---
title: Bemästra uppgiftsanvändningsvyer i Aspose.Tasks för .NET
linktitle: Konfigurera uppgiftsanvändningsvyer i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska Aspose.Tasks för .NET och lär dig hur du konfigurerar uppgiftsanvändningsvyer. Anpassa tidsskalainställningar och förbättra dina projektledningsbilder.
weight: 24
url: /sv/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra uppgiftsanvändningsvyer i Aspose.Tasks för .NET

## Introduktion
Inom projektledningsområdet är visualisering av uppgiftsanvändning avgörande för effektiv planering och utförande. Aspose.Tasks för .NET tillhandahåller en robust lösning för att rendera uppgiftsanvändningsvyer, så att du kan anpassa tidsskalainställningar och presentationsformat. I den här handledningen går vi igenom stegen för att konfigurera uppgiftsanvändningsvyer med Aspose.Tasks.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1.  Aspose.Tasks för .NET: Se till att du har Aspose.Tasks-biblioteket integrerat i ditt .NET-projekt. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
2. .NET-miljö: Ha en fungerande .NET-miljö inställd på din dator.
## Importera namnområden
I ditt .NET-projekt, importera de nödvändiga namnområdena för att komma åt Aspose.Tasks-funktioner. Lägg till följande rader i din kod:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Steg 1: Ställ in dokumentkatalogsökvägen
 Innan du arbetar med Aspose.Tasks-funktionerna, ställ in sökvägen till din dokumentkatalog. Byta ut`"Your Document Directory"` med den faktiska vägen.
```csharp
String DataDir = "Your Document Directory";
```
## Steg 2: Ladda projektet
 Initiera Aspose.Tasks`Project` objekt genom att ladda din projektfil (t.ex. TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Steg 3: Definiera Sparalternativ
 Skapa en`SaveOptions`objekt för att ange renderingsalternativen. Ställ in tidsskalan till "Dagar" och presentationsformatet till "TaskUsage".
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Steg 4: Spara med Days Timescale
Spara projektet med de fördefinierade tidsskalainställningarna för "Dagar".
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Steg 5: Spara med ThirdsOfMonths Timescale
Ändra tidsskalainställningarna till 'ThirdsOfMonths' och spara projektet.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Steg 6: Spara med månaders tidsskala
Ställ in tidsskalan till "Månader" och spara projektet med de uppdaterade inställningarna.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Slutsats
Att konfigurera uppgiftsanvändningsvyer med Aspose.Tasks för .NET är en enkel process. Genom att anpassa tidsskalainställningarna kan du skräddarsy visualiseringen av dina projektuppgifter efter dina specifika behov.
 Utforska gärna fler funktioner och funktioner i[dokumentation](https://reference.aspose.com/tasks/net/).
## Vanliga frågor
### Kan jag anpassa tidsskalan utöver fördefinierade inställningar?
Ja, du kan ställa in en anpassad tidsskala genom att ange intervall och enheter.
### Finns det andra presentationsformat tillgängliga?
Aspose.Tasks stöder olika presentationsformat, inklusive GanttChart, ResourceUsage och mer.
### Är Aspose.Tasks kompatibel med olika projektfilformat?
Ja, Aspose.Tasks stöder populära projektfilformat som MPP, XML och CSV.
### Kan jag tillämpa olika tidsskalainställningar för specifika uppgifter?
Absolut, du kan anpassa tidsskalainställningar för individuella uppgifter inom ditt projekt.
### Hur kan jag få stöd eller söka hjälp för Aspose.Tasks?
 Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och vägledning.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
