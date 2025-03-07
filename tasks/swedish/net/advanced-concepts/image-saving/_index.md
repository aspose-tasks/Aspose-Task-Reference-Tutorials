---
title: Hantera bildsparande i Aspose.Tasks
linktitle: Hantera bildsparande i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar bildsparande i Aspose.Tasks för .NET med hjälp av steg-för-steg-riktlinjer. Integrera sömlöst bildsparfunktion i dina .NET-applikationer.
weight: 10
url: /sv/net/advanced-concepts/image-saving/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera bildsparande i Aspose.Tasks

## Introduktion

I den här handledningen kommer vi att fördjupa oss i processen att hantera bildsparande i Aspose.Tasks för .NET. Aspose.Tasks är ett kraftfullt API som gör det möjligt för utvecklare att manipulera Microsoft Project-filer programmatiskt. En vanlig uppgift när man arbetar med projektfiler är behovet av att spara bilder, som kan innehålla diagram, grafer eller andra visuella element. Vi kommer att bryta ner processen steg för steg, för att säkerställa klarhet och förståelse hela tiden.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#: Bekanta dig med grunderna i programmeringsspråket i C#.

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden till vårt projekt:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Skapa ett projektobjekt

Börja med att skapa ett projektobjekt från din Microsoft Project-fil:

```csharp
var project = new Project("Project1.mpp");
```

## Steg 2: Definiera sparalternativ

Definiera sparalternativen för ditt projekt, ange sidorna och andra inställningar:

```csharp
var options = GetSaveOptions(1);
```

## Steg 3: Spara projektet som HTML

Spara projektet som HTML med de angivna alternativen:

```csharp
project.Save("document_out.html", options);
```

## Steg 4: Implementera bildsparande återuppringning

Implementera ImageSavingCallback-gränssnittet för att hantera bildsparande:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Bildsparande logik går här
    }
}
```

## Steg 5: Spara bilder i specificerad katalog

Inom ImageSaving-metoden, ange logiken för att spara bilder i önskad katalog:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Spara kapslade resurser
}
else
{
    // Spara regelbundna resurser
}
```

## Steg 6: Ange Sparningsalternativ

Ange sparalternativ, inklusive återuppringningar för CSS, teckensnitt och bilder:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Ange sparalternativ här
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Slutsats

Sammanfattningsvis innebär hantering av bildsparande i Aspose.Tasks för .NET att definiera sparalternativ och implementera callbacks för att hantera sparprocessen effektivt. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera bildsparfunktioner i dina .NET-applikationer.

## FAQ's

### F1: Kan jag använda Aspose.Tasks för att manipulera projektfiler i andra format än HTML?

S1: Ja, Aspose.Tasks stöder olika format som PDF, XLSX och MPP.

### F2: Ger Aspose.Tasks stöd för integration av molnlagring?

S2: Ja, Aspose.Tasks erbjuder API:er för att arbeta med populära molnlagringstjänster som Amazon S3 och Google Drive.

### F3: Är Aspose.Tasks kompatibel med .NET Core?

S3: Ja, Aspose.Tasks är kompatibelt med .NET Core, vilket gör att du kan utveckla plattformsoberoende applikationer.

### F4: Kan jag anpassa utseendet på sparade bilder?

S4: Ja, du kan anpassa utseendet på sparade bilder genom att ändra logiken för att spara bilder inom återuppringningsmetoderna.

### F5: Erbjuder Aspose.Tasks testversioner för utvärderingssyften?

 S5: Ja, du kan få en gratis provversion av Aspose.Tasks från[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
