---
title: Anpassa MS Project Page View Settings i Aspose.Tasks
linktitle: Konfigurera sidvisningsinställningar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du konfigurerar sidvisningsinställningar i Aspose.Tasks för .NET för att skräddarsy utskriftsformatet för dina Microsoft Project-dokument.
type: docs
weight: 21
url: /sv/net/outline-code-page-settings/page-view-settings/
---
## Introduktion
Microsoft Project är ett kraftfullt verktyg för projektledning, men ibland måste du anpassa hur ditt projekt visas och skrivs ut. Med Aspose.Tasks för .NET kan du enkelt konfigurera sidvisningsinställningarna för att uppfylla dina specifika krav. I den här handledningen guidar vi dig genom processen steg för steg.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Aspose.Tasks for .NET: Se till att du har laddat ner och installerat Aspose.Tasks for .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Ha en Microsoft Project-fil redo som du vill konfigurera sidvisningsinställningarna för.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks i ditt .NET-projekt.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Steg 1: Ladda projektfilen
 Börja med att ladda din Microsoft Project-fil i en instans av`Project` klass.
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Steg 2: Ställ in antal första kolumner
Ange antalet första kolumner som ska skrivas ut på alla sidor.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Steg 3: Skriv ut anteckningar
Välj om du vill skriva ut anteckningar tillsammans med projektet.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Steg 4: Anpassa tidsskala till slutet av sidan
Bestäm om du vill anpassa tidsskalan till slutet av en sida vid utskrift.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Steg 5: Skriv ut alla arkkolumner
Ange om alla arkkolumner i en vy ska skrivas ut.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Steg 6: Skriv ut tomma sidor
Välj om du vill skriva ut tomma sidor i en vy.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Steg 7: Skriv ut första kolumner på alla sidor
Ställ in om ett visst antal första kolumner ska skrivas ut på alla sidor.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Steg 8: Spara projektet med konfigurerade inställningar
Slutligen sparar du projektet med de konfigurerade sidvisningsinställningarna, och anger utdataformatet, till exempel PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Slutsats
Att konfigurera sidvisningsinställningar för Microsoft Project i Aspose.Tasks för .NET är enkelt och låter dig skräddarsy utskriftsformatet efter dina exakta behov. Genom att följa stegen som beskrivs i denna handledning kan du säkerställa att dina projektdokument presenteras exakt som krävs.
## FAQ's
### F: Kan jag konfigurera sidvisningsinställningar för andra filformat än PDF?
S: Ja, Aspose.Tasks stöder olika filformat för att spara projekt, inklusive XLSX, MPP och HTML.
### F: Finns det några begränsningar för antalet kolumner jag kan skriva ut?
S: Aspose.Tasks låter dig anpassa antalet kolumner som ska skrivas ut baserat på dina krav.
### F: Kan jag använda olika sidvisningsinställningar för olika projekt?
S: Ja, du kan justera sidvisningsinställningarna oberoende för varje projektfil du arbetar med.
### F: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?
S: Aspose.Tasks erbjuder kompatibilitet med Microsoft Project 2003 och senare versioner.
### F: Var kan jag hitta ytterligare hjälp eller support för Aspose.Tasks?
 A: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för eventuella frågor eller problem som du stöter på under användning.