---
title: Hantera projektöversiktskoder i Aspose.Tasks för .NET
linktitle: Hantera dispositionskoder i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig att hantera MS Project-konturkoder med Aspose.Tasks för .NET. Förenkla projektorganisationen utan ansträngning.
weight: 10
url: /sv/net/outline-code-page-settings/outline-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera projektöversiktskoder i Aspose.Tasks för .NET

## Introduktion
I den här handledningen kommer vi att utforska hur man hanterar Microsoft Project-konturkoder med Aspose.Tasks för .NET. Dispositionskoder är anpassade fält i Microsoft Project som tillåter användare att kategorisera och organisera uppgifter enligt specifika kriterier. Aspose.Tasks förenklar processen att läsa och manipulera dessa konturkoder programmatiskt.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1.  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[hemsida](https://releases.aspose.com/tasks/net/).
2. Utvecklingsmiljö: Sätt upp en lämplig utvecklingsmiljö för .NET-programmering, som Visual Studio.
3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt för att förstå kodexemplen.

## Importera namnområden
För att komma igång måste du importera de nödvändiga namnrymden till ditt C#-projekt. Detta låter dig komma åt klasserna och metoderna som tillhandahålls av Aspose.Tasks-biblioteket.
1. Öppna Visual Studio: Starta din Visual Studio IDE.
2. Skapa ett nytt projekt: Starta ett nytt C#-projekt eller öppna ett befintligt där du tänker använda Aspose.Tasks.
3. Lägg till Aspose.Tasks-referens: Högerklicka på ditt projekt i Solution Explorer, välj "Hantera NuGet-paket", sök efter "Aspose.Tasks" och installera den senaste versionen.
4. Importera Aspose.Tasks Namespace: Överst i din C#-fil, lägg till följande med hjälp av direktiv:
```csharp
using Aspose.Tasks;
using System;

```
## Steg 1: Definiera dokumentkatalog
Ange först sökvägen till katalogen som innehåller din MS Project-fil.
```csharp
String DataDir = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med den faktiska sökvägen till din projektfil.
## Steg 2: Ladda projektfilen
 Instantiera en ny`Project` objekt genom att ladda MS Project-filen.
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Detta initierar projektobjektet med den angivna filen.
## Steg 3: Läs dispositionskoder
Iterera igenom alla uppgifter i projektet och hämta deras dispositionskoder.
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
Det här kodavsnittet går igenom varje uppgift, kontrollerar om den har dispositionskoder och skriver ut detaljer som fält-ID, värdeguide och värde-id för varje dispositionskod som är kopplad till uppgiften.

## Slutsats
Sammanfattningsvis ger Aspose.Tasks för .NET kraftfulla funktioner för att hantera Microsoft Project-konturkoder programmatiskt. Genom att följa stegen som beskrivs i denna handledning kan du effektivt läsa och manipulera dispositionskoder i dina MS Project-filer med C#.
## FAQ's
### F: Kan jag ändra konturkoder med Aspose.Tasks?
S: Ja, du kan modifiera konturkoder programmatiskt med Aspose.Tasks för .NET. Få helt enkelt tillgång till uppgifternas dispositionskoder och uppdatera deras värden efter behov.
### F: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project?
S: Aspose.Tasks stöder ett brett utbud av Microsoft Project-versioner, inklusive 2003, 2007, 2010, 2013, 2016 och 2019.
### F: Kräver Aspose.Tasks en licens för kommersiellt bruk?
S: Ja, en giltig licens krävs för kommersiell användning av Aspose.Tasks. Du kan få en licens från Asposes webbplats.
### F: Kan jag prova Aspose.Tasks innan jag köper?
S: Ja, du kan ladda ner en gratis testversion av Aspose.Tasks från webbplatsen för att utvärdera dess funktioner och möjligheter.
### F: Var kan jag få support för Aspose.Tasks?
 S: Du kan få support för Aspose.Tasks genom att besöka forumet på[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15).## Komplett källkod
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
