---
date: 2026-03-19
description: Leer hoe u de projectbaseline kunt instellen en toewijzingsbaselines
  efficiënt kunt beheren met Aspose.Tasks voor .NET, zodat de voortgang van het project
  nauwkeurig kan worden gevolgd.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projectbaseline instellen – Toewijzingsbaseline beheren in Aspose.Tasks
url: /nl/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectbaseline instellen – Toewijzingsbaseline beheren in Aspose.Tasks

## Inleiding

Wanneer u werkt aan projectmanagementtaken, is **het instellen van een projectbaseline** essentieel om de werkelijke voortgang te meten ten opzichte van het oorspronkelijke plan. Aspose.Tasks voor .NET stelt u niet alleen in staat om **een projectbaseline in te stellen**, maar geeft u ook volledige controle over toewijzingsbaselines, waardoor nauwkeurige prestatie‑tracking mogelijk is. In deze tutorial lopen we het volledige proces door — een project laden, een baseline instellen, toewijzingsbaseline‑gegevens lezen en baselines vergelijken — zodat u uw projecten met vertrouwen kunt monitoren.

## Snelle antwoorden
- **Wat betekent “set project baseline”?** Het registreert de oorspronkelijke planning‑ en kostengegevens voor later vergelijken met de werkelijke prestaties.  
- **Welke API‑methode stelt een baseline in?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Vereisen toewijzingsbaselines een aparte aanroep?** Nee, ze worden automatisch opgeslagen wanneer u een projectbaseline instelt.  
- **Welke formaten worden ondersteund?** MPP, XML, MPX en meer via Aspose.Tasks.  
- **Is een licentie vereist voor productie?** Ja, een commerciële licentie is nodig voor niet‑trial gebruik.  

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

- Basiskennis van C#‑programmeren.  
- Visual Studio (een recente versie).  
- Aspose.Tasks voor .NET‑bibliotheek toegevoegd aan uw project. U kunt deze downloaden van [hier](https://releases.aspose.com/tasks/net/).  
- Toegang tot een projectbestand in MPP‑formaat (bijv. `AssignmentBaseline2007.mpp`).  

## Namespaces importeren

Voeg de vereiste namespaces toe aan de bovenkant van uw C#‑bestand zodat de compiler weet waar de Aspose.Tasks‑klassen te vinden zijn.

```csharp
using Aspose.Tasks;
using System;
```

## Stap 1: Project laden en projectbaseline instellen

Laad eerst het bestaande MPP‑bestand en roep vervolgens `SetBaseline` aan om **een projectbaseline in te stellen** voor het hele project.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Stap 2: Toewijzingsbaseline‑informatie lezen

Nadat de baseline is ingesteld, bevat elke resource‑toewijzing zijn eigen baseline‑records. De onderstaande lus haalt die details op en drukt ze af, inclusief start-/einddatums, kosten, werk en eventuele tijdgebaseerde gegevens.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Stap 3: Toewijzingsbaselines vergelijken

U kunt baselines van verschillende toewijzingen vergelijken met behulp van de ingebouwde gelijkheids‑ en vergelijkingsoperatoren. Dit is handig wanneer u schema‑verschuivingen of kostenoverschrijdingen tussen taken moet detecteren.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Waarom het gebeurt | Oplossing |
|----------|--------------------|-----------|
| **Baseline‑gegevens verschijnen leeg** | Het projectbestand werd geopend in alleen‑lezen‑modus of de baseline was nooit ingesteld. | Roep `project.SetBaseline(BaselineType.Baseline)` aan voordat u toewijzingsbaselines leest. |
| **`NullReferenceException` op `TimephasedData`** | Niet alle baselines bevatten tijdgebaseerde items. | Controleer altijd `baseline.TimephasedData != null` (zoals getoond in de code). |
| **Onjuiste UID‑ophaling** | UID‑waarden verschillen tussen bestandsversies. | Gebruik `ResourceAssignments.GetByUid` met de juiste UID of itereren om de benodigde toewijzing te vinden. |

## Veelgestelde vragen

**Q: Kan Aspose.Tasks meerdere baselines voor één toewijzing verwerken?**  
A: Ja, Aspose.Tasks ondersteunt meerdere baselines voor elke toewijzing, waardoor uitgebreide tracking van de projectvoortgang in de loop van de tijd mogelijk is.

**Q: Is Aspose.Tasks compatibel met verschillende projectbestandsformaten naast MPP?**  
A: Ja, Aspose.Tasks ondersteunt een breed scala aan projectbestandsformaten, waaronder XML, MPX en MPP, waardoor compatibiliteit met diverse projectmanagementtools wordt gegarandeerd.

**Q: Kan ik baseline‑informatie programmatisch wijzigen met Aspose.Tasks?**  
A: Absoluut, Aspose.Tasks biedt uitgebreide API’s om baseline‑informatie dynamisch aan te passen aan projectvereisten, waardoor flexibiliteit en controle over projectmanagementprocessen worden geboden.

**Q: Biedt Aspose.Tasks documentatie en ondersteuningsbronnen voor ontwikkelaars?**  
A: Ja, ontwikkelaars hebben toegang tot uitgebreide documentatie, tutorials en forums op de Aspose.Tasks‑website, wat een soepele integratie en probleemoplossing vergemakkelijkt.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?**  
A: Ja, ontwikkelaars kunnen een gratis proefversie van Aspose.Tasks voor .NET verkrijgen via [hier](https://releases.aspose.com/), zodat ze de functies en mogelijkheden kunnen evalueren voordat ze een aankoopbeslissing nemen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-19  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose