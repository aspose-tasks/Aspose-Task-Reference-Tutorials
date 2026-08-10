---
date: 2026-03-21
description: Leer hoe u beschikbaarheidsperioden voor resources beheert en effectieve
  projectresourcebeschikbaarheid bereikt met Aspose.Tasks voor .NET. Deze stapsgewijze
  gids laat zien hoe u beschikbaarheidsperioden kunt toevoegen, bijwerken en verwijderen.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projectresourcebeschikbaarheid – Beschikbaarheidstermijnen beheren in Aspose.Tasks
url: /nl/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectresourcebeschikbaarheid: Verzameling van Beschikbaarheidsperioden in Aspose.Tasks

Het beheren van **projectresourcebeschikbaarheid** is een essentieel onderdeel van succesvolle projectplanning. In deze tutorial leer je **hoe je beschikbaarheid** voor resources beheert met de Aspose.Tasks voor .NET API, stap voor stap, van het laden van een project tot het kopiëren van perioden tussen resources.

## Snelle Antwoorden
- **Wat is de hoofdklasse voor beschikbaarheidsperioden?** `AvailabilityPeriod` in de `Aspose.Tasks` namespace.  
- **Kan ik bestaande perioden wissen?** Ja, roep `resource.AvailabilityPeriods.Clear()` aan.  
- **Hoe voeg ik een nieuwe periode toe?** Maak een `AvailabilityPeriod` object aan en gebruik `Add` of `Insert`.  
- **Is het mogelijk om perioden naar een andere resource te kopiëren?** Absoluut – gebruik `CopyTo` en voeg vervolgens elk item toe aan de doelresource.  
- **Heb ik een licentie nodig voor productiegebruik?** Ja, een commerciële Aspose.Tasks-licentie is vereist voor niet‑trial implementaties.

## Wat is projectresourcebeschikbaarheid?
Projectresourcebeschikbaarheid definieert de data en eenheden (percentage van capaciteit) waarop een resource aan taken kan worden toegewezen. Door deze perioden te beheersen voorkom je overallocatie en verbeter je de nauwkeurigheid van het schema.

## Waarom Aspose.Tasks gebruiken om beschikbaarheidsperioden te beheren?
- **Volledige .NET-integratie** – geen COM-interoperabiliteit, pure managed code.  
- **Fijne controle** – stel exacte start/einddatums en fractionele eenheden in.  
- **Eenvoudig kopiëren** – verplaats beschikbaarheidsgegevens tussen resources zonder handmatig parseren.  
- **Prestatie‑geoptimaliseerd** – werkt efficiënt met grote MPP‑bestanden.

## Vereisten
1. **Visual Studio** – elke recente versie (2019, 2022 of later).  
2. **Aspose.Tasks for .NET** – download van [hier](https://releases.aspose.com/tasks/net/).  
3. **Basiskennis van C#** – je moet vertrouwd zijn met klassen, collecties en LINQ.

## Namespaces importeren

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

We importeren de kernnamespace Aspose.Tasks samen met standaard .NET-collecties die later nodig zijn.

## Stap 1: Initialiseer het project en de resource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Hier laden we een bestaand MPP‑bestand en halen we de resource op waarvan we de beschikbaarheid willen bewerken (ID = 1).

## Stap 2: Verwijder bestaande beschikbaarheidsperioden

```csharp
resource.AvailabilityPeriods.Clear();
```

Het wissen verwijdert alle eerder gedefinieerde perioden, waardoor we een schone lei hebben.

## Stap 3: Voeg beschikbaarheidsperioden toe

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

We halen een collectie van `AvailabilityPeriod` objecten op (de `GetPeriods`‑helper wordt verondersteld elders gedefinieerd te zijn) en voegen elk toe, waarbij we controleren of de collectie beschrijfbaar is.

## Stap 4: Voeg een nieuwe beschikbaarheidsperiode in

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Dit maakt een aangepaste periode voor het jaar 2013 aan en voegt deze in op positie 1 (tweede plek) als deze nog niet aanwezig is.

## Stap 5: Toon beschikbaarheidsperioden

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Een snelle console‑dump toont het totale aantal en de details van elke periode – handig voor debugging of verificatie.

## Stap 6: Kopieer beschikbaarheidsperioden naar een andere resource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

We kopiëren de volledige collectie naar een array, wissen de perioden van de doelresource en vullen deze vervolgens opnieuw. Dit toont hoe beschikbaarheidsgegevens over resources heen gekopieerd kunnen worden.

## Stap 7: Werk beschikbaarheidsperioden bij en verwijder ze

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Hier passen we de `AvailableUnits` aan voor de één-na-laatste periode en verwijderen vervolgens de 2013‑periode die we eerder hebben toegevoegd.

## Veelvoorkomende problemen en oplossingen
- **Read‑only collectie‑fout** – Zorg ervoor dat het project niet in read‑only‑modus is geopend of dat je `resource.AvailabilityPeriods.Clear()` hebt aangeroepen voordat je nieuwe items toevoegt.  
- **Overlap‑perioden** – Aspose.Tasks voegt overlappen niet automatisch samen; je moet mogelijk aangepaste logica schrijven om ze te detecteren en op te lossen.  
- **Onjuist datumformaat** – Gebruik altijd `DateTime` objecten; het parseren van strings kan leiden tot locale‑specifieke fouten.

## Veelgestelde vragen

**Q: Kan ik aangepaste velden toevoegen aan beschikbaarheidsperioden?**  
A: Nee, beschikbaarheidsperioden in Aspose.Tasks for .NET ondersteunen geen aangepaste velden.

**Q: Zijn beschikbaarheidsperioden gekoppeld aan specifieke taken?**  
A: Nee, ze zijn gekoppeld aan resources en definiëren wanneer de resource over het algemeen beschikbaar is voor taken.

**Q: Kan ik beschikbaarheidsperioden importeren vanuit externe bronnen?**  
A: Ja, je kunt perioden importeren vanuit CSV, XML of een database door `AvailabilityPeriod` objecten te maken en deze aan de collectie toe te voegen.

**Q: Hoe ga ik om met overlappende beschikbaarheidsperioden?**  
A: Overlappen worden niet automatisch opgelost; je moet aangepaste validatie implementeren om conflicterende perioden samen te voegen of te weigeren.

**Q: Is er een limiet aan het aantal beschikbaarheidsperioden dat een resource kan hebben?**  
A: Er is geen hard‑gecodeerde limiet, maar zeer grote collecties kunnen de prestaties beïnvloeden; overweeg waar mogelijk perioden te consolideren.

## Conclusie

In deze gids hebben we alles behandeld wat je moet weten om **projectresourcebeschikbaarheid** te beheren met Aspose.Tasks for .NET — van het initialiseren van een project en het wissen van oude gegevens, tot het toevoegen, invoegen, kopiëren, bijwerken en verwijderen van beschikbaarheidsperioden. Het beheersen van deze stappen helpt je om resource‑kalenders nauwkeurig te houden en je projectschema's realistisch.

---

**Laatst bijgewerkt:** 2026-03-21  
**Getest met:** Aspose.Tasks for .NET (latest release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}