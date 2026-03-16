---
date: 2026-03-16
description: Lär dig hur du implementerar en callback för sidlagring i Aspose.Tasks
  för .NET, vilket möjliggör anpassad hantering av flersidiga dokumentutmatningsströmmar.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementera callback för sidsparning i Aspose.Tasks
url: /sv/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementera page saving callback i Aspose.Tasks

## Introduktion

I den här handledningen kommer du att lära dig hur du **implement page saving callback** i Aspose.Tasks för .NET. Denna kraftfulla funktion låter dig rikta varje sida i ett flersidigt dokument till en ström du väljer, vilket ger dig full kontroll över hur utdata lagras eller vidarebehandlas.

## Snabba svar
- **Vad gör page saving callback?** Den fångar varje renderad sida i en separat ström så att du kan hantera dem individuellt.  
- **Vilket format kan jag exportera till?** Alla format som stöds av `ImageSaveOptions`, t.ex. PNG, JPEG, PDF.  
- **Behöver jag en licens?** En giltig Aspose.Tasks‑licens krävs för produktionsanvändning.  
- **Kan jag använda detta med .NET Core?** Ja, Aspose.Tasks stöder fullt ut .NET Core och .NET 5/6+.  
- **Är återuppringningen trådsäker?** Återuppringningen körs på samma tråd som utför renderingen, så vanliga trådsäkerhetsregler gäller.

## Vad är **implement page saving callback**?
Mönstret **implement page saving callback** låter dig ansluta anpassad logik till sparnings‑pipeline i Aspose.Tasks. Istället för att skriva direkt till en fil får du ett `Stream`‑objekt för varje sida, vilket gör att du kan lagra det i minnet, ladda upp till molnlagring eller tillämpa ytterligare bearbetning.

## Varför exportera projekt som PNG med en återuppringning?
Att exportera ett projekt som PNG ger dig en rasterbild av varje Gantt‑diagramssida, vilket är idealiskt för rapporter, e‑post eller inbäddning i webbsidor. Genom att använda en återuppringning kan du behålla varje sida i ett separat `MemoryStream` utan att skapa temporära filer på disken.

## Förutsättningar

1. **C#‑kunskap** – grundläggande förståelse för klasser, gränssnitt och strömmar.  
2. **Aspose.Tasks för .NET** – ladda ner och installera från [here](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider eller någon .NET‑kompatibel editor.

## Importera namnrymder

För att börja, importera de nödvändiga namnrymderna:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Steg 1: Skapa ett Project‑objekt

Läs in en befintlig MPP‑fil i en `Project`‑instans:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Steg 2: Konfigurera Image Save Options

Ställ in `ImageSaveOptions` för PNG‑utmatning och anslut den anpassade återuppringningen:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Proffstips:** Att sätta `RenderToSinglePage = false` säkerställer att varje Gantt‑diagramssida renderas separat, vilket är avgörande för att återuppringningen ska få separata strömmar.

## Steg 3: Spara projekt med återuppringning

Anropa `Save`‑metoden och skicka `Stream.Null` eftersom de faktiska strömmarna levereras av återuppringningen:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Steg 4: Bearbeta sparade sidströmmar

När sparningsoperationen är klar håller återuppringningen en samling `MemoryStream`‑objekt – en per sida. Du kan nu iterera över dem:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Steg 5: Implementera anpassad page saving callback

Skapa en sealed‑klass som implementerar `IPageSavingCallback`. Denna klass fångar varje sidas ström och lagrar den i en lista för senare användning.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Vanliga fallgropar & felsökning

| Problem | Orsak | Lösning |
|-------|--------|----------|
| **Inga sidor returneras** | `RenderToSinglePage` lämnades som `true`. | Sätt `RenderToSinglePage = false` för att generera separata sidor. |
| **Strömmar är tomma** | `KeepStreamOpen` satt till `true` utan att stänga senare. | Behåll den som `false` (standard) och låt återuppringningen stänga strömmarna automatiskt. |
| **Out‑of‑memory‑fel** | Mycket stora projekt genererar många högupplösta PNG‑filer. | Bearbeta strömmarna en efter en eller öka VM‑minnesgränserna. |

## Vanliga frågor

**Q1: Vad är en page saving callback i Aspose.Tasks?**  
A: En page saving callback låter dig avbryta sparningsprocessen för varje sida i ett flersidigt dokument och tillhandahåller en anpassad `Stream` för den sidan.

**Q2: Kan jag använda olika format för att spara sidor med denna återuppringning?**  
A: Ja. Genom att ändra `SaveFileFormat` kan du exportera till PNG, JPEG, PDF, SVG osv.

**Q3: Är Aspose.Tasks kompatibel med .NET Core?**  
A: Absolut. Aspose.Tasks stödjer .NET Core, .NET 5 och .NET 6.

**Q4: Hur kan jag hantera fel under page saving‑processen?**  
A: Omslut återuppringningslogiken i try/catch‑block och logga undantag. `OnFinish`‑metoden är ett bra ställe för slutlig städning.

**Q5: Var kan jag hitta fler resurser och support för Aspose.Tasks?**  
A: Du kan besöka [Aspose.Tasks‑forumet](https://forum.aspose.com/c/tasks/15) för hjälp, få åtkomst till dokumentation [här](https://reference.aspose.com/tasks/net/), eller utforska ytterligare funktioner och licensalternativ på [Aspose.Tasks‑webbplatsen](https://purchase.aspose.com/buy).

---

**Senast uppdaterad:** 2026-03-16  
**Testad med:** Aspose.Tasks 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}