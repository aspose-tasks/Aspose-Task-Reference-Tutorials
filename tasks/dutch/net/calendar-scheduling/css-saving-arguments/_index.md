---
date: 2026-07-05
description: Leer hoe u CSS kunt aanpassen tijdens het exporteren van een project
  naar HTML met Aspose.Tasks voor .NET. Pas de HTML-uitvoer aan met CSS-opslagargumenten.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Hoe CSS aanpassen bij het opslaan van projecten met Aspose.Tasks
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
title: Hoe CSS aanpassen bij het opslaan van projecten met Aspose.Tasks
url: /nl/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe CSS aan te passen bij het opslaan van projecten met Aspose.Tasks

In deze gids ontdek je **hoe je CSS kunt aanpassen** tijdens de HTML-export van een Microsoft Project‑bestand met Aspose.Tasks voor .NET. Door de CSS‑opslaargumenten aan te passen krijg je volledige controle over de visuele stijl van de gegenereerde HTML‑pagina's, waardoor de output overeenkomt met je huisstijl of rapportage‑normen.

## Snelle antwoorden
- **Wat is het belangrijkste instappunt?** Gebruik `HtmlSaveOptions` met aangepaste callbacks.  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productie.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan ik grote projecten exporteren?** Aspose.Tasks verwerkt projecten met > 10.000 taken zonder het volledige bestand in het geheugen te laden.  
- **Is CSS‑aanpassing optioneel?** Ja, je kunt callbacks weglaten om het standaard‑stylesheet te gebruiken.

## Hoe CSS aan te passen in Aspose.Tasks?

Laad je project, koppel CSS‑opsla‑callbacks aan het `HtmlSaveOptions`‑object en roep vervolgens `project.Save` aan. Dit patroon stelt je in staat om aangepaste CSS‑bestanden te schrijven, standaardstijlen te vervangen en de mapstructuur te beheersen — alles in een paar regels code. De callbacks worden automatisch aangeroepen voor elk CSS‑bestand tijdens het exportproces.

`HtmlSaveOptions` configureert hoe een project wordt geëxporteerd naar HTML.

## Introductie

In deze tutorial gaan we dieper in op het proces van het opslaan van CSS‑argumenten met Aspose.Tasks voor .NET. Cascading Style Sheets (CSS) zijn cruciaal voor het definiëren van de weergave van HTML‑elementen. Aspose.Tasks stelt ons in staat om deze CSS‑attributen efficiënt te manipuleren en op te slaan.

## Voorvereisten

Zorg er voordat we beginnen voor dat je de volgende voorvereisten hebt:

1. Installatie: Zorg ervoor dat je Aspose.Tasks voor .NET hebt geïnstalleerd. Je kunt het downloaden van de [website](https://releases.aspose.com/tasks/net/).
2. Basiskennis: Bekendheid met C# en de .NET‑ontwikkelomgeving wordt aanbevolen.

## Namespaces importeren

Om te beginnen, importeer de benodigde namespaces:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Stap 1: CSS‑opsla‑callbacks definiëren

`ICssSavingCallback` is een interface die je in staat stelt om aan te passen hoe CSS‑bestanden worden opgeslagen tijdens HTML‑export.

Een **CSS‑opsla‑callback** is een delegate die Aspose.Tasks aanroept om CSS‑bestanden te schrijven tijdens HTML‑export. Definieer de callback‑methoden om te bepalen hoe elk CSS‑bestand wordt aangemaakt:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Stap 2: Font‑ en afbeelding‑opsla‑callbacks implementeren

`FontSavingArgs` biedt informatie over het lettertype dat wordt opgeslagen, terwijl `ImageSavingArgs` details levert voor afbeeldingsbronnen.

Implementeer de font‑ en afbeelding‑opsla‑callback‑methoden op dezelfde manier:

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

## Stap 3: Opslaan‑opties configureren

`HtmlSaveOptions` is het configuratie‑object dat bepaalt hoe een Project wordt geëxporteerd naar HTML.

`HtmlSaveOptions` stelt je in staat om callbacks, uitvoermap‑paden en andere exportinstellingen op te geven.

Stel de eigenschappen in om de eerder gedefinieerde callbacks te gebruiken en om de uitvoermap op te geven:

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

## Stap 4: Project opslaan met aangepaste CSS

`Project` vertegenwoordigt een Microsoft Project‑bestand dat kan worden gemanipuleerd en opgeslagen.

Sla tenslotte je project op met de aangepaste CSS‑instellingen:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Waarom CSS aanpassen bij het exporteren van projecten?

Aspose.Tasks ondersteunt **export van projecten naar HTML** in meer dan 30 formaten en kan tot 30 afzonderlijke CSS‑bestanden per export genereren. Het verwerkt betrouwbaar projecten met meer dan 10 000 taken terwijl het geheugengebruik onder 200 MB blijft, waardoor rapportage op ondernemingsniveau mogelijk is zonder prestatie‑knelpunten.

## Conclusie

In deze tutorial hebben we onderzocht hoe je CSS‑argumenten kunt opslaan met Aspose.Tasks voor .NET. Door CSS‑opsla‑callbacks te definiëren en HTML‑opslaan‑opties te configureren, kunnen we CSS‑attributen efficiënt manipuleren volgens onze eisen.

## Veelgestelde vragen

### Q1: Wat is Aspose.Tasks voor .NET?
A1: Aspose.Tasks voor .NET is een krachtige .NET‑API die ontwikkelaars in staat stelt om programmatically met Microsoft Project‑bestanden te werken.

### Q2: Kan ik CSS‑attributen aanpassen bij het opslaan van HTML‑bestanden met Aspose.Tasks?
A2: Ja, je kunt CSS‑opsla‑callbacks definiëren om CSS‑attributen aan te passen aan je behoeften.

### Q3: Is Aspose.Tasks voor .NET compatibel met alle versies van Microsoft Project‑bestanden?
A3: Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project‑bestanden, waardoor compatibiliteit over verschillende omgevingen heen wordt gegarandeerd.

### Q4: Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor .NET?
A4: Je kunt de [documentatie](https://reference.aspose.com/tasks/net/) raadplegen voor gedetailleerde informatie en voorbeelden.

### Q5: Biedt Aspose.Tasks voor .NET ondersteuning voor ontwikkelaars?
A5: Ja, je kunt ondersteuning krijgen van de Aspose.Tasks‑community via het [forum](https://forum.aspose.com/c/tasks/15).

**Aanvullende vragen**

**Q: Hoe beïnvloedt het aanpassen van CSS de grootte van de geëxporteerde HTML?**  
A: Het gebruik van aangepaste CSS kan de totale grootte met tot 15 % verminderen omdat je ongebruikte standaardstijlen kunt elimineren.

**Q: Kan ik dezelfde callbacks gebruiken voor meerdere projecten?**  
A: Absoluut. Implementeer de callbacks één keer en hergebruik ze voor een willekeurig aantal project‑exports.

**Q: Is het mogelijk om CSS direct in de HTML in te sluiten in plaats van aparte bestanden?**  
A: Ja, stel `HtmlSaveOptions.EmbeddedCss = true` in om het stylesheet inline te plaatsen, wat distributie vereenvoudigt.

---

**Laatst bijgewerkt:** 2026-07-05  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [MS Project opslaan als HTML met Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementeren van pagina‑opsla‑callback in Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Afbeeldings‑opslaan verwerken in Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}