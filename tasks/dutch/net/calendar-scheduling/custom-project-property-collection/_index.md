---
date: 2026-10-15
description: Leer hoe u een aangepaste eigenschap kunt toevoegen en aangepaste projecteigenschappen
  kunt beheren in Aspose.Tasks voor .NET, waardoor u meer controle krijgt over de
  projectmetadata.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Beheren van de collectie aangepaste projecteigenschappen in Aspose.Tasks
og_description: Voeg een aangepaste eigenschap toe aan uw projectbestanden met Aspose.Tasks
  voor .NET. Deze gids laat zien hoe u aangepaste eigenschappen beheert, ze uitleest
  en efficiënt booleaanse of tekenreekswaarden toevoegt.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Aangepaste eigenschap toevoegen met de Aspose.Tasks .NET API voor projecten
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Hoe een aangepaste eigenschap toe te voegen in Aspose.Tasks voor .NET
url: /nl/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een aangepaste eigenschap toe te voegen in Aspose.Tasks voor .NET

## Introductie

Ondersteuning voor aangepaste eigenschap laat u project‑specifieke metadata opslaan die de ingebouwde velden niet dekken. In deze tutorial leert u hoe u een **aangepaste eigenschap** kunt toevoegen, deze kunt uitlezen, en de volledige collectie van aangepaste eigenschappen kunt beheren met Aspose.Tasks voor .NET. Aan het einde kunt u projectbestanden aanpassen met Boolean-, DateTime-, Double- en String‑waarden die passen bij uw bedrijfsregels.

## Snelle antwoorden
- **Kan ik een Boolean‑aangepaste eigenschap toevoegen?** Ja – gebruik `CustomPropertyType.Boolean`.
- **Hoeveel aangepaste eigenschaptypen worden ondersteund?** Vier: Boolean, DateTime, Double, String.
- **Is de collectie van aangepaste eigenschappen alleen‑lezen?** Deze kan alleen‑lezen zijn als het project wordt geladen vanuit een alleen‑lezen bron.
- **Heb ik een licentie nodig om deze functie te gebruiken?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productie.
- **Welke .NET‑versies zijn compatibel?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Wat is een aangepaste eigenschap?

Een aangepaste eigenschap is een door de gebruiker gedefinieerd metadata‑veld dat u aan een Project‑object koppelt. Het stelt u in staat extra informatie op te slaan, zoals “Risiconiveau”, “Klant‑ID”, of een Boolean‑vlag die niet wordt gedekt door de standaard MS‑Project‑velden.

## Waarom een aangepaste eigenschap toevoegen in Aspose.Tasks?

Aspose.Tasks ondersteunt **meer dan 50 invoer‑ en uitvoerformaten** en kan projecten met **tot 10.000 taken** verwerken zonder het volledige bestand in het geheugen te laden. Het toevoegen van aangepaste eigenschappen stelt u in staat bedrijfs‑kritieke gegevens direct in het projectbestand te embedden, waardoor externe databases overbodig worden en de gegevens met het project meereizen.

## Vereisten

- Visual Studio (een recente editie) geïnstalleerd op uw werkstation.  
- Aspose.Tasks for .NET – download het van de [download link](https://releases.aspose.com/tasks/net/).  
- Basiskennis van C#‑syntaxis en .NET‑projectstructuur.

## Importeren van namespaces

De volgende namespaces geven u toegang tot het kernprojectmodel en de API’s voor aangepaste eigenschappen.

```csharp
using Aspose.Tasks;
using System;


```

## Hoe een aangepaste eigenschap toe te voegen in Aspose.Tasks?

Om een aangepaste eigenschap toe te voegen, laadt u eerst het project, maakt u vervolgens een `CustomProperty`‑object, stelt u de naam, het type en de waarde in, en voegt u het uiteindelijk toe aan de `CustomProperties`‑collectie van het project. Deze bewerking embedt de metadata direct in het projectbestand, en de wijzigingen worden opgeslagen wanneer u `project.Save(...)` aanroept.  

`CustomProperty` vertegenwoordigt een enkel door de gebruiker gedefinieerd veld dat aan een project is gekoppeld.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Stap 1: project initialiseren

`Project` is de primaire klasse die een projectbestand vertegenwoordigt in Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Stap 2: controleer of de collectie van aangepaste eigenschappen klaar is

`CustomProperties` is de collectie die alle aangepaste eigenschapsobjecten voor een project bevat.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Stap 3: aangepaste eigenschappen toevoegen

De `Add`‑methode voegt een nieuwe aangepaste eigenschap toe aan de collectie van het project.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Stap 4: toegang tot aangepaste eigenschappen

De `CustomProperties`‑collectie implementeert IEnumerable, waardoor iteratie over elke `CustomProperty` mogelijk is.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Stap 5: een aangepaste eigenschapwaarde ophalen

De `Get`‑methode retourneert de waarde van een aangepaste eigenschap op basis van de naam.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Stap 6: itereren over namen van aangepaste eigenschappen

De `Names`‑eigenschap biedt een lijst van alle namen van aangepaste eigenschappen in de collectie.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Stap 7: aangepaste eigenschappen verwijderen of wissen

De `Remove`‑methode verwijdert een specifieke eigenschap, terwijl `Clear` de gehele collectie leegt.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Veelvoorkomende valkuilen en probleemoplossing

- **Alleen‑lezen collectie** – Als `project.CustomProperties.IsReadOnly` `true` retourneert, zorg er dan voor dat het bronbestand niet met exclusieve lees‑toegang is geopend of kopieer het naar een schrijfbare locatie voordat u bewerkt.  
- **Type‑mismatch** – Het toewijzen van een waarde die niet overeenkomt met het gedeclareerde `CustomPropertyType` veroorzaakt een `ArgumentException`. Stel altijd de `Value` in nadat u het juiste `Type` hebt gedefinieerd.  
- **Wijzigingen opslaan** – Na het toevoegen of verwijderen van eigenschappen, roep `project.Save("output.mpp")` aan om de wijzigingen permanent op te slaan; anders blijven de wijzigingen alleen in het geheugen.

## Veelgestelde vragen

**Q: Kan ik aangepaste eigenschappen van elk gegevenstype toevoegen aan mijn project met Aspose.Tasks voor .NET?**  
A: Ja, u kunt aangepaste eigenschappen toevoegen die Boolean-, DateTime-, Double- en String‑typen ondersteunen.

**Q: Is het mogelijk om te itereren over namen van aangepaste eigenschappen in Aspose.Tasks voor .NET?**  
A: Absoluut, u kunt itereren over namen van aangepaste eigenschappen met behulp van de `Names`‑eigenschap.

**Q: Hoe kan ik een specifieke aangepaste eigenschap uit mijn project verwijderen?**  
A: U kunt een aangepaste eigenschap verwijderen op basis van de naam met de `Remove`‑methode.

**Q: Biedt Aspose.Tasks voor .NET ondersteuning voor tijdelijke licenties?**  
A: Ja, u kunt een tijdelijke licentie verkrijgen van de Aspose‑website voor evaluatiedoeleinden.

**Q: Waar kan ik ondersteuning of verdere hulp vinden met betrekking tot Aspose.Tasks voor .NET?**  
A: U kunt het Aspose.Tasks‑forum bezoeken [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) voor vragen of assistentie.

---

**Laatst bijgewerkt:** 2026-10-15  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe ingebouwde projecteigenschappen lezen met Aspose.Tasks voor .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Beheer MS Project‑attribuutencollectie in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks aangepaste veldtypen – Kalender en planning](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}