---
date: 2026-04-06
description: Lär dig hur du ändrar stapelns stil och anpassar stapelfärger i Aspose.Tasks
  för .NET för att förbättra projektvisualiseringen.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Stylingfält i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man ändrar stapelstil i Aspose.Tasks
url: /sv/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ändrar du stapelstil i Aspose.Tasks

## Introduktion

Om du behöver **hur man ändrar stapel**-utseendet i en Microsoft Project‑fil, ger Aspose.Tasks för .NET dig full kontroll över stapelfärger, former och textstilar. Genom att anpassa stapelfärger och andra visuella attribut kan du göra projektplaner mycket lättare att läsa och mer i linje med ditt företags varumärke. I den här handledningen går vi igenom ett komplett, steg‑för‑steg‑exempel som visar hur du ändrar stapelstil, från att ladda ett projekt till att exportera det med de nya visuella reglerna tillämpade.

## Snabba svar
- **Vad kan jag formatera?** Staplar, milstolpar och uppgiftstext i Gantt‑diagram.  
- **Vilket format stödjer stylade staplar?** PDF, XLSX, HTML och native MPP när de sparas med `PdfSaveOptions`.  
- **Behöver jag en licens?** En kommersiell licens krävs för produktionsbruk; en gratis provversion fungerar för testning.  
- **Kan jag tillämpa flera stilar?** Ja – lägg till så många `BarStyle`‑objekt du behöver.  
- **Är det .NET Core‑kompatibelt?** Absolut – fungerar med .NET Framework och .NET Core/5/6+.

## Vad är stapelstil i Aspose.Tasks?

Stapelstil låter dig definiera visuella regler som Aspose.Tasks‑motorn använder när den renderar Gantt‑diagram. Varje regel (en **BarStyle**) riktar sig mot en specifik objekttyp – uppgifter, milstolpar eller samlingsuppgifter – och låter dig ange färger, former och till och med anpassad text.

## Varför anpassa stapelfärger?

Att anpassa stapelfärger hjälper intressenter att omedelbart identifiera kritiska vägar, försenade uppgifter eller milstolpar. Det låter dig också matcha företagets färgscheman, vilket får rapporterna att se professionella och varumärkesanpassade ut.

## Förutsättningar

Innan vi börjar, se till att du har:

1. **Aspose.Tasks för .NET** – ladda ner det från [download page](https://releases.aspose.com/tasks/net/).  
2. En utvecklingsmiljö som stödjer .NET (Framework 4.6+, .NET Core 3.1+ eller senare).  
3. Grundläggande kunskaper i C# – exemplen använder enkel, självständig kod.

## Importera namnrymder

Importera först de namnrymder som innehåller de klasser vi ska använda:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Ladda projektet

Läs in en befintlig MPP‑fil (eller skapa en ny) så att du har ett projektobjekt att arbeta med:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Steg 2: Konfigurera sparalternativ

Skapa en `PdfSaveOptions`‑instans och initiera `BarStyles`‑samlingen där vi ska lagra våra anpassade stilar:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Steg 3: Definiera stapelstil

Nu bygger vi ett `BarStyle`‑objekt och sätter egenskaperna som styr hur stapeln ser ut. Här anpassar vi **stapelfärger** och former:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Steg 4: Anpassa textkonverterare (valfritt)

Om du vill justera texten som visas på stapeln kan du tilldela en egen konverterare. Exemplet lägger till prefix på uppgiftsnamn som inte redan börjar med “T”:

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

## Steg 5: Lägg till stapelstil i alternativ

Lägg till den fullständigt konfigurerade stilen i `BarStyles`‑samlingen på sparalternativen:

```csharp
options.BarStyles.Add(style);
```

## Steg 6: Spara projektet

Till sist exporterar du projektet. PDF‑filen (eller annat format) renderar Gantt‑diagrammet med den stapelstil vi definierat:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Stil för stapel tillämpas inte** | `BarStyles`‑samlingen var tom eller inte kopplad till sparalternativen. | Se till att du lägger till `BarStyle` i `options.BarStyles` innan du anropar `Save`. |
| **Färger ser annorlunda ut i PDF** | PDF‑rendering kan använda en annan färgprofil. | Använd standardvärden från `System.Drawing.Color` eller definiera egna ARGB‑färger. |
| **Textkonverterare kastar null‑referens** | Uppgiftsegenskapen `Tsk.Name` är null för vissa uppgifter. | Lägg till en null‑kontroll innan du åtkommer `task.Get(Tsk.Name)`. |

## Vanliga frågor

### Q1: Kan jag tillämpa flera stapelstilar på ett enda projekt?

A1: Ja, du kan definiera och tillämpa flera stapelstilar på olika typer av uppgifter i samma projekt.

### Q2: Är det möjligt att dynamiskt ändra stapelstilar under körning?

A2: Ja, du kan dynamiskt ändra stapelstilar baserat på vissa villkor eller användarpreferenser i din applikation.

### Q3: Stöder Aspose.Tasks att exportera projekt med stylade staplar till olika filformat?

A3: Ja, Aspose.Tasks stödjer export av projekt med stylade staplar till olika format såsom PDF, XLSX och HTML.

### Q4: Finns fördefinierade stapelstilar i Aspose.Tasks?

A4: Även om Aspose.Tasks tillhandahåller standardstapelstilar kan utvecklare också skapa egna stapelstilar anpassade efter deras projektbehov.

### Q5: Kan jag hämta och ändra befintliga stapelstilar i ett projekt via API:et?

A5: Ja, du kan programatiskt hämta och ändra befintliga stapelstilar med Aspose.Tasks för .NET API.

## Vanliga frågor

**Q: Hur ändrar jag stapelfärgen för vanliga uppgifter istället för milstolpar?**  
A: Ange `style.ItemType = BarItemType.Task;` och tilldela `style.BarColor` till önskad `Color`.

**Q: Kan jag använda detta tillvägagångssätt för att styla staplar vid export till HTML?**  
A: Ja. Använd `HtmlSaveOptions` och fyll dess `BarStyles`‑samling på samma sätt.

**Q: Finns det någon gräns för hur många stapelstilar jag kan definiera?**  
A: Praktiskt sett ingen; du kan lägga till så många du behöver, men tänk på prestanda för mycket stora samlingar.

**Q: Behöver jag anropa `project.Calculate()` efter att ha ändrat stilar?**  
A: Nej, stilar tillämpas under sparoperationen; omräkning behövs bara för schemaläggningsändringar.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}