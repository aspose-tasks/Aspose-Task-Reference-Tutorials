---
date: 2026-03-05
description: Leer hoe u afbeeldingen opslaat, HTML met afbeeldingen genereert en de
  afbeeldingsexport aanpast met Aspose.Tasks voor .NET. Stapsgewijze handleiding om
  een project op te slaan als HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Hoe afbeeldingen opslaan met Aspose.Tasks voor .NET
url: /nl/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe afbeeldingen opslaan met Aspose.Tasks voor .NET

## Inleiding

In deze tutorial ontdek je **hoe je afbeeldingen** kunt opslaan vanuit Microsoft Project‑bestanden met de Aspose.Tasks‑API voor .NET. Of je nu grafieken in rapporten wilt insluiten, HTML‑pagina's wilt genereren die projectvisualisaties bevatten, of simpelweg diagrammen wilt exporteren, de onderstaande stappen begeleiden je door het volledige proces — van het instellen van het projectobject tot het aanpassen van de afbeelding‑export‑callbacks.

## Snelle antwoorden
- **Wat betekent “hoe afbeeldingen opslaan” in Aspose.Tasks?**  
  Het verwijst naar het gebruik van de `IImageSavingCallback`‑interface om te bepalen waar en hoe visuele bronnen naar schijf worden geschreven.
- **Kan ik een project opslaan als HTML met ingesloten afbeeldingen?**  
  Ja, door `HtmlSaveOptions` te gebruiken in combinatie met afbeelding‑opslaancallbacks kun je **project opslaan als HTML** dat alle gegenereerde afbeeldingen bevat.
- **Heb ik een licentie nodig voor afbeeldingsexport?**  
  Een tijdelijke evaluatielicentie werkt voor testen; een volledige licentie is vereist voor productiegebruik.
- **Welke .NET‑versies worden ondersteund?**  
  Aspose.Tasks voor .NET ondersteunt .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6+.
- **Is het mogelijk om afbeeldingsexport aan te passen (formaat, map, naamgeving)?**  
  Absoluut — de callback geeft je volledige controle over bestandsnaam, formaat en bestemming.

## Wat betekent “hoe afbeeldingen opslaan” in de context van Aspose.Tasks?
Afbeeldingen opslaan betekent het extraheren van visuele elementen (grafieken, Gantt‑balken, resource‑graphics) uit een Project‑bestand en deze wegschrijven naar afbeeldingsbestanden (PNG, JPEG, enz.). Aspose.Tasks biedt een flexibel callback‑mechanisme waarmee je de exacte locatie, naamgevingsconventie en zelfs het afbeeldingsformaat kunt bepalen.

## Waarom Aspose.Tasks gebruiken om afbeeldingen op te slaan?
- **Volledige programmatiche controle** – geen handmatige UI‑interactie nodig.  
- **Cross‑platform** – werkt op Windows, Linux en macOS via .NET Core.  
- **Hoge‑fidelity rendering** – afbeeldingen behouden dezelfde kwaliteit als de oorspronkelijke Project‑weergave.  
- **Eenvoudige HTML‑generatie** – combineer `HtmlSaveOptions` met afbeelding‑callbacks om **automatisch HTML met afbeeldingen** te genereren.

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

1. Visual Studio geïnstalleerd op je ontwikkelmachine.  
2. Aspose.Tasks voor .NET gedownload van [hier](https://releases.aspose.com/tasks/net/).  
3. Basiskennis van C# en .NET‑projectstructuur.

## Namespaces importeren

Breng eerst de benodigde namespaces in je bronbestand:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Stap 1: Een Project‑object maken

Laad het Microsoft Project‑bestand dat je wilt gebruiken:

```csharp
var project = new Project("Project1.mpp");
```

## Stap 2: Opslagopties definiëren

Maak de HTML‑opslaan‑opties aan die ook onze afbeelding‑opslaancallbacks bevatten:

```csharp
var options = GetSaveOptions(1);
```

## Stap 3: Het project opslaan als HTML (save project as html)

Exporteer nu het project naar een HTML‑bestand. De afbeeldingen die in de HTML worden verwezen, worden gegenereerd door de callback die we vervolgens definiëren:

```csharp
project.Save("document_out.html", options);
```

## Stap 4: Afbeelding‑opslaan‑callback implementeren (customize image export)

Implementeer de `IImageSavingCallback`‑interface. Hier kun je het gedrag van **afbeeldingsexport aanpassen**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Stap 5: Afbeeldingen opslaan in opgegeven map

Binnen de `ImageSaving`‑methode bepaal je waar elke afbeelding moet worden opgeslagen. Het voorbeeld hieronder onderscheidt PNG‑bronnen van andere formaten:

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

## Stap 6: Opslaan‑opties specificeren (inclusief callbacks)

Koppel de callbacks voor lettertypen, CSS en afbeeldingen. Dit zorgt ervoor dat elk visueel element consistent wordt afgehandeld:

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

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Afbeeldingen verschijnen niet in de gegenereerde HTML | Callback wijst geen geldig bestandspad toe | Zorg ervoor dat `args.Path` naar een schrijfbare map wijst en stel `args.ImageStream` correct in. |
| PNG‑bestanden worden opgeslagen met verkeerde extensie | Voorwaardelijke logica controleert alleen op “png” suffix | Gebruik `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` voor robuuste detectie. |
| HTML‑verwijzingen zijn kapot na het verplaatsen van bestanden | Relatieve paden veranderden na het verplaatsen van de output‑map | Houd de HTML‑ en afbeeldingsmappen samen of werk `options.ImageFolder` dienovereenkomstig bij. |

## Conclusie

Door deze stappen te volgen weet je nu **hoe je afbeeldingen kunt opslaan** uit een Project‑bestand, **hoe je project opslaat als HTML**, en **hoe je afbeeldingsexport kunt aanpassen** aan de mapstructuur van je applicatie. Deze aanpak stelt je in staat om **HTML met afbeeldingen** te genereren die naadloos kunnen worden ingebed in rapporten, documentatie‑portalen of web‑dashboards.

## Veelgestelde vragen

**Q1: Kan ik Aspose.Tasks gebruiken om projectbestanden in andere formaten dan HTML te manipuleren?**  
A1: Ja, Aspose.Tasks ondersteunt verschillende formaten zoals PDF, XLSX en MPP.

**Q2: Biedt Aspose.Tasks ondersteuning voor integratie met cloudopslag?**  
A2: Ja, Aspose.Tasks biedt API’s voor het werken met populaire cloudopslagdiensten zoals Amazon S3 en Google Drive.

**Q3: Is Aspose.Tasks compatibel met .NET Core?**  
A3: Ja, Aspose.Tasks is compatibel met .NET Core, waardoor je cross‑platform applicaties kunt ontwikkelen.

**Q4: Kan ik het uiterlijk van opgeslagen afbeeldingen aanpassen?**  
A4: Ja, je kunt het uiterlijk van opgeslagen afbeeldingen aanpassen door de logica voor afbeelding opslaan binnen de callback‑methoden te wijzigen.

**Q5: Biedt Aspose.Tasks proefversies voor evaluatiedoeleinden?**  
A5: Ja, je kunt een gratis proefversie van Aspose.Tasks verkrijgen via [hier](https://releases.aspose.com/).

---

**Laatst bijgewerkt:** 2026-03-05  
**Getest met:** Aspose.Tasks 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}