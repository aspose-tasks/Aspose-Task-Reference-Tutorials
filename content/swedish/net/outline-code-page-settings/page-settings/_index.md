---
title: Konfigurera MS Project Page Settings med Aspose.Tasks
linktitle: Konfigurera sidinställningar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konfigurerar MS Project-sidans inställningar med Aspose.Tasks för .NET. Anpassa orientering, storlek och mer med enkla steg.
type: docs
weight: 20
url: /sv/net/outline-code-page-settings/page-settings/
---
## Introduktion
I den här handledningen går vi igenom processen att konfigurera Microsoft Project-sidans inställningar med Aspose.Tasks för .NET. Aspose.Tasks är ett kraftfullt API som tillåter utvecklare att manipulera Microsoft Project-filer programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1.  Aspose.Tasks för .NET: Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Ha en utvecklingsmiljö inrättad med Visual Studio eller någon annan föredragen IDE för .NET-utveckling.

## Importera namnområden
För att komma igång måste du importera de nödvändiga namnrymden i ditt projekt. Dessa namnområden ger åtkomst till Aspose.Tasks-klasserna och metoderna som krävs för att manipulera MS Project-filer.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Steg 1: Ladda projektfilen
Först måste du ladda MS Project-filen som du vill konfigurera sidinställningarna för.
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Steg 2: Öppna sidinställningar
Därefter kommer du åt sidinställningarna för projektfilen.
```csharp
// Hämta inställningarna
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Steg 3: Konfigurera sidinställningar
Låt oss nu konfigurera olika egenskaper för sidinställningarna enligt dina krav.
```csharp
// Ställ in sidriktningen på stående
settings.IsPortrait = true;
// Ställ in antalet sidor i bredd som ska skrivas ut
settings.PagesInWidth = 5;
// Ställ in antalet sidor i höjd som ska skrivas ut
settings.PagesInHeight = 7;
// Ställ in procent av normal storlek att justera utskriften till
settings.PercentOfNormalSize = 200;
// Ställ in pappersstorlek
settings.PaperSize = PrinterPaperSize.PaperB4;
// Ställ in första sidnummer för utskrift
settings.FirstPageNumber = 3;
```
## Steg 4: Spara projektfilen
Spara slutligen projektfilen med de uppdaterade sidinställningarna.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Slutsats
I den här handledningen har vi lärt oss hur man konfigurerar Microsoft Project-sidans inställningar med Aspose.Tasks för .NET. Genom att följa dessa steg kan du enkelt anpassa sidans orientering, storlek och andra utskriftsalternativ enligt dina krav.

## FAQ's
### F: Kan jag konfigurera sidinställningar för flera MS Project-filer samtidigt?
S: Ja, du kan gå igenom flera projektfiler och tillämpa samma sidinställningar på var och en.
### F: Är det möjligt att återställa sidinställningarna till standardinställningarna?
S: Absolut, du kan helt enkelt utelämna konfigurationsstegen eller återställa inställningarna till deras standardvärden.
### F: Finns det några begränsningar för de pappersstorlekar som stöds?
S: Aspose.Tasks stöder ett brett utbud av pappersstorlekar, inklusive standard och anpassade storlekar.
### F: Kan jag automatisera konfigurationsprocessen för sidinställningar?
S: Visst kan du integrera den här funktionen i din applikations arbetsflöde för att automatisera konfigurationen av sidinställningar.
### F: Erbjuder Aspose.Tasks stöd för olika filformat förutom .mpp?
S: Ja, Aspose.Tasks stöder olika filformat som bland annat XML, MPT och HTML.