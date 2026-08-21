---
date: 2026-03-19
description: Leer hoe u meerdere aangepaste kolommen kunt toevoegen en de breedte
  van aangepaste kolommen kunt formatteren bij het exporteren van een project naar
  XML met Aspose.Tasks voor .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Meerdere aangepaste kolommen toevoegen aan de toewijzingsweergave in Aspose.Tasks
url: /nl/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg meerdere aangepaste kolommen toe aan de toewijzingsweergave in Aspose.Tasks

## Introductie

In deze tutorial ontdek je **hoe je meerdere aangepaste kolommen** kunt toevoegen aan een toewijzingsweergave met Aspose.Tasks voor .NET. Aangepaste kolommen stellen je in staat extra gegevens—zoals notities, kosten of aangepaste vlaggen—direct in geëxporteerde rapporten weer te geven. Aan het einde van de gids kun je de breedte van aangepaste kolommen formatteren, het project exporteren naar XML en de weergave afstemmen op je project‑managementbehoeften.

## Snelle antwoorden
- **Wat kan ik bereiken?** Toon elke toewijzingsdata in aangepaste kolommen en beheer hun weergave.  
- **Welk formaat ondersteunt dit?** Exporteer het project naar XML (of andere formaten) met `Spreadsheet2003SaveOptions`.  
- **Heb ik een licentie nodig?** Ja, een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.  
- **Welke .NET‑versies werken?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hoeveel kolommen kan ik toevoegen?** Onbeperkt – maak gewoon extra `AssignmentViewColumn`‑instanties aan.

## Wat zijn meerdere aangepaste kolommen?
Meerdere aangepaste kolommen zijn door de gebruiker gedefinieerde velden die naast de standaard toewijzingskolommen verschijnen wanneer een project wordt opgeslagen of geëxporteerd. Ze geven je de flexibiliteit om elke eigenschap van een `ResourceAssignment`‑object weer te geven, zoals aangepaste notities, kostencodes of berekende waarden.

## Waarom meerdere aangepaste kolommen toevoegen aan de toewijzingsweergave?
- **Verbeterde rapportage:** Voeg projectspecifieke informatie toe die niet wordt gedekt door de ingebouwde kolommen.  
- **Betere besluitvorming:** Stakeholders kunnen de exacte gegevens zien die ze nodig hebben zonder in ruwe bestanden te graven.  
- **Consistente opmaak:** Beheer de kolombreedte en tekstconversie voor een nette, leesbare output.  

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

1. Basiskennis van de programmeertaal C#.  
2. Aspose.Tasks for .NET‑bibliotheek geïnstalleerd. Zo niet, download deze **[hier](https://releases.aspose.com/tasks/net/)**.  
3. Een geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio.  

## Stapsgewijze handleiding

### Stap 1: Namespaces importeren
Importeer eerst de namespaces die de klassen leveren die we nodig hebben voor het werken met projecten en visualisaties.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Stap 2: Het project laden
Maak een `Project`‑instantie aan en laad een bestaand MPP‑bestand.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Stap 3: Spreadsheet‑opslaanopties maken
Instantieer `Spreadsheet2003SaveOptions` – dit object stelt ons in staat de toewijzingsweergave aan te passen vóór het exporteren.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Stap 4: Aangepaste kolom definiëren
Maak een `AssignmentViewColumn` voor elk gegeven dat je wilt weergeven. Hieronder voegen we een **Notes**‑kolom toe met een breedte van 200 punten.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** Om *meerdere* aangepaste kolommen toe te voegen, herhaal deze stap met verschillende veldnamen en delegate‑logica, en voeg vervolgens elke instantie toe aan `options.AssignmentView.Columns`.

### Stap 5: Aangepaste kolom toevoegen aan opties
Voeg de kolom (of kolommen) toe aan de `Columns`‑collectie van de toewijzingsweergave.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Stap 6: Door toewijzingen itereren (optioneel debuggen)
Je kunt door de toewijzingen lopen om te verifiëren dat de tekst van de aangepaste kolom correct wordt gegenereerd.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Stap 7: Het project opslaan met aangepaste kolommen
Sla tenslotte het project op. Het voorbeeld slaat op als XML, maar je kunt elk ondersteund formaat kiezen.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Hoe exporteer je een project naar XML met aangepaste kolommen?
Wanneer je `project.Save` aanroept met de geconfigureerde `Spreadsheet2003SaveOptions`, schrijft Aspose.Tasks de projectgegevens — inclusief alle **meerdere aangepaste kolommen** — naar het gekozen XML‑bestand. Dit maakt het eenvoudig om verrijkte projectinformatie te delen met andere systemen of belanghebbenden.

## Formatteer de breedte van aangepaste kolommen voor betere leesbaarheid
De tweede parameter van de `AssignmentViewColumn`‑constructor bepaalt de kolombreedte (gemeten in punten). Pas deze waarde aan op basis van de hoeveelheid tekst die je verwacht. Bijvoorbeeld, een breedte van **300** werkt goed voor langere notities, terwijl **100** voldoende is voor korte vlaggen.

## Veelvoorkomende problemen en oplossingen
- **Kolomtekst verschijnt leeg:** Zorg ervoor dat de delegate een string retourneert en dat de onderliggende toewijzings‑eigenschap (bijv. `Asn.NotesText`) is gevuld.  
- **Kolommen zijn niet zichtbaar in het geëxporteerde bestand:** Controleer dat `options.AssignmentView.Columns` je aangepaste kolommen bevat voordat je `Save` aanroept.  
- **Breedte lijkt genegeerd:** Sommige exportformaten hebben hun eigen layoutrichtlijnen; XML respecteert de breedte, maar PDF/HTML kunnen extra styling vereisen.

## Veelgestelde vragen

### Q1: Kan ik meerdere aangepaste kolommen toevoegen aan de toewijzingsweergave?
**A:** Ja, maak eenvoudig extra `AssignmentViewColumn`‑objecten aan en voeg elk toe aan `options.AssignmentView.Columns`.

### Q2: Zijn er vooraf gedefinieerde converters beschikbaar voor veelvoorkomende toewijzingsvelden?
**A:** Ja, Aspose.Tasks biedt ingebouwde converters voor veel standaardvelden, waardoor je gegevens kunt ophalen zonder eigen delegates te schrijven.

### Q3: Kan ik het uiterlijk van aangepaste kolommen aanpassen, zoals tekst opmaken of stijlen toepassen?
**A:** Absoluut. Naast het instellen van de breedte kun je lettertype, uitlijning en andere visuele eigenschappen wijzigen via de stijlopties van de kolom.

### Q4: Is het mogelijk om standaardkolommen uit de toewijzingsweergave te verwijderen?
**A:** Je kunt standaardkolommen uitsluiten door ze uit de `Columns`‑collectie te verwijderen of hun breedte op nul te zetten.

### Q5: Ondersteunt Aspose.Tasks het exporteren van projecten naar andere formaten naast spreadsheets met aangepaste kolommen?
**A:** Ja, Aspose.Tasks kan exporteren naar PDF, HTML, XML en vele andere formaten terwijl de definities van aangepaste kolommen behouden blijven.

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}