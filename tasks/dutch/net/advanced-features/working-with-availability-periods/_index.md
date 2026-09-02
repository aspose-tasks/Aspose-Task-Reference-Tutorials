---
date: 2026-04-06
description: Leer hoe u een resource aan een project toevoegt en de beschikbaarheidsperioden
  van de resource instelt met Aspose.Tasks voor .NET. Stapsgewijze handleiding voor
  het beheren van resource‑kalenders.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Werken met beschikbaarheidsperioden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Resource toevoegen aan project en beschikbaarheid instellen in Aspose.Tasks
url: /nl/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Resource toevoegen aan project en beschikbaarheid instellen in Aspose.Tasks

## Inleiding

In deze tutorial leer je **hoe je een resource aan een project toevoegt** en vervolgens de beschikbaarheidsperioden definieert met behulp van de Aspose.Tasks .NET-bibliotheek. Het beheren van resource‑kalenders is essentieel voor realistische projectschema's, en de onderstaande stappen begeleiden je door het volledige proces—van het maken van een project‑instantie tot het afdrukken van de details van elke periode.

## Snelle antwoorden
- **Wat is het hoofddoel?** Om een resource aan een project toe te voegen en de beschikbaarheidsperioden te configureren.  
- **Welke bibliotheek is vereist?** Aspose.Tasks for .NET.  
- **Heb ik een licentie nodig voor productie?** Ja, een commerciële licentie is vereist.  
- **Ondersteunde .NET‑versies?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementatietijd?** Meestal minder dan 15 minuten voor basiscenario's.

## Wat is “resource toevoegen aan project”?

Het toevoegen van een resource aan een project creëert een placeholder voor een persoon, uitrusting of materiaal die aan taken kan worden toegewezen. Zodra de resource bestaat, kun je **resource beschikbaarheid instellen**, de werk‑kalender definiëren, en de planner deze beperkingen laten respecteren.

## Waarom werkrooster en beschikbaarheidsperioden configureren?

- **Nauwkeurige planning:** Taken worden alleen ingepland wanneer de resource daadwerkelijk beschikbaar is.  
- **Kostenbeheersing:** Beschikbaarheidseenheden weerspiegelen deeltijdse inspanning, waardoor je arbeidskosten correct kunt berekenen.  
- **Resource‑leveling:** De engine kan automatisch over‑allocaties egaliseren wanneer hij de kalender van elke resource kent.

## Voorvereisten

1. Visual Studio (of een IDE die .NET‑compatibel is).  
2. Aspose.Tasks for .NET – download van [hier](https://releases.aspose.com/tasks/net/).  
3. Basiskennis van C#.

## Namespaces importeren

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Hoe een resource aan een project toevoegen?

### Stap 1: Maak een nieuwe `Project`‑instantie

```csharp
var project = new Project();
```

Dit object vertegenwoordigt het volledige projectbestand in het geheugen.

### Stap 2: Voeg een resource toe aan het project

```csharp
var resource = project.Resources.Add("Work Resource");
```

De aanroep maakt een **resource** aan met de naam *Work Resource* die je later aan taken kunt koppelen.

### Stap 3: Definieer beschikbaarheidsperioden

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` is een hulpmethode (implementatie niet getoond) die een collectie van `AvailabilityPeriod`‑objecten retourneert. Elke periode specificeert een startdatum, een einddatum en de eenheden (percentage van voltijdsinspanning) waarin de resource beschikbaar is.

### Stap 4: Voeg de perioden toe aan de resource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Hier **stellen we de resource‑beschikbaarheid in** door door de collectie te itereren en elke periode toe te voegen aan de kalender van de resource.

### Stap 5: Toon de beschikbaarheidsdetails

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

De console‑output laat je verifiëren dat de perioden correct zijn opgeslagen.

## Veelvoorkomende valkuilen & tips

- **Datumprecisie:** `AvailableFrom` en `AvailableTo` zijn `DateTime`‑waarden; zorg ervoor dat ze op middernacht zijn ingesteld als je volledige‑dag perioden wilt.  
- **Eenhedenbereik:** Geldige waarden zijn 0‑100 %; waarden buiten dit bereik zullen een uitzondering veroorzaken.  
- **Overlapende perioden:** Overlapende perioden worden automatisch samengevoegd, maar het is duidelijker om ze gescheiden te houden.

## Veelgestelde vragen

### Q1: Kan ik Aspose.Tasks for .NET gebruiken in commerciële projecten?
A1: Ja, Aspose.Tasks for .NET kan worden gebruikt in commerciële projecten. Je kunt een licentie aanschaffen [hier](https://purchase.aspose.com/buy).

### Q2: Is er een gratis proefversie beschikbaar voor Aspose.Tasks for .NET?
A2: Ja, je kunt een gratis proefversie van Aspose.Tasks for .NET verkrijgen [hier](https://releases.aspose.com/).

### Q3: Waar kan ik de documentatie voor Aspose.Tasks for .NET vinden?
A3: Je kunt de documentatie vinden [hier](https://reference.aspose.com/tasks/net/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks for .NET?
A4: Je kunt ondersteuning krijgen via het community‑forum [hier](https://forum.aspose.com/c/tasks/15).

### Q5: Biedt u tijdelijke licenties aan voor Aspose.Tasks for .NET?
A5: Ja, tijdelijke licenties zijn beschikbaar [hier](https://purchase.aspose.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-04-06  
**Getest met:** Aspose.Tasks for .NET (latest stable release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}