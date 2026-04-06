---
date: 2026-04-06
description: Leer hoe u de balkstijl kunt wijzigen en de balkkleuren kunt aanpassen
  in Aspose.Tasks voor .NET om de projectvisualisatie te verbeteren.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Stijlbalk in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe de balkstijl te wijzigen in Aspose.Tasks
url: /nl/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe de balkstijlen wijzigen in Aspose.Tasks

## Inleiding

Als u de **hoe u balken wijzigt**‑uiterlijk in een Microsoft Project‑bestand moet aanpassen, biedt Aspose.Tasks voor .NET volledige controle over balkkleuren, vormen en tekststijlen. Door balkkleuren en andere visuele attributen aan te passen, kunt u projectplannen veel leesbaarder maken en beter laten aansluiten bij de huisstijl van uw organisatie. In deze tutorial lopen we stap voor stap een volledig voorbeeld door dat laat zien hoe u balkstijlen wijzigt, van het laden van een project tot het exporteren met de nieuwe visuele regels toegepast.

## Snelle antwoorden
- **Wat kan ik stylen?** Balken, mijlpalen en taaktekst in Gantt‑diagrammen.  
- **Welke indeling ondersteunt gestylede balken?** PDF, XLSX, HTML en native MPP wanneer opgeslagen met `PdfSaveOptions`.  
- **Heb ik een licentie nodig?** Een commerciële licentie is vereist voor productiegebruik; een gratis proefversie werkt voor testen.  
- **Kan ik meerdere stijlen toepassen?** Ja – voeg zoveel `BarStyle`‑objecten toe als u nodig heeft.  
- **Is het compatibel met .NET Core?** Absoluut – werkt met .NET Framework en .NET Core/5/6+.

## Wat is balkstijlen in Aspose.Tasks?

Balkstijlen laten u visuele regels definiëren die de Aspose.Tasks‑engine toepast bij het renderen van Gantt‑diagrammen. Elke regel (een **BarStyle**) richt zich op een specifiek itemtype—taken, mijlpalen of samenvattende taken—en stelt u in staat kleuren, vormen en zelfs aangepaste tekst in te stellen.

## Waarom balkkleuren aanpassen?

Het aanpassen van balkkleuren helpt belanghebbenden direct kritieke paden, vertraagde taken of mijlpalen te herkennen. Het stelt u ook in staat de bedrijfs­kleuren te volgen, waardoor rapporten er professioneel en merk‑consistent uitzien.

## Voorvereisten

Zorg ervoor dat u het volgende heeft:

1. **Aspose.Tasks for .NET** – download het vanaf de [downloadpagina](https://releases.aspose.com/tasks/net/).  
2. Een ontwikkelomgeving die .NET ondersteunt (Framework 4.6+, .NET Core 3.1+ of later).  
3. Basiskennis van C# – de voorbeelden gebruiken eenvoudige, zelfstandige code.

## Namespaces importeren

Importeer eerst de namespaces die de klassen bevatten die we gaan gebruiken:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Stap 1: Het project laden

Laad een bestaand MPP‑bestand (of maak een nieuw aan) zodat u een projectobject heeft om mee te werken:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Stap 2: Opslagopties configureren

Maak een `PdfSaveOptions`‑instantie aan en initialiseert de `BarStyles`‑collectie waarin we onze aangepaste stijlen opslaan:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Stap 3: Balkstijl definiëren

Nu bouwen we een `BarStyle`‑object en stellen we de eigenschappen in die bepalen hoe de balk eruitziet. Dit is waar we **balkkleuren** en vormen aanpassen:

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

## Stap 4: Tekstconverter aanpassen (optioneel)

Als u de tekst die op de balk verschijnt wilt aanpassen, kunt u een aangepaste converter toewijzen. Het voorbeeld voegt een voorvoegsel toe aan taaknamen die nog niet met “T” beginnen:

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

## Stap 5: Balkstijl toevoegen aan opties

Voeg de volledig geconfigureerde stijl toe aan de `BarStyles`‑collectie van de opslagopties:

```csharp
options.BarStyles.Add(style);
```

## Stap 6: Het project opslaan

Exporteer tenslotte het project. De PDF (of een ander formaat) zal het Gantt‑diagram weergeven met de balkstijl die we hebben gedefinieerd:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Balkstijl niet toegepast** | `BarStyles`‑collectie was leeg of niet gekoppeld aan de opslagopties. | Zorg ervoor dat u de `BarStyle` toevoegt aan `options.BarStyles` voordat u `Save` aanroept. |
| **Kleuren zien er anders uit in PDF** | PDF‑rendering kan een ander kleurprofiel gebruiken. | Gebruik standaard `System.Drawing.Color`‑waarden of definieer aangepaste ARGB‑kleuren. |
| **Tekstconverter geeft null‑referentie** | Taakeigenschap `Tsk.Name` is null voor sommige taken. | Voeg een null‑check toe voordat u `task.Get(Tsk.Name)` benadert. |

## Veelgestelde vragen

### Q1: Kan ik meerdere balkstijlen toepassen op één project?

A1: Ja, u kunt meerdere balkstijlen definiëren en toepassen op verschillende soorten taken binnen hetzelfde project.

### Q2: Is het mogelijk om balkstijlen dynamisch te wijzigen tijdens runtime?

A2: Ja, u kunt balkstijlen dynamisch aanpassen op basis van bepaalde voorwaarden of gebruikersvoorkeuren in uw applicatie.

### Q3: Ondersteunt Aspose.Tasks het exporteren van projecten met gestylede balken naar verschillende bestandsformaten?

A3: Ja, Aspose.Tasks ondersteunt het exporteren van projecten met gestylede balken naar diverse formaten zoals PDF, XLSX en HTML.

### Q4: Zijn er vooraf gedefinieerde balkstijlen beschikbaar in Aspose.Tasks?

A4: Hoewel Aspose.Tasks standaard balkstijlen biedt, kunnen ontwikkelaars ook aangepaste balkstijlen maken die zijn afgestemd op hun projectvereisten.

### Q5: Kan ik bestaande balkstijlen binnen een project ophalen en wijzigen via de API?

A5: Ja, u kunt bestaande balkstijlen programmatically ophalen en aanpassen met de Aspose.Tasks for .NET API.

## Veelgestelde vragen (FAQ)

**V: Hoe wijzig ik de balkkleur voor reguliere taken in plaats van mijlpalen?**  
A: Stel `style.ItemType = BarItemType.Task;` in en wijs `style.BarColor` toe aan de gewenste `Color`.

**V: Kan ik deze aanpak gebruiken om balken te stylen bij export naar HTML?**  
A: Ja. Gebruik `HtmlSaveOptions` en vul de `BarStyles`‑collectie op dezelfde manier.

**V: Is er een limiet aan het aantal balkstijlen dat ik kan definiëren?**  
A: Praktisch gezien geen; u kunt er zoveel toevoegen als nodig, maar houd rekening met de prestaties bij zeer grote collecties.

**V: Moet ik `project.Calculate()` aanroepen na het wijzigen van stijlen?**  
A: Nee, stijlen worden toegepast tijdens de opslaactie; herberekening is alleen nodig voor roosterwijzigingen.

---

**Laatst bijgewerkt:** 2026-04-06  
**Getest met:** Aspose.Tasks 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}