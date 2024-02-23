---
title: Image Spara MS Project Alternativ för Aspose.Tasks
linktitle: Image Spara alternativ för Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du sparar MS Project-alternativ som bilder med Aspose.Tasks för .NET. Följ vår steg-för-steg-guide för sömlös integration.
type: docs
weight: 11
url: /sv/net/saving-options/image-save-options/
---

## Introduktion
en värld av mjukvaruutveckling är hantering av projektuppgifter effektivt avgörande för framgångsrik projektledning. Aspose.Tasks för .NET erbjuder en kraftfull lösning för utvecklare som arbetar med Microsoft Project-filer, som låter dem manipulera, konvertera och hantera projektuppgifter sömlöst i sina .NET-applikationer.
## Förutsättningar
Innan du börjar använda Aspose.Tasks för .NET för att spara MS Project-alternativ som bilder, se till att du har följande förutsättningar:
### 1. Installera Aspose.Tasks för .NET
 För att börja måste du ha Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Du kan ladda ner biblioteket från[hemsida](https://releases.aspose.com/tasks/net/) och följ installationsanvisningarna.
### 2. Skaffa en licens (valfritt)
 Medan Aspose.Tasks för .NET kan användas utan licens i utvärderingsläge, rekommenderas att skaffa en licens för full funktionalitet och för att ta bort utvärderingsbegränsningar. Du kan skaffa en licens från[köpsidan](https://purchase.aspose.com/buy) eller välj en[tillfällig licens](https://purchase.aspose.com/temporary-license/) för teständamål.
### 3. Grundläggande kunskaper i C# och .NET-utveckling
En grundläggande förståelse för programmeringsspråket C# och .NET-ramverket är nödvändigt för att följa exemplen och effektivt integrera Aspose.Tasks-funktioner i dina applikationer.
## Importera namnområden
Innan vi börjar spara MS Project-alternativ som bilder med Aspose.Tasks för .NET, låt oss se till att vi importerar de nödvändiga namnrymden till vårt C#-projekt:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Ställ in dokumentkatalogsökväg
Se till att du har en angiven katalog för dina dokument och ställ in sökvägen därefter:
```csharp
String DataDir = "Your Document Directory";
```
## Steg 2: Ladda MS Project File
 Initiera en ny`Project` objekt genom att ladda MS Project-filen:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Steg 3: Definiera bildsparalternativ
 Skapa en instans av`ImageSaveOptions` och ange önskade inställningar:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Steg 4: Ange sidor som ska sparas
Om det behövs, ange vilka sidor som ska sparas. I det här exemplet lägger vi till sida 2:
```csharp
options.Pages.Add(2);
```
## Steg 5: Spara bilden
Slutligen, spara de markerade sidorna som en bild med de angivna alternativen:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Slutsats
Aspose.Tasks för .NET förenklar processen att arbeta med MS Project-filer, vilket gör att utvecklare enkelt kan manipulera projektuppgifter. Genom att följa stegen som beskrivs i denna handledning kan du effektivt spara MS Project-alternativ som bilder i dina .NET-applikationer.
## FAQ's
### F1: Kan jag använda Aspose.Tasks för .NET utan licens?
S: Ja, du kan använda Aspose.Tasks för .NET utan licens i utvärderingsläge. Det rekommenderas dock att skaffa en licens för full funktionalitet och att ta bort utvärderingsbegränsningar.
### F2: Hur kan jag få en tillfällig licens för testning?
 S: Du kan få en tillfällig licens för teständamål från[sida för tillfällig licens](https://purchase.aspose.com/temporary-license/).
### F3: Är Aspose.Tasks för .NET kompatibelt med andra .NET-ramverk?
S: Ja, Aspose.Tasks för .NET är kompatibelt med olika .NET-ramverk, inklusive .NET Core och .NET Standard.
### F4: Kan jag anpassa bildsparalternativen ytterligare?
S: Ja, du kan anpassa bildsparalternativen enligt dina specifika krav, som att justera sidstorlek, upplösning eller utdataformat.
### F5: Var kan jag hitta support för Aspose.Tasks för .NET?
 S: Du kan hitta support och hjälp för Aspose.Tasks för .NET på[forum](https://forum.aspose.com/c/tasks/15).