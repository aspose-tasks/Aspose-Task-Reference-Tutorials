---
date: 2026-04-06
description: Leer hoe u alle baselines kunt verwijderen en baseline‑collecties kunt
  beheren in Aspose.Tasks voor .NET met stapsgewijze code‑voorbeelden.
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: Alle baselines verwijderen met Aspose.Tasks Baseline Collection
second_title: Aspose.Tasks .NET API
title: Alle baselines verwijderen met Aspose.Tasks Baseline Collection
url: /nl/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alle baselines verwijderen met Aspose.Tasks Baseline Collection

## Inleiding

Aspose.Tasks for .NET stelt je in staat Microsoft Project‑bestanden rechtstreeks vanuit je .NET‑toepassingen te manipuleren. Een van de krachtigste functies is de mogelijkheid om **alle baselines verwijderen** voor een resource, wat essentieel is wanneer je de trackinggegevens van een project moet resetten of een nieuwe baseline‑periode wilt starten. In deze tutorial lopen we het volledige proces door — van het laden van een projectbestand tot het verwijderen van elke baseline die aan een specifieke resource is gekoppeld — met duidelijke, gesprekachtige uitleg en kant‑klaar C#‑code.

## Snelle antwoorden
- **Wat doet “delete all baselines”?** Het verwijdert elk opgeslagen baseline‑record voor een geselecteerde resource, waardoor historische kosten‑ en werkinformatie wordt gewist.  
- **Waarom zou ik dit nodig hebben?** Om de tracking te resetten na een grote projectwijziging of wanneer de oorspronkelijke baselines niet meer relevant zijn.  
- **Welke bibliotheek biedt deze functionaliteit?** Aspose.Tasks for .NET.  
- **Heb ik een licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar.  
- **Is de code compatibel met .NET 6+?** Ja, de API werkt met .NET Framework 4.5+, .NET Core 3.1+, en .NET 5/6.

## Wat is een baseline en waarom alle baselines verwijderen?

Een baseline legt het oorspronkelijke plan voor kosten, werk en planning vast op een specifiek moment. Gedurende de levensduur van een project kun je meerdere baselines (Baseline 1, Baseline 2, enz.) creëren om de werkelijke voortgang te vergelijken met verschillende planningsmomenten. Er zijn echter scenario's — zoals een herdefinitie van het project of een frisse start — waarbij het behouden van die historische baselines verwarrend wordt. Het verwijderen van alle baselines geeft je een schone lei, zodat je nieuwe baselines kunt instellen die de huidige realiteit weerspiegelen.

## Vereisten

1. **Visual Studio** – elke recente editie (Community, Professional of Enterprise).  
2. **Aspose.Tasks for .NET** – download het via de [download link](https://releases.aspose.com/tasks/net/).  
3. **Basis C#‑kennis** – je moet vertrouwd zijn met variabelen, lussen en console‑output.  
4. **Een Microsoft Project‑bestand** (`.mpp`) – een voorbeeldbestand genaamd *WorkWithBaselineCollection.mpp* wordt gebruikt in de voorbeelden.

## Namespaces importeren

Eerst importeer je de benodigde namespaces zodat de compiler weet waar de klassen die we gaan gebruiken zich bevinden.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Stap 1: Laad het projectbestand

We beginnen met het laden van een bestaand Project‑bestand. Pas `DataDir` aan zodat het naar de map wijst die je `.mpp`‑bestand bevat.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Stap 2: Haal de doelresource op

Voor demonstratie halen we de resource met UID = 1 op. In een echte situatie zou je de resource vinden op basis van naam of een andere identifier.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Stap 3: Toon bestaande baseline‑informatie

Voordat je iets verwijdert, is het nuttig om te zien welke baselines momenteel aan de resource zijn gekoppeld. Dit geeft je vertrouwen dat je de juiste gegevens verwijdert.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Stap 4: Doorloop alle baselines

Hier doorlopen we elke baseline en printen we belangrijke metrische gegevens zoals kosten, werk en verdiende waarde (BCWP/BCWS). Deze stap is optioneel maar nuttig voor log‑ of auditdoeleinden.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Alle baselines verwijderen

Nu voeren we de kernactie uit: **alle baselines verwijderen** voor de geselecteerde resource. We kopiëren eerst de collectie naar een lijst om te voorkomen dat we de collectie wijzigen tijdens het itereren, en verwijderen vervolgens elke baseline één voor één.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

Nadat dit blok is uitgevoerd, zal `resource.Baselines.Count` `0` zijn, wat bevestigt dat alle baseline‑records zijn gewist.

## Veelvoorkomende problemen en tips

- **NullReferenceException** – Zorg ervoor dat het projectbestand daadwerkelijk de resource bevat die je target; anders zal `GetByUid` `null` retourneren.  
- **Licensing** – Zonder een geldige Aspose.Tasks‑licentie zie je een watermerk in de output en beperkte functionaliteit.  
- **Performance** – Voor zeer grote projecten kun je overwegen te itereren met `Parallel.ForEach` om het verwijderingsproces te versnellen, maar onthoud dat de onderliggende collectie niet thread‑veilig is.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks grote projectbestanden aan?**  
A: Ja, Aspose.Tasks is geoptimaliseerd voor prestaties en kan efficiënt multi‑gigabyte `.mpp`‑bestanden verwerken.

**Q: Is de bibliotheek compatibel met alle Microsoft Project‑versies?**  
A: Aspose.Tasks ondersteunt Project 2000 tot en met Project 2024, inclusief zowel oudere `.mpp`‑formaten als de nieuwere XML‑gebaseerde bestanden.

**Q: Kan ik baselines aanpassen voordat ik ze verwijder?**  
A: Absoluut. Je kunt elke baseline‑eigenschap (kosten, werk, datums) lezen of wijzigen voordat je besluit deze te verwijderen.

**Q: Werkt Aspose.Tasks op cloudplatformen?**  
A: Ja, de API draait op elke .NET‑compatibele omgeving, inclusief Azure App Service, AWS Lambda (via .NET Core) en Docker‑containers.

**Q: Waar kan ik de community om hulp vragen?**  
A: Bezoek het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) om in contact te komen met andere ontwikkelaars en het Aspose‑team.

## Conclusie

In deze gids hebben we laten zien hoe je **alle baselines** van een resource kunt **verwijderen** met Aspose.Tasks for .NET. Door de stap‑voor‑stap code te volgen, kun je baseline‑gegevens resetten, je projecttracking schoon houden en je planning voorbereiden op een nieuwe planningscyclus. Voel je vrij om te experimenteren met het creëren van nieuwe baselines na het verwijderen om te zien hoe de bibliotheek het projectbestand bijwerkt.

---

**Laatst bijgewerkt:** 2026-04-06  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}