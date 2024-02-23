---
title: Anpassad tilldelning Visa kolumn i Aspose.Tasks
linktitle: Anpassad tilldelning Visa kolumn i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du lägger till anpassade uppdragsvykolumner i Aspose.Tasks för .NET för att förbättra projekthanteringskapaciteten.
type: docs
weight: 16
url: /sv/net/advanced-features/assignment-view-column/
---
## Introduktion

den här handledningen kommer vi att utforska hur du lägger till anpassade kolumner för uppdragsvyer med Aspose.Tasks för .NET. Anpassade kolumner ger flexibilitet och låter dig visa ytterligare information som är relevant för dina projektledningsbehov.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Grundläggande kunskaper i programmeringsspråket C#.
2.  Aspose.Tasks för .NET-biblioteket installerat. Om inte kan du ladda ner den[här](https://releases.aspose.com/tasks/net/).
3. En integrerad utvecklingsmiljö (IDE) som Visual Studio.

## Importera namnområden

Låt oss först importera de nödvändiga namnområdena för att komma åt de klasser och metoder som krävs för att skapa anpassade tilldelningsvykolumner:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Steg 1: Ladda projektet

 För att börja, ladda din projektfil med hjälp av`Project` klass:

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Steg 2: Skapa sparalternativ för kalkylblad

 Skapa sedan en instans av`Spreadsheet2003SaveOptions` vilket gör att vi kan anpassa uppgiftsvykolumnerna:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Steg 3: Definiera anpassad kolumn

 Definiera nu din anpassade kolumn genom att skapa en instans av`AssignmentViewColumn`Den här klassen kräver kolumnnamn, bredd och en delegatfunktion för att konvertera tilldelningsdata till kolumntext:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Steg 4: Lägg till anpassad kolumn till alternativ

Lägg till den anpassade kolumnen i kolumnsamlingen för uppdragsvyn med sparalternativ:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Steg 5: Iterera genom uppdrag

Iterera genom varje resurstilldelning i projektet och visa den anpassade kolumntexten:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Steg 6: Spara projektet med anpassade kolumner

Slutligen sparar du projektet med kolumnerna för anpassad uppdragsvy:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Slutsats

I den här handledningen lärde vi oss hur man lägger till anpassade uppdragsvykolumner med Aspose.Tasks för .NET. Anpassade kolumner erbjuder flexibilitet när det gäller att visa ytterligare information skräddarsydd för dina projektkrav, vilket förbättrar projektledningskapaciteten.

## FAQ's

### F1: Kan jag lägga till flera anpassade kolumner i uppdragsvyn?

 S1: Ja, du kan lägga till flera anpassade kolumner genom att skapa ytterligare instanser av`AssignmentViewColumn` och lägga till dem i`Columns` samling.

### F2: Finns det fördefinierade omvandlare tillgängliga för vanliga tilldelningsfält?

S2: Ja, Aspose.Tasks tillhandahåller fördefinierade omvandlare för vanliga tilldelningsfält, vilket gör det lättare att extrahera data för anpassade kolumner.

### F3: Kan jag anpassa utseendet på anpassade kolumner, som att formatera text eller använda stilar?

S3: Ja, du kan anpassa utseendet på anpassade kolumner genom att ändra egenskaper som bredd, teckensnitt och justering.

### F4: Är det möjligt att ta bort standardkolumner från uppdragsvyn?

 S4: Ja, du kan ta bort standardkolumner genom att utesluta dem från`Columns` samling eller ställ in deras bredd till noll.

### F5: Stöder Aspose.Tasks export av projekt till andra format än kalkylblad med anpassade kolumner?

S5: Ja, Aspose.Tasks stöder export av projekt till olika format som PDF, HTML och XML, vilket möjliggör mångsidiga projektrapporteringsalternativ.