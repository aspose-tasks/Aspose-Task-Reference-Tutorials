---
title: Styling Bar i Aspose.Tasks
linktitle: Styling Bar i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du stilar staplar i Aspose.Tasks för .NET för att förbättra projektvisualiseringen.
weight: 19
url: /sv/net/advanced-features/styling-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Styling Bar i Aspose.Tasks

## Introduktion

Styling av barer i Aspose.Tasks är en viktig aspekt av att skapa visuellt tilltalande projektplaner. Med flexibiliteten som erbjuds av Aspose.Tasks API kan utvecklare anpassa olika aspekter av staplar, såsom färg, form och textstil, för att förbättra projektvisualiseringen. I den här handledningen kommer vi att undersöka hur man stilar staplar med Aspose.Tasks för .NET, och delar upp varje exempel i hanterbara steg.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1.  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Skapa en utvecklingsmiljö med stöd för .NET framework.
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden

Låt oss först importera de nödvändiga namnområdena för att komma åt Aspose.Tasks-klasser och metoder:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Steg 1: Ladda projektet

Börja med att ladda projektfilen med Aspose.Tasks API:

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Steg 2: Konfigurera sparalternativ

Definiera sparalternativen och ange de stapelstilar som ska tillämpas:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Steg 3: Definiera barstil

Skapa en ny barstil och anpassa dess egenskaper:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Ställ in barobjektstyp
style.BarColor = Color.Green; // Ställ in stapelfärg
style.BarShape = BarShape.HalfHeight; // Ställ in stångform
style.StartShape = Shape.LeftBracket; // Ställ in formen i början av stapeln
style.StartShapeColor = Color.Aqua; // Ställ in färg på startformen
style.EndShape = Shape.RightBracket; // Sätt formen i slutet av stången
style.EndShapeColor = Color.Aquamarine; // Ställ in färg på slutformen
style.TextStyle = new TextStyle(); // Ställ in textstil
style.TextStyle.BackgroundColor = Color.Black; // Ställ in bakgrundsfärg för text
```

## Steg 4: Anpassa Text Converter

Alternativt kan du anpassa textkonverteraren för att ändra textåtergivningen:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Steg 5: Lägg till barstil till alternativ

Lägg till den konfigurerade stapelstilen till sparalternativen:

```csharp
options.BarStyles.Add(style);
```

## Steg 6: Spara projektet

Slutligen, spara projektet med de tillämpade stapelstilarna:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Slutsats

Anpassning av barstilar i Aspose.Tasks för .NET ger utvecklare möjligheten att skapa visuellt tilltalande projektplaner. Genom att följa stegen som beskrivs i den här handledningen kan du effektivt utforma staplar för att möta specifika projektvisualiseringskrav.

## FAQ's

### F1: Kan jag tillämpa flera stapelstilar på ett enda projekt?

S1: Ja, du kan definiera och tillämpa flera stapelstilar på olika typer av uppgifter inom samma projekt.
   
### F2: Är det möjligt att dynamiskt ändra stapelstilar under körning?

S2: Ja, du kan dynamiskt ändra stapelstilar baserat på vissa villkor eller användarpreferenser i din applikation.
   
### F3: Stöder Aspose.Tasks export av projekt med formaterade staplar till olika filformat?

S3: Ja, Aspose.Tasks stöder export av projekt med formaterade staplar till olika format som PDF, XLSX och HTML.
   
### F4: Finns det fördefinierade barstilar tillgängliga i Aspose.Tasks?

S4: Medan Aspose.Tasks tillhandahåller standardfältstilar, kan utvecklare också skapa anpassade fältstilar skräddarsydda för deras projektkrav.
   
### F5: Kan jag hämta och ändra befintliga stapelstilar inom ett projekt med hjälp av API:et?

S5: Ja, du kan hämta och ändra befintliga stapelstilar programmatiskt med Aspose.Tasks för .NET API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
