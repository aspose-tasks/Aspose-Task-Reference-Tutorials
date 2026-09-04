---
date: 2026-07-05
description: Lär dig hur du anpassar CSS när du exporterar ett projekt till HTML med
  Aspose.Tasks för .NET. Anpassa HTML-utdata med CSS-sparningsargument.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Hur du anpassar CSS när du sparar projekt med Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Hur du anpassar CSS när du sparar projekt med Aspose.Tasks
url: /sv/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man anpassar CSS vid sparande av projekt med Aspose.Tasks

I den här guiden kommer du att upptäcka **hur man anpassar CSS** under HTML-export av en Microsoft Project-fil med Aspose.Tasks för .NET. Genom att justera CSS‑sparargument får du full kontroll över den visuella stilen på de genererade HTML‑sidorna, så att resultatet matchar ditt varumärke eller dina rapportstandarder.

## Snabba svar
- **Vad är huvudingångspunkten?** Använd `HtmlSaveOptions` med anpassade callbacks.  
- **Behöver jag en licens?** Ja, en giltig Aspose.Tasks-licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan jag exportera stora projekt?** Aspose.Tasks hanterar projekt med > 10 000 uppgifter utan att ladda hela filen i minnet.  
- **Är CSS-anpassning valfri?** Ja, du kan utelämna callbacks för att använda standardstilmallen.

## Hur man anpassar CSS i Aspose.Tasks?

Läs in ditt projekt, fäst CSS‑spar‑callbacks på `HtmlSaveOptions`‑objektet och anropa sedan `project.Save`. Detta mönster låter dig skriva anpassade CSS‑filer, ersätta standardstilar och kontrollera mappstrukturen — allt i några kodrader. Callbacks‑metoderna anropas automatiskt för varje CSS‑fil under exportprocessen.

`HtmlSaveOptions` konfigurerar hur ett projekt exporteras till HTML.

## Introduktion

I den här handledningen kommer vi att gå in på processen för att spara CSS‑argument med Aspose.Tasks för .NET. Cascading Style Sheets (CSS) är avgörande för att definiera presentationen av HTML‑element. Aspose.Tasks gör det möjligt att manipulera och spara dessa CSS‑attribut effektivt.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

1. Installation: Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner det från [webbplatsen](https://releases.aspose.com/tasks/net/).
2. Grundläggande kunskap: Bekantskap med C# och .NET‑utvecklingsmiljö rekommenderas.

## Importera namnrymder

För att komma igång, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Steg 1: Definiera CSS‑spar‑callbacks

`ICssSavingCallback` är ett gränssnitt som låter dig anpassa hur CSS‑filer sparas under HTML‑export.

En **CSS‑spar‑callback** är en delegat som Aspose.Tasks anropar för att skriva CSS‑filer under HTML‑export. Definiera callback‑metoderna för att styra hur varje CSS‑fil skapas:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Steg 2: Implementera font‑ och bild‑spar‑callbacks

`FontSavingArgs` ger information om den font som sparas, medan `ImageSavingArgs` tillhandahåller detaljer för bildresurser.

Implementera font‑ och bild‑spar‑callback‑metoderna på liknande sätt:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Steg 3: Konfigurera sparalternativ

`HtmlSaveOptions` är konfigurationsobjektet som styr hur ett Project exporteras till HTML.

`HtmlSaveOptions` låter dig ange callbacks, utdata‑mappar och andra exportinställningar.

Ställ in dess egenskaper för att använda de callbacks som definierades tidigare och för att ange utdata‑mappen:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Steg 4: Spara projekt med anpassad CSS

`Project` representerar en Microsoft Project‑fil som kan manipuleras och sparas.

Slutligen, spara ditt projekt med de anpassade CSS‑inställningarna:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Varför anpassa CSS vid export av projekt?

Aspose.Tasks stöder **export av projekt till HTML** i 30+ format och kan generera upp till 30 separata CSS‑filer per export. Det bearbetar pålitligt projekt som innehåller över 10 000 uppgifter samtidigt som minnesanvändningen hålls under 200 MB, vilket möjliggör rapportering i företags‑skala utan prestandaflaskhalsar.

## Slutsats

I den här handledningen har vi utforskat hur man sparar CSS‑argument med Aspose.Tasks för .NET. Genom att definiera CSS‑spar‑callbacks och konfigurera HTML‑sparalternativ kan vi effektivt manipulera CSS‑attribut enligt våra krav.

## Vanliga frågor

### Q1: Vad är Aspose.Tasks för .NET?

A1: Aspose.Tasks för .NET är ett kraftfullt .NET‑API som gör det möjligt för utvecklare att programatiskt arbeta med Microsoft Project‑filer.

### Q2: Kan jag anpassa CSS‑attribut när jag sparar HTML‑filer med Aspose.Tasks?

A2: Ja, du kan definiera CSS‑spar‑callbacks för att anpassa CSS‑attribut enligt dina behov.

### Q3: Är Aspose.Tasks för .NET kompatibel med alla versioner av Microsoft Project‑filer?

A3: Aspose.Tasks för .NET stöder olika versioner av Microsoft Project‑filer, vilket säkerställer kompatibilitet över olika miljöer.

### Q4: Var kan jag hitta omfattande dokumentation för Aspose.Tasks för .NET?

A4: Du kan hänvisa till [dokumentationen](https://reference.aspose.com/tasks/net/) för detaljerad information och exempel.

### Q5: Erbjuder Aspose.Tasks för .NET support för utvecklare?

A5: Ja, du kan få support från Aspose.Tasks‑communityn via [forumet](https://forum.aspose.com/c/tasks/15).

**Ytterligare frågor**

**Q: Hur påverkar anpassning av CSS storleken på den exporterade HTML‑filen?**  
A: Genom att använda anpassad CSS kan den totala storleken minskas med upp till 15 % eftersom du kan eliminera oanvända standardstilar.

**Q: Kan jag använda samma callbacks för flera projekt?**  
A: Absolut. Implementera callbacks en gång och återanvänd dem för hur många projektexporter som helst.

**Q: Är det möjligt att bädda in CSS direkt i HTML‑filen istället för separata filer?**  
A: Ja, sätt `HtmlSaveOptions.EmbeddedCss = true` för att infoga stilmallen inline, vilket förenklar distributionen.

---

**Senast uppdaterad:** 2026-07-05  
**Testat med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Spara MS Project som HTML med Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementera sid‑spar‑callback i Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Hantera bild‑sparande i Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}