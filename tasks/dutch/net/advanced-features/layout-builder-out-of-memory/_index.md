---
date: 2026-03-24
description: Leer omgaan met out‑of‑memory en hoe je een projectafbeelding opslaat
  met Aspose.Tasks Layout Builder in .NET. Stapsgewijze gids met codevoorbeelden.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Out of Memory-afhandeling met Aspose.Tasks Layout Builder (C#)
url: /nl/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Out of Memory‑afhandeling met Aspose.Tasks Layout Builder

## Introductie

Out of memory‑afhandeling is een cruciaal onderdeel bij het bouwen van betrouwbare .NET‑toepassingen die met grote projectbestanden werken. Wanneer je visualisaties genereert met Aspose.Tasks Layout Builder, kun je snel tegen geheugen‑gerelateerde uitzonderingen aanlopen, vooral bij complexe Gantt‑diagrammen. In deze tutorial lopen we stap voor stap door hoe je **geheugen‑uitzonderingen afhandelt**, **de Gantt‑weergave aanpast**, en **het projectafbeelding veilig opslaat**, zodat je applicatie responsief blijft, zelfs bij enorme planningen.

## Snelle antwoorden
- **Wat is out of memory‑afhandeling?** Het beheren van geheugengebruik en het opvangen van `OutOfMemoryException`‑type fouten bij het verwerken van grote data.
- **Welke API helpt?** Aspose.Tasks Layout Builder voor .NET.
- **Typisch scenario?** Het renderen van een high‑resolution Gantt‑diagram naar PNG.
- **Belangrijke voorwaarde?** .NET (Framework 4.5+ of .NET 6) met Aspose.Tasks geïnstalleerd.
- **Hoe fouten opvangen?** Gebruik `try…catch`‑blokken voor `ApsLayoutBuilderOutOfMemoryException` en gerelateerde uitzonderingen.

## Voorvereisten

Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

1. **C#‑basiskennis** – je moet vertrouwd zijn met de standaard C#‑syntaxis.
2. **Aspose.Tasks voor .NET** geïnstalleerd. Als je het nog niet hebt toegevoegd, download het dan van [here](https://releases.aspose.com/tasks/net/).
3. **Een IDE** zoals Visual Studio (of VS Code met de C#‑extensie) om het voorbeeld te compileren en uit te voeren.

## Namespaces importeren

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Stapsgewijze handleiding

### Stap 1: Laad het project

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Deze regel laadt **Blank2010.mpp** in een `Project`‑instantie, zodat deze klaar is voor visualisatie.

### Stap 2: Pas de Gantt‑diagramweergave aan

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Hier **passen we de Gantt‑weergave** aan door de middelste en onderste tijdschaal‑lagen te wijzigen. Het aanpassen van deze lagen vermindert de hoeveelheid data die in één keer wordt gerenderd, wat kan helpen de geheugenbelasting te verlagen.

### Stap 3: Configureer afbeeldingsopties voor opslaan

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` vertelt Aspose.Tasks hoe het diagram moet worden gerenderd. We kiezen PNG als uitvoerformaat en koppelen de tijdschaal aan de weergave die we zojuist hebben aangepast.

### Stap 4: Sla het project op als afbeelding

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

De `Save`‑aanroep **slaat de projectafbeelding** op met de hierboven gedefinieerde opties. Als het project zeer groot is, is dit het moment waarop een out‑of‑memory‑situatie het meest waarschijnlijk optreedt.

### Stap 5: Afhandelen van uitzonderingen

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Door `ApsLayoutBuilderOutOfMemoryException` op te vangen, **handel je geheugen‑uitzonderingen** op een nette manier af, met een duidelijke melding in plaats van een crash. De tweede catch behandelt bitmap‑grootte‑problemen die ook kunnen optreden bij het renderen van enorme diagrammen.

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **OutOfMemoryException** | Het renderen van een zeer high‑resolution afbeelding verbruikt meer RAM dan het proces kan toewijzen. | Verklein de afbeeldingsafmetingen, vereenvoudig de tijdschaal‑lagen, of splits het diagram in meerdere afbeeldingen. |
| **BitmapInvalidSizeException** | De gevraagde bitmap‑grootte overschrijdt het maximale limiet van het platform. | Beperk breedte/hoogte in `ImageSaveOptions` of render in segmenten. |
| **Slow performance** | Grote projectbestanden vereisen veel verwerking. | Schakel `project.Set(Prj.SaveToCache, true)` in vóór het renderen, of gebruik een achtergrondthread. |

## Veelgestelde vragen

### V1: Wat is Aspose.Tasks voor .NET?

A1: Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars Microsoft Project‑bestanden programmatisch kunnen manipuleren in .NET‑toepassingen.

### V2: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?

A2: Je kunt een tijdelijke licentie voor Aspose.Tasks verkrijgen via [this link](https://purchase.aspose.com/temporary-license/).

### V3: Is Aspose.Tasks geschikt voor het verwerken van grote projectbestanden?

A3: Ja, Aspose.Tasks biedt functies en optimalisaties om grote projectbestanden efficiënt te verwerken, maar ontwikkelaars moeten nog steeds geheugenbeheerstrategieën overwegen.

### V4: Kan ik het uiterlijk van Gantt‑diagrammen aanpassen met Aspose.Tasks?

A4: Absoluut! Aspose.Tasks biedt uitgebreide mogelijkheden om het uiterlijk en de lay‑out van Gantt‑diagrammen aan te passen volgens jouw eisen.

### V5: Waar kan ik meer hulp en ondersteuning vinden voor Aspose.Tasks?

A5: Je kunt meer hulp en ondersteuning vinden, en deelnemen aan de community, op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Veelgestelde vragen

**V: Hoe kan ik het geheugenverbruik verminderen bij het opslaan van een projectafbeelding?**  
**A:** Verlaag de afbeeldingsresolutie, beperk het tijdschaal‑bereik, of sla het diagram op in meerdere kleinere segmenten.

**V: Is het mogelijk om de afbeelding direct naar een web‑respons te streamen?**  
**A:** Ja, je kunt `project.Save(stream, options)` gebruiken en de stream naar de HTTP‑respons schrijven.

**V: Ondersteunt Aspose.Tasks .NET Core en .NET 5/6?**  
**A:** De bibliotheek is volledig compatibel met .NET Core, .NET 5 en .NET 6.

**V: Wat moet ik doen als ik na optimalisatie nog steeds een out‑of‑memory‑fout krijg?**  
**A:** Overweeg het project te verwerken op een machine met meer RAM of de rendering uit te besteden aan een achtergrondservice.

**V: Kan ik het Gantt‑diagram exporteren naar andere formaten dan PNG?**  
**A:** Ja, `ImageSaveOptions` ondersteunt JPEG, BMP en TIFF naast PNG.

---

**Laatst bijgewerkt:** 2026-03-24  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}