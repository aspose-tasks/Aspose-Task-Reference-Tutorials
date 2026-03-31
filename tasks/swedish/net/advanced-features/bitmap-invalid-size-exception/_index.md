---
date: 2026-03-21
description: Lär dig hur du exporterar en bild och hanterar BitmapInvalidSizeException
  när du sparar ett projekt som bild i Aspose.Tasks för .NET. Inkluderar steg för
  att spara projektet som bild och exportera projektet till PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man exporterar bild och hanterar undantag för ogiltig storlek
url: /sv/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så exporterar du bild – Hantera ogiltigt storleksundantag för Bitmap i Aspose.Tasks

I den här handledningen lär du dig **hur du exporterar bild** från en Microsoft Project‑fil med Aspose.Tasks för .NET och, ännu viktigare, hur du fångar `BitmapInvalidSizeException` som kan uppstå under processen. Att exportera ett projekt som en bild är ett vanligt krav för rapporterings‑dashboards, dokumentation eller helt enkelt för att dela en visuell ögonblicksbild av ett schema. I slutet av guiden kan du **spara projekt som bild** på ett pålitligt sätt och även **exportera projekt till PNG**‑format utan oväntade krascher.

## Snabba svar
- **Vilket undantag kan uppstå vid export av en bild?** `BitmapInvalidSizeException`  
- **Vilket format används i exemplet?** PNG (`SaveFileFormat.Png`)  
- **Behöver jag en speciell licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning.  
- **Kan jag ändra tidslinjen?** Ja – du kan ange tidslinjeenheten (minuter, timmar, dagar osv.).  
- **Är koden kompatibel med .NET Core?** Absolut – samma API fungerar på .NET Framework och .NET Core.

## Vad är BitmapInvalidSizeException?
`BitmapInvalidSizeException` kastas när bitmap‑dimensionerna som beräknas för bilden ligger utanför det stödjade intervallet (t.ex. bredd eller höjd är noll eller överskrider interna gränser). Detta händer vanligtvis när tidslinjen eller vyinställningarna skapar en bild som är för stor eller för liten.

## Varför exportera ett projekt som en bild?
- **Visuell rapportering** – bädda in ett Gantt‑diagram i PDF‑filer, Word‑dokument eller webbsidor.  
- **Plattformsoberoende delning** – PNG‑filer kan visas på vilken enhet som helst utan att Microsoft Project behövs.  
- **Prestanda** – bilder är lätta jämfört med fullständiga projektfiler för snabba förhandsvisningar.

## Förutsättningar
1. Grundläggande kunskap om C# och .NET‑utveckling.  
2. Aspose.Tasks för .NET installerat (NuGet‑paket `Aspose.Tasks`).  
3. En exempel‑Microsoft Project‑fil (t.ex. `Blank2010.mpp`).  

## Importera namnrymder
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg‑för‑steg guide

### Steg 1: Initiera projektet och välj en vy
Först skapar du en `Project`‑instans och väljer den vy du vill rendera (här använder vi den första Gantt‑diagramvyn).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Steg 2: Konfigurera bildsparalternativ (Exportera projekt till PNG)
Ange önskat bildformat och låt Aspose.Tasks använda tidslinjen som definierats i vyn.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Steg 3: Justera tidslinjeenheten (Kontrollera bildstorlek)
Att ändra tidslinjen påverkar bitmap‑dimensionerna. I det här exemplet använder vi **minuter** för att hålla bildstorleken hanterbar.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Steg 4: Försök att spara projektet som en bild
Denna rad utför den faktiska **spara projekt som bild**‑operationen.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Steg 5: Fånga och hantera BitmapInvalidSizeException
Omge spar‑anropet med ett `try / catch`‑block så att din applikation kan reagera smidigt om bitmap‑storleken är ogiltig.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|----------|
| Undantaget kastas fortfarande efter att tidslinjen justerats | Tidslinjen resulterar fortfarande i en för stor bitmap | Minska `view.MiddleTimescaleTier.Count` eller byt till en grövre `TimescaleUnit` (t.ex. timmar). |
| Utdatfilen är tom | Felaktig filsökväg eller saknade skrivbehörigheter | Verifiera att `DataDir` pekar på en skrivbar mapp och att filnamnet slutar med `.png` om du ändrar formatet. |
| Bildkvaliteten är dålig | Standard‑DPI kan vara låg | Ställ in `options.DpiX` och `options.DpiY` till högre värden (t.ex. 300). |

## Vanliga frågor

**Q: Vad orsakar BitmapInvalidSizeException i Aspose.Tasks?**  
A: Det inträffar när de beräknade bitmap‑dimensionerna är ogiltiga – vanligtvis för att tidslinjen skapar en bild som är för stor eller har noll bredd/höjd.

**Q: Kan jag anpassa tidslinjen när jag exporterar en bild?**  
A: Ja. Du kan ändra `view.MiddleTimescaleTier.Unit` och `Count` för att passa dina behov, som visas i handledningen.

**Q: Stöder Aspose.Tasks andra bildformat förutom PNG?**  
A: Absolut. `SaveFileFormat` inkluderar även JPEG, BMP, GIF och TIFF. Byt bara enum‑värdet i `ImageSaveOptions`.

**Q: Krävs en licens för att exportera bilder i en produktionsmiljö?**  
A: Ja. Biblioteket fungerar i evalueringsläge, men en kommersiell licens tar bort evalueringsbegränsningarna och ger full support.

**Q: Hur kan jag förbättra kvaliteten på den exporterade PNG‑filen?**  
A: Öka DPI‑inställningarna (`options.DpiX` och `options.DpiY`) eller justera projektets tidslinje för att producera en större bitmap.

## Slutsats
Genom att följa stegen ovan vet du nu **hur du exporterar bild** från en projektfil, hur du **sparar projekt som bild**, och hur du på ett smidigt sätt hanterar `BitmapInvalidSizeException`. Dessa tekniker gör dina rapporteringsflöden mer robusta och säkerställer att visuella exporter fungerar pålitligt oavsett projektstorlek och tidslinje.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-03-21  
**Testat med:** Aspose.Tasks 24.12 for .NET  
**Författare:** Aspose