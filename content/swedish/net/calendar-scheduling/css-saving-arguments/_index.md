---
title: CSS sparar argument i Aspose.Tasks
linktitle: CSS sparar argument i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du sparar CSS-argument i Aspose.Tasks för .NET för att anpassa HTML-utdata. Förbättra presentationen med skräddarsydda CSS-inställningar.
type: docs
weight: 20
url: /sv/net/calendar-scheduling/css-saving-arguments/
---
## Introduktion

den här handledningen kommer vi att fördjupa oss i processen att spara CSS-argument med Aspose.Tasks för .NET. Cascading Style Sheets (CSS) är avgörande för att definiera presentationen av HTML-element. Aspose.Tasks tillåter oss att manipulera och spara dessa CSS-attribut effektivt.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1.  Installation: Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner den från[hemsida](https://releases.aspose.com/tasks/net/).

2. Grundläggande kunskaper: Bekantskap med utvecklingsmiljön C# och .NET rekommenderas.

## Importera namnområden

För att komma igång, importera nödvändiga namnområden:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Steg 1: Definiera CSS Spara återuppringningar

För det första definierar vi CSS-sparande callback-metoder för att hantera sparandet av CSS-filer:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implementera din CSS-sparlogik här
    }
}
```

## Steg 2: Implementera teckensnitt och bildsparande återuppringningar

Implementera sedan återuppringningsmetoderna för teckensnitt och bildsparande på liknande sätt:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implementera logiken för att spara teckensnitt här
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implementera din bildsparlogik här
}
```

## Steg 3: Konfigurera sparalternativ

Konfigurera nu HTML-sparalternativen för att använda de implementerade återuppringningarna:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Konfigurera HTML-sparalternativ
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Steg 4: Spara projekt med anpassad CSS

Slutligen, spara ditt projekt med de anpassade CSS-inställningarna:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Slutsats

I den här handledningen har vi utforskat hur man sparar CSS-argument med Aspose.Tasks för .NET. Genom att definiera CSS-sparande callbacks och konfigurera HTML-sparalternativ kan vi effektivt manipulera CSS-attribut enligt våra krav.

## Vanliga frågor

### F1: Vad är Aspose.Tasks för .NET?

S1: Aspose.Tasks för .NET är ett kraftfullt .NET API som gör det möjligt för utvecklare att arbeta med Microsoft Project-filer programmatiskt.

### F2: Kan jag anpassa CSS-attribut när jag sparar HTML-filer med Aspose.Tasks?

S2: Ja, du kan definiera CSS-sparande återuppringningar för att anpassa CSS-attribut efter dina behov.

### F3: Är Aspose.Tasks för .NET kompatibelt med alla versioner av Microsoft Project-filer?

S3: Aspose.Tasks för .NET stöder olika versioner av Microsoft Project-filer, vilket säkerställer kompatibilitet mellan olika miljöer.

### F4: Var kan jag hitta omfattande dokumentation för Aspose.Tasks för .NET?

A4: Du kan hänvisa till[dokumentation](https://reference.aspose.com/tasks/net/) för detaljerad information och exempel.

### F5: Erbjuder Aspose.Tasks för .NET stöd för utvecklare?

 S5: Ja, du kan få stöd från Aspose.Tasks-communityt genom[forum](https://forum.aspose.com/c/tasks/15).