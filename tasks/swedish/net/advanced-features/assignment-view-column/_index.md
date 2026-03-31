---
date: 2026-03-19
description: Lär dig hur du lägger till flera anpassade kolumner och formaterar anpassad
  kolumnbredd när du exporterar ett projekt till XML med Aspose.Tasks för .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Lägg till flera anpassade kolumner i tilldelningsvyn i Aspose.Tasks
url: /sv/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till flera anpassade kolumner i tilldelningsvyn i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att upptäcka **hur du lägger till flera anpassade kolumner** i en tilldelningsvy med Aspose.Tasks för .NET. Anpassade kolumner låter dig visa extra data—såsom anteckningar, kostnader eller anpassade flaggor—direkt i exporterade rapporter. I slutet av guiden kommer du att kunna formatera bredden på anpassade kolumner, exportera projektet till XML och anpassa vyn så att den matchar dina projektledningsbehov.

## Snabba svar
- **Vad kan jag uppnå?** Visa vilken tilldelningsdata som helst i anpassade kolumner och kontrollera deras utseende.  
- **Vilket format stöder det?** Exportera projekt till XML (eller andra format) med `Spreadsheet2003SaveOptions`.  
- **Behöver jag en licens?** Ja, en giltig Aspose.Tasks-licens krävs för produktionsanvändning.  
- **Vilka .NET-versioner fungerar?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur många kolumner kan jag lägga till?** Obegränsat – skapa bara ytterligare `AssignmentViewColumn`-instanser.

## Vad är flera anpassade kolumner?
Flera anpassade kolumner är användardefinierade fält som visas bredvid standardkolumnerna för tilldelningar när ett projekt sparas eller exporteras. De ger dig flexibiliteten att visa vilken egenskap som helst i ett `ResourceAssignment`-objekt, såsom anpassade anteckningar, kostnadskoder eller beräknade värden.

## Varför lägga till flera anpassade kolumner i tilldelningsvyn?
- **Förbättrad rapportering:** Inkludera projektspecifik information som inte täcks av de inbyggda kolumnerna.  
- **Bättre beslutsfattande:** Intressenter kan se exakt den data de behöver utan att gräva i råa filer.  
- **Konsekvent formatering:** Kontrollera kolumnbredd och textkonvertering för ett rent, läsbart resultat.  

## Förutsättningar

Innan vi dyker in, se till att du har:

1. Grundläggande kunskap om programmeringsspråket C#.  
2. Aspose.Tasks för .NET-biblioteket installerat. Om inte, kan du ladda ner det **[här](https://releases.aspose.com/tasks/net/)**.  
3. En integrerad utvecklingsmiljö (IDE) såsom Visual Studio.  

## Steg‑för‑steg‑guide

### Steg 1: Importera namnrymder
Först, importera namnrymderna som tillhandahåller de klasser vi behöver för att arbeta med projekt och visualiseringar.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Steg 2: Ladda projektet
Skapa en `Project`-instans och ladda en befintlig MPP-fil.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Steg 3: Skapa Spreadsheet Save Options
Instansiera `Spreadsheet2003SaveOptions` – detta objekt låter oss anpassa tilldelningsvyn innan export.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Steg 4: Definiera anpassad kolumn
Skapa en `AssignmentViewColumn` för varje datapunkt du vill visa. Nedan lägger vi till en **Notes**-kolumn med en bredd på 200 punkter.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tips:** För att lägga till *flera* anpassade kolumner, upprepa detta steg med olika fältnamn och delegatlogik, och lägg sedan till varje instans i `options.AssignmentView.Columns`.

### Steg 5: Lägg till anpassad kolumn i alternativ
Lägg till kolumnen (eller kolumnerna) i `Columns`-samlingen för tilldelningsvyn.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Steg 6: Iterera genom tilldelningar (valfri felsökning)
Du kan loopa genom tilldelningarna för att verifiera att texten för den anpassade kolumnen genereras korrekt.

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

### Steg 7: Spara projektet med anpassade kolumner
Slutligen, spara projektet. Exemplet sparar till XML, men du kan välja vilket stödformat som helst.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Hur exporterar man projekt till XML med anpassade kolumner?
När du anropar `project.Save` med de konfigurerade `Spreadsheet2003SaveOptions` skriver Aspose.Tasks projektdata—inklusive alla **flera anpassade kolumner**—till den valda XML-filen. Detta gör det enkelt att dela berikad projektinformation med andra system eller intressenter.

## Formatera bredden på anpassade kolumner för bättre läsbarhet
Den andra parametern i `AssignmentViewColumn`-konstruktorn styr kolumnbredden (mätt i punkter). Justera detta värde för att passa den mängd text du förväntar dig. Till exempel fungerar en bredd på **300** bra för längre anteckningar, medan **100** räcker för korta flaggor.

## Vanliga problem och lösningar
- **Kolumntext visas tom:** Se till att delegaten returnerar en sträng och att den underliggande tilldelningsegenskapen (t.ex. `Asn.NotesText`) är ifylld.  
- **Kolumner syns inte i den exporterade filen:** Verifiera att `options.AssignmentView.Columns` innehåller dina anpassade kolumner innan du anropar `Save`.  
- **Bredden verkar ignoreras:** Vissa exportformat har egna layoutregler; XML respekterar bredden, men PDF/HTML kan behöva ytterligare styling.

## Vanliga frågor

### Q1: Kan jag lägga till flera anpassade kolumner i tilldelningsvyn?
**A:** Ja, skapa helt enkelt ytterligare `AssignmentViewColumn`-objekt och lägg till varje i `options.AssignmentView.Columns`.

### Q2: Finns det fördefinierade konverterare tillgängliga för vanliga tilldelningsfält?
**A:** Ja, Aspose.Tasks tillhandahåller inbyggda konverterare för många standardfält, vilket gör det enkelt att hämta data utan att skriva anpassade delegater.

### Q3: Kan jag anpassa utseendet på anpassade kolumner, såsom formatering av text eller tillämpning av stilar?
**A:** Absolut. Förutom att ställa in bredden kan du ändra teckensnitt, justering och andra visuella egenskaper via kolumnens stilalternativ.

### Q4: Är det möjligt att ta bort standardkolumner från tilldelningsvyn?
**A:** Du kan exkludera standardkolumner genom att ta bort dem från `Columns`-samlingen eller genom att sätta deras bredd till noll.

### Q5: Stöder Aspose.Tasks att exportera projekt till andra format än kalkylblad med anpassade kolumner?
**A:** Ja, Aspose.Tasks kan exportera till PDF, HTML, XML och många andra format samtidigt som anpassade kolumndefinitioner bevaras.

---

**Senast uppdaterad:** 2026-03-19  
**Testat med:** Aspose.Tasks 24.12 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}