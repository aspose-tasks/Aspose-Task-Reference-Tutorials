---
date: 2026-03-21
description: Leer hoe u een afbeelding kunt exporteren en de BitmapInvalidSizeException
  kunt afhandelen bij het opslaan van een project als afbeelding in Aspose.Tasks voor .NET.
  Inclusief stappen om een project als afbeelding op te slaan en het project naar
  PNG te exporteren.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe een afbeelding te exporteren en een ongeldige grootte‑exception af te handelen
url: /nl/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een afbeelding exporteren – Afhandelen van de Invalid Size Exception voor Bitmap in Aspose.Tasks

In deze tutorial leer je **hoe je een afbeelding exporteert** vanuit een Microsoft Project‑bestand met Aspose.Tasks voor .NET en, nog belangrijker, hoe je de `BitmapInvalidSizeException` opvangt die tijdens het proces kan optreden. Het exporteren van een project als afbeelding is een veelvoorkomende eis voor rapportagedashboards, documentatie of simpelweg het delen van een visueel momentopname van een planning. Aan het einde van deze gids kun je **een project opslaan als afbeelding** op een betrouwbare manier en zelfs **een project exporteren naar PNG**‑formaat zonder onverwachte crashes.

## Snelle antwoorden
- **Welke uitzondering kan optreden bij het exporteren van een afbeelding?** `BitmapInvalidSizeException`  
- **Welk formaat wordt in het voorbeeld gebruikt?** PNG (`SaveFileFormat.Png`)  
- **Heb ik een speciale licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Kan ik de tijdschaal wijzigen?** Ja – je kunt de tijdschaaleenheid (minuten, uren, dagen, enz.) instellen.  
- **Is de code compatibel met .NET Core?** Absoluut – dezelfde API werkt op .NET Framework en .NET Core.

## Wat is de BitmapInvalidSizeException?
`BitmapInvalidSizeException` wordt gegooid wanneer de bitmap‑afmetingen die voor de afbeelding zijn berekend buiten het ondersteunde bereik vallen (bijv. breedte of hoogte is nul of overschrijdt interne limieten). Dit gebeurt meestal wanneer de tijdschaal‑ of weergave‑instellingen een afbeelding produceren die te groot of te klein is.

## Waarom een project exporteren als afbeelding?
- **Visuele rapportage** – embed een Gantt‑diagram in PDF‑s, Word‑doc‑s of webpagina’s.  
- **Cross‑platform delen** – PNG‑bestanden kunnen op elk apparaat worden bekeken zonder Microsoft Project.  
- **Prestaties** – afbeeldingen zijn lichter dan volledige projectbestanden voor snelle previews.

## Vereisten
1. Basiskennis van C# en .NET‑ontwikkeling.  
2. Aspose.Tasks voor .NET geïnstalleerd (NuGet‑pakket `Aspose.Tasks`).  
3. Een voorbeeld‑Microsoft Project‑bestand (bijv. `Blank2010.mpp`).  

## Namespaces importeren
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Stapsgewijze handleiding

### Stap 1: Initialiseert het project en kies een weergave
Maak eerst een `Project`‑instantie en selecteer de weergave die je wilt renderen (hier gebruiken we de eerste Gantt‑chart‑weergave).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Stap 2: Configureer de afbeeldingsopties (Export Project to PNG)
Stel het gewenste afbeeldingsformaat in en vertel Aspose.Tasks de tijdschaal te gebruiken die in de weergave is gedefinieerd.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Stap 3: Pas de tijdschaaleenheid aan (Beheer afbeeldingsgrootte)
Het wijzigen van de tijdschaal beïnvloedt de bitmap‑afmetingen. In dit voorbeeld gebruiken we **minuten** om de afbeeldingsgrootte beheersbaar te houden.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Stap 4: Probeer het project op te slaan als afbeelding
Deze regel voert de daadwerkelijke **save project as image**‑operatie uit.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Stap 5: Vang de BitmapInvalidSizeException op en verwerk deze
Omhul de opslaan‑aanroep met een `try / catch`‑blok zodat je applicatie netjes kan reageren als de bitmap‑grootte ongeldig is.

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

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Exception nog steeds gegooid na aanpassen van tijdschaal | Tijdschaal resulteert nog steeds in een te grote bitmap | Verminder `view.MiddleTimescaleTier.Count` of schakel over naar een grovere `TimescaleUnit` (bijv. Hours). |
| Uitvoerbestand is leeg | Onjuist bestandspad of ontbrekende schrijfrechten | Controleer of `DataDir` naar een schrijfbare map wijst en of de bestandsnaam eindigt op `.png` wanneer je het formaat wijzigt. |
| Beeldkwaliteit is slecht | Standaard DPI kan laag zijn | Stel `options.DpiX` en `options.DpiY` in op hogere waarden (bijv. 300). |

## Veelgestelde vragen

**Q: Wat veroorzaakt de BitmapInvalidSizeException in Aspose.Tasks?**  
A: Deze treedt op wanneer de berekende bitmap‑afmetingen ongeldig zijn — meestal omdat de tijdschaal een afbeelding oplevert die te groot is of een breedte/hoogte van nul heeft.

**Q: Kan ik de tijdschaal aanpassen bij het exporteren van een afbeelding?**  
A: Ja. Je kunt `view.MiddleTimescaleTier.Unit` en `Count` aanpassen naar eigen wens, zoals in de tutorial wordt getoond.

**Q: Ondersteunt Aspose.Tasks andere afbeeldingsformaten naast PNG?**  
A: Absoluut. `SaveFileFormat` bevat ook JPEG, BMP, GIF en TIFF. Wijzig gewoon de enum‑waarde in `ImageSaveOptions`.

**Q: Is een licentie vereist voor het exporteren van afbeeldingen in een productie‑omgeving?**  
A: Ja. Hoewel de bibliotheek in evaluatiemodus werkt, verwijdert een commerciële licentie de evaluatiebeperkingen en biedt volledige ondersteuning.

**Q: Hoe kan ik de kwaliteit van de geëxporteerde PNG verbeteren?**  
A: Verhoog de DPI‑instellingen (`options.DpiX` en `options.DpiY`) of pas de tijdschaal van de weergave aan om een grotere bitmap te produceren.

## Conclusie
Door de bovenstaande stappen te volgen weet je nu **hoe je een afbeelding exporteert** vanuit een Project‑bestand, hoe je **een project opslaat als afbeelding**, en hoe je de `BitmapInvalidSizeException` op een nette manier afhandelt. Deze technieken maken je rapportage‑pijplijnen robuuster en zorgen ervoor dat visuele exports betrouwbaar werken voor verschillende projectgroottes en tijdschalen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-21  
**Getest met:** Aspose.Tasks 24.12 voor .NET  
**Auteur:** Aspose  

---