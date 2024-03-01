---
title: Konvertera MSP till XPS-alternativ med Aspose.Tasks
linktitle: XPS-alternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konverterar Microsoft Project-filer till XPS-format med Aspose.Tasks för .NET. Enkel integration, robust funktionalitet.
type: docs
weight: 21
url: /sv/net/saving-options/xps-options/
---
## Introduktion
Microsoft Project (MSP) är ett mycket använt verktyg för projektledning, vilket underlättar planering, spårning och rapportering av projektaktiviteter. Aspose.Tasks för .NET erbjuder robusta funktioner för att manipulera MSP-filer programmatiskt, vilket ger utvecklare möjlighet att automatisera olika uppgifter relaterade till projektledning. I den här handledningen kommer vi att fördjupa oss i att utnyttja Aspose.Tasks för .NET för att generera XPS-filer från MSP-dokument, och utforska nödvändiga steg och överväganden.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1.  Installation av Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[hemsida](https://releases.aspose.com/tasks/net/).
2. Microsoft Project Document: Förbered Microsoft Project-dokumentet (.mpp) som du tänker konvertera till XPS-format.

## Importera namnområden
För att kickstarta processen, importera de nödvändiga namnrymden i ditt .NET-projekt:
```csharp

using Aspose.Tasks.Saving;
```

## Steg 1: Ställ in dokumentkatalogsökvägen
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med sökvägen där ditt MSP-dokument finns.
## Steg 2: Ladda MSP-dokumentet
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
 Här initierar vi en ny`Project` objekt genom att skicka sökvägen till MSP-dokumentet.
## Steg 3: Skapa XPS-sparalternativ
```csharp
// Skapa XPS-sparalternativ och justera parametrarna
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
 I det här steget instansierar vi`XpsOptions`och konfigurera parametrar. Miljö`RenderMetafileAsBitmap` till`true` säkerställer korrekt rendering av metafiler.
## Steg 4: Spara dokumentet som XPS
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
 Slutligen kallar vi`Save` metod på`Project` objekt, som anger utdatafilens sökväg och den tidigare konfigurerade`XpsOptions`.

## Slutsats
Sammanfattningsvis förenklar Aspose.Tasks för .NET processen att konvertera Microsoft Project-dokument till XPS-format programmatiskt. Genom att följa stegen som beskrivs i denna handledning kan utvecklare sömlöst integrera den här funktionen i sina .NET-applikationer, vilket med lätthet förbättrar arbetsflöden för projektledning.
## FAQ's
### F: Kan Aspose.Tasks för .NET hantera komplexa MSP-filer?
S: Ja, Aspose.Tasks för .NET kan effektivt hantera komplexa Microsoft Project-filer, vilket säkerställer korrekt konvertering till olika format.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan få en gratis testversion från[här](https://releases.aspose.com/).
### F: Stöder Aspose.Tasks för .NET andra utdataformat förutom XPS?
S: Ja, Aspose.Tasks för .NET stöder olika utdataformat som bland annat PDF, HTML, PNG och JPEG.
### F: Kan jag anpassa renderingsalternativen för utdatafilen?
S: Absolut, Aspose.Tasks för .NET erbjuder omfattande alternativ för att anpassa renderingsparametrar enligt dina krav.
### F: Var kan jag hitta ytterligare support eller hjälp för Aspose.Tasks för .NET?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för eventuella frågor eller hjälp angående Aspose.Tasks för .NET.