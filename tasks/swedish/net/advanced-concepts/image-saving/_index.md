---
date: 2026-03-05
description: Lär dig hur du sparar bilder, genererar HTML med bilder och anpassar
  bildexport med Aspose.Tasks för .NET. Steg‑för‑steg‑guide för att spara projektet
  som HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hur man sparar bilder med Aspose.Tasks för .NET
url: /sv/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man sparar bilder med Aspose.Tasks för .NET

## Introduktion

I den här handledningen kommer du att upptäcka **hur man sparar bilder** från Microsoft Project‑filer med hjälp av Aspose.Tasks‑API‑et för .NET. Oavsett om du behöver bädda in diagram i rapporter, generera HTML‑sidor som innehåller projektvisualiseringar, eller helt enkelt exportera diagramresurser, så guidar stegen nedan dig genom hela processen – från att konfigurera projektobjektet till att anpassa bild‑export‑callback‑funktionerna.

## Snabba svar
- **Vad betyder “hur man sparar bilder” i Aspose.Tasks?**  
  Det avser att använda gränssnittet `IImageSavingCallback` för att styra var och hur visuella resurser skrivs till disk.
- **Kan jag spara ett projekt som HTML med inbäddade bilder?**  
  Ja, genom att använda `HtmlSaveOptions` tillsammans med bild‑spar‑callback‑funktioner kan du **spara projekt som HTML** som inkluderar alla genererade bilder.
- **Behöver jag en licens för bildexport?**  
  En tillfällig utvärderingslicens fungerar för testning; en fullständig licens krävs för produktionsanvändning.
- **Vilka .NET‑versioner stöds?**  
  Aspose.Tasks för .NET stöder .NET Framework 4.5+, .NET Core 3.1+, och .NET 5/6+.
- **Är det möjligt att anpassa bildexport (format, mapp, namn)?**  
  Absolut – callback‑funktionen ger dig full kontroll över filnamn, format och destination.

## Vad är “hur man sparar bilder” i samband med Aspose.Tasks?
Att spara bilder innebär att extrahera visuella element (diagram, Gantt‑staplar, resursgrafik) från en Project‑fil och skriva dem till bildfiler (PNG, JPEG osv.). Aspose.Tasks tillhandahåller en flexibel callback‑mekanism som låter dig bestämma exakt plats, namnkonvention och till och med bildformat.

## Varför använda Aspose.Tasks för att spara bilder?
- **Fullt programatiskt kontroll** – ingen manuell UI‑interaktion krävs.  
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS via .NET Core.  
- **Högupplöst rendering** – bilder behåller samma kvalitet som den ursprungliga Project‑vyn.  
- **Enkel HTML‑generering** – kombinera `HtmlSaveOptions` med bild‑callback‑funktioner för att **automatiskt generera HTML med bilder**.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Visual Studio installerat på din utvecklingsmaskin.  
2. Aspose.Tasks för .NET nedladdat från [här](https://releases.aspose.com/tasks/net/).  
3. Grundläggande kunskap om C# och .NET‑projektstruktur.

## Importera namnrymder

Först, importera de nödvändiga namnrymderna i din källfil:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Steg 1: Skapa ett Project‑objekt

Läs in Microsoft Project‑filen du vill arbeta med:

```csharp
var project = new Project("Project1.mpp");
```

## Steg 2: Definiera sparalternativ

Skapa HTML‑sparalternativen som också kommer att innehålla våra bild‑spar‑callback‑funktioner:

```csharp
var options = GetSaveOptions(1);
```

## Steg 3: Spara projektet som HTML (spara projekt som html)

Exportera nu projektet till en HTML‑fil. Bilderna som refereras i HTML‑filen kommer att genereras av callback‑funktionen vi definierar härnäst:

```csharp
project.Save("document_out.html", options);
```

## Steg 4: Implementera bildspar‑callback (anpassa bildexport)

Implementera `IImageSavingCallback`‑gränssnittet. Här kan du **anpassa bildexport**‑beteendet:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Steg 5: Spara bilder till angiven katalog

Inuti `ImageSaving`‑metoden, bestäm var varje bild ska lagras. Exemplet nedan skiljer PNG‑resurser från andra format:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Steg 6: Specificera sparalternativ (inklusive callbacks)

Koppla ihop callbacks för teckensnitt, CSS och bilder. Detta säkerställer att varje visuellt element hanteras konsekvent:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Bilder visas inte i den genererade HTML‑filen | Callback tilldelar inte en giltig filsökväg | Se till att `args.Path` pekar på en skrivbar mapp och att `args.ImageStream` sätts korrekt. |
| PNG‑filer sparas med fel filändelse | Villkorslogiken kontrollerar endast suffixet “png” | Använd `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` för robust detektering. |
| HTML‑referenser brutna efter att filer flyttats | Relativa sökvägar ändrades efter att output‑mappen flyttades | Behåll HTML‑ och bildmapparna tillsammans eller uppdatera `options.ImageFolder` därefter. |

## Slutsats

Genom att följa dessa steg vet du nu **hur man sparar bilder** från en Project‑fil, **spara projekt som HTML**, och **anpassa bildexport** för att passa din applikations mappstruktur. Detta tillvägagångssätt låter dig **generera HTML med bilder** som kan bäddas in i rapporter, dokumentationsportaler eller webb‑dashboards sömlöst.

## Vanliga frågor

**Q1: Kan jag använda Aspose.Tasks för att manipulera projektfiler i andra format än HTML?**  
A1: Ja, Aspose.Tasks stöder olika format såsom PDF, XLSX och MPP.

**Q2: Erbjuder Aspose.Tasks stöd för integration med molnlagring?**  
A2: Ja, Aspose.Tasks erbjuder API:er för att arbeta med populära molnlagringstjänster som Amazon S3 och Google Drive.

**Q3: Är Aspose.Tasks kompatibel med .NET Core?**  
A3: Ja, Aspose.Tasks är kompatibel med .NET Core, vilket gör att du kan utveckla plattformsoberoende applikationer.

**Q4: Kan jag anpassa utseendet på sparade bilder?**  
A4: Ja, du kan anpassa utseendet på sparade bilder genom att ändra logiken för bildsparande i callback‑metoderna.

**Q5: Erbjuder Aspose.Tasks provversioner för utvärderingsändamål?**  
A5: Ja, du kan skaffa en gratis provversion av Aspose.Tasks från [här](https://releases.aspose.com/).

---

**Senast uppdaterad:** 2026-03-05  
**Testad med:** Aspose.Tasks 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}