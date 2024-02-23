---
title: Hanterar undantag för ogiltig storlek för bitmapp i Aspose.Tasks
linktitle: Hanterar undantag för ogiltig storlek för bitmapp i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar BitmapInvalidSizeException i Aspose.Tasks för .NET när du sparar projekt som bilder. Omfattande handledning med steg-för-steg-vägledning.
type: docs
weight: 22
url: /sv/net/advanced-features/bitmap-invalid-size-exception/
---
## Introduktion

 den här handledningen kommer vi att fördjupa oss i att hantera`BitmapInvalidSizeException` när du arbetar med Aspose.Tasks för .NET. Aspose.Tasks är ett kraftfullt bibliotek som tillåter utvecklare att manipulera Microsoft Project-filer programmatiskt, vilket möjliggör uppgifter som att spara projekt som bilder. Men ibland, när vi försöker spara ett projekt som en bild, kan vi stöta på en`Invalid Size Exception` relaterad till bitmappen. Denna handledning syftar till att guida dig genom processen att fånga och hantera detta undantag effektivt.

## Förutsättningar

Innan du fortsätter med denna handledning, se till att du har följande förutsättningar på plats:
1. Grundläggande förståelse för programmeringsspråket C#.
2. Installerade Aspose.Tasks för .NET.
3. Kännedom om att arbeta med Microsoft Project-filer.

## Importera namnområden

Innan du börjar, se till att importera de nödvändiga namnrymden:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Steg 1: Initiera projekt och definiera vy

 Initiera först a`Project` objekt och definiera en vy, till exempel`GanttChartView`.

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

## Steg 2: Ange alternativ för bildspar

Ange sedan alternativen för att spara bilden, inklusive format och tidsskala.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

## Steg 3: Ställ in tidsskalaenhet och antal

Justera tidsskaleenheten och räkna enligt dina krav. I det här exemplet ställer vi in tidsskalan till minuter.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

## Steg 4: Spara projekt som bild

Försök att spara projektet som en bild med de angivna alternativen.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

## Steg 5: Fånga och hantera undantag

 Implementera undantagshantering för att fånga`BitmapInvalidSizeException` om det inträffar under bildsparprocessen.

```csharp
try
{
    // Försök att spara projektet som en bild
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Hantera undantaget
    Console.WriteLine(ex.Message);
}
```

## Slutsats

 Sammanfattningsvis, hantering av`BitmapInvalidSizeException` när du sparar projekt som bilder i Aspose.Tasks för .NET är avgörande för att säkerställa smidigt utförande av dina applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du effektivt fånga och hantera detta undantag och på så sätt förbättra robustheten i dina projektledningslösningar.

## FAQ's

### F1: Vad orsakar BitmapInvalidSizeException i Aspose.Tasks?

S1: Detta undantag inträffar när man försöker spara ett projekt som en bild med ogiltiga parametrar för bitmappsstorlek.

### F2: Kan jag anpassa tidsskalan när jag sparar ett projekt som en bild?

S2: Ja, du kan justera tidsskaleenheten och räkna enligt dina krav, som visas i handledningen.

### F3: Var kan jag hitta fler resurser för att arbeta med Aspose.Tasks för .NET?

S3: Du kan utforska dokumentationen och supportforumen som tillhandahålls av Aspose.Tasks för omfattande vägledning och hjälp.

### F4: Är Aspose.Tasks kompatibel med olika versioner av Microsoft Project-filer?

S4: Ja, Aspose.Tasks stöder olika versioner av Microsoft Project-filer, vilket möjliggör sömlös interoperabilitet.

### F5: Hur kan jag få en tillfällig licens för Aspose.Tasks?

S5: Du kan skaffa en tillfällig licens för utvärderingssyften via den angivna länken i artikeln.