---
date: 2026-03-16
description: Leer hoe u een callback voor het opslaan van pagina's implementeert in
  Aspose.Tasks voor .NET, waardoor u aangepaste verwerking van uitvoerstromen van
  meerpagina‑documenten mogelijk maakt.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementeer callback voor het opslaan van pagina's in Aspose.Tasks
url: /nl/net/advanced-concepts/page-saving-callback/
weight: 12
---

 any missed items: The bullet list under Quick Answers uses bold. Keep same formatting.

Make sure to keep code block placeholders unchanged.

Now craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementeer page saving callback in Aspose.Tasks

## Introductie

In deze tutorial leer je hoe je **page saving callback** implementeert in Aspose.Tasks voor .NET. Deze krachtige functie stelt je in staat elke pagina van een meer‑pagina document naar een door jou gekozen stream te sturen, waardoor je volledige controle hebt over hoe de output wordt opgeslagen of verder verwerkt.

## Snelle antwoorden
- **Wat doet de page saving callback?** Het legt elke gerenderde pagina vast in een aparte stream zodat je ze individueel kunt verwerken.  
- **Naar welk formaat kan ik exporteren?** Elk formaat dat wordt ondersteund door `ImageSaveOptions`, bijv. PNG, JPEG, PDF.  
- **Heb ik een licentie nodig?** Een geldige Aspose.Tasks-licentie is vereist voor productiegebruik.  
- **Kan ik dit gebruiken met .NET Core?** Ja, Aspose.Tasks ondersteunt volledig .NET Core en .NET 5/6+.  
- **Is de callback thread‑safe?** De callback draait op dezelfde thread die de rendering uitvoert, dus de normale thread‑veiligheidsregels gelden.

## Wat is **page saving callback**?
Het **page saving callback**‑patroon stelt je in staat aangepaste logica in de opslaanketen van Aspose.Tasks te injecteren. In plaats van direct naar een bestand te schrijven, ontvang je een `Stream`‑object voor elke pagina, waardoor je het in het geheugen kunt opslaan, naar cloudopslag kunt uploaden of extra verwerking kunt toepassen.

## Waarom project exporteren als PNG met een callback?
Een project exporteren als PNG levert een rasterafbeelding van elke Gantt‑chart‑pagina op, wat ideaal is voor rapporten, e‑mails of insluiten in webpagina's. Met een callback kun je elke pagina in een aparte `MemoryStream` bewaren zonder tijdelijke bestanden op schijf te maken.

## Vereisten

1. **C#-kennis** – basiskennis van klassen, interfaces en streams.  
2. **Aspose.Tasks voor .NET** – download en installeer vanaf [hier](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider of een andere .NET‑compatibele editor.

## Namespaces importeren

Om te beginnen importeer je de benodigde namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Stap 1: Maak een Project‑object

Laad een bestaand MPP‑bestand in een `Project`‑instantie:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Stap 2: Configureer Image Save Options

Stel `ImageSaveOptions` in voor PNG‑output en koppel de aangepaste callback:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Pro tip:** Door `RenderToSinglePage = false` in te stellen, wordt elke Gantt‑chart‑pagina afzonderlijk gerenderd, wat essentieel is zodat de callback afzonderlijke streams ontvangt.

## Stap 3: Sla project op met callback

Roep de `Save`‑methode aan en geef `Stream.Null` door omdat de daadwerkelijke streams door de callback worden geleverd:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Stap 4: Verwerk opgeslagen paginastreams

Na afloop van de opslaan‑operatie bevat de callback een collectie van `MemoryStream`‑objecten—één per pagina. Je kunt ze nu itereren:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Stap 5: Implementeer aangepaste page saving callback

Maak een sealed class die `IPageSavingCallback` implementeert. Deze class legt de stream van elke pagina vast en slaat deze op in een lijst voor later gebruik.

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

## Veelvoorkomende valkuilen & probleemoplossing

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Geen pagina's worden geretourneerd** | `RenderToSinglePage` staat op `true`. | Stel `RenderToSinglePage = false` in om afzonderlijke pagina's te genereren. |
| **Streams zijn leeg** | `KeepStreamOpen` staat op `true` zonder later te disposen. | Houd het op `false` (standaard) en laat de callback de streams automatisch sluiten. |
| **Out‑of‑memory fouten** | Zeer grote projecten genereren veel high‑resolution PNG's. | Verwerk streams één voor één of vergroot de VM‑geheugenlimieten. |

## Veelgestelde vragen

**Q1: Wat is een page saving callback in Aspose.Tasks?**  
A: Een page saving callback stelt je in staat het opslaan van elke pagina van een meer‑pagina document te onderscheppen, door een aangepaste `Stream` voor die pagina te bieden.

**Q2: Kan ik verschillende formaten gebruiken voor het opslaan van pagina's met deze callback?**  
A: Ja. Door `SaveFileFormat` te wijzigen kun je exporteren naar PNG, JPEG, PDF, SVG, enz.

**Q3: Is Aspose.Tasks compatibel met .NET Core?**  
A: Absoluut. Aspose.Tasks ondersteunt .NET Core, .NET 5 en .NET 6.

**Q4: Hoe kan ik fouten afhandelen tijdens het page saving proces?**  
A: Plaats de callback‑logica in try/catch‑blokken en log de uitzonderingen. De `OnFinish`‑methode is een goede plek voor de uiteindelijke opruiming.

**Q5: Waar kan ik meer bronnen en ondersteuning voor Aspose.Tasks vinden?**  
A: Je kunt het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken voor hulp, de documentatie raadplegen [hier](https://reference.aspose.com/tasks/net/), of extra functies en licentie‑opties verkennen op de [Aspose.Tasks‑website](https://purchase.aspose.com/buy).

**Laatst bijgewerkt:** 2026-03-16  
**Getest met:** Aspose.Tasks 24.12 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}