---
date: 2026-03-19
description: Leer hoe u een resource aan een project toevoegt, de taakduur berekent
  met het Tree‑algoritme van Aspose.Tasks en resources aan taken toewijst in .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Resource toevoegen aan project met boomalgoritme in Aspose.Tasks
url: /nl/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Resource toevoegen aan project met boomalgoritme in Aspose.Tasks

## Introductie

In deze tutorial ontdek je **hoe je een resource aan een project toevoegt** door gebruik te maken van het krachtige boomalgoritme dat wordt geleverd door Aspose.Tasks voor .NET. We lopen stap voor stap door het maken van een taakhiërarchie, het berekenen van de taakduur en het toewijzen van resources aan taken — allemaal op een duidelijke manier die je kunt kopiëren naar je eigen oplossing.

## Snelle antwoorden
- **Wat doet het boomalgoritme?** Het doorloopt een taakhiërarchie om werkwaarden efficiënt te aggregeren.  
- **Welke primaire bewerking behandelt deze gids?** Het toevoegen van een resource aan een project en het bijwerken van de werktotalen.  
- **Heb ik een licentie nodig?** Een tijdelijke of volledige licentie is vereist voor productiegebruik.  
- **Kan ik dit gebruiken met .NET Core?** Ja, Aspose.Tasks ondersteunt .NET Framework en .NET Core.  
- **Hoe lang duurt de implementatie?** Ongeveer 10‑15 minuten voor een basis projectbestand.

## Wat betekent “resource toevoegen aan project” in Aspose.Tasks?

Een resource aan een project toevoegen betekent het aanmaken van een `Resource`‑object, het definiëren van het type (bijv. werk), en het koppelen ervan aan één of meer taken via `ResourceAssignments`. Dit stelt de planner in staat om inspanning, kosten en de totale projectduur te berekenen.

## Waarom het boomalgoritme gebruiken voor berekeningen van resource‑werk?

Het boomalgoritme doorloopt de takenboom één keer en verzamelt werk van de bladtaken tot hun samenvattende taken. Deze aanpak is veel efficiënter dan het itereren over elke taak afzonderlijk, vooral in grote projecten met diepe hiërarchieën. Het garandeert ook dat samenvattende werkwaarden synchroon blijven met hun onderliggende taken.

## Vereisten

1. **Visual Studio** – elke recente editie (2019, 2022 of later).  
2. **Aspose.Tasks for .NET** – download het vanaf [hier](https://releases.aspose.com/tasks/net/).  
3. **Basis C#-kennis** – je moet vertrouwd zijn met klassen, objecten en eenvoudige LINQ.

## Namespaces importeren

In je C#‑project importeer je de benodigde namespaces om met Aspose.Tasks‑functionaliteiten te werken:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Laten we nu elk voorbeeld in meerdere stappen opsplitsen:

## Stap 1: Projectbestand laden

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Laad het projectbestand in het geheugen met behulp van de `Project`‑klasse.

## Stap 2: Taakhiërarchie definiëren

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definieer de taakhiërarchie door bovenliggende en onderliggende taken toe te voegen.

## Stap 3: Taakeigenschappen instellen (inclusief **taakduur berekenen**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Hier **berekenen we de taakduur** door werkuren om te zetten naar een `Duration`‑object en vervolgens de einddatum af te leiden.

## Stap 4: Resource toevoegen (**resources aan taken toewijzen**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Deze codefragment **voegt een resource toe aan het project** en **wijst resources toe aan taken** zodat de planner weet wie verantwoordelijk is voor het werk.

## Stap 5: Boomalgoritme toepassen

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initialiseer de `WorkAccumulator`‑klasse en pas het boomalgoritme toe om gemeenschappelijk werk over de hiërarchie te verzamelen.

## Stap 6: Taakwerk bijwerken

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Werk de werkwaarden voor taken bij op basis van de verzamelde informatie.

## Veelvoorkomende problemen & tips

- **Ontbrekende kalenderinstellingen:** Als de einddatum er verkeerd uitziet, zorg er dan voor dat de projectkalender correct is geconfigureerd voordat `GetFinishDateByStartAndWork` wordt aangeroepen.  
- **Resource‑type mismatch:** Stel altijd `Rsc.Type` in op `ResourceType.Work` voor op inspanning gebaseerde resources; anders kan de werkaccumulatie nul opleveren.  
- **Pro tip:** Na het bijwerken van het werk, roep `project.Save("UpdatedProject.mpp")` aan om de wijzigingen op te slaan.

## Conclusie

Door deze stappen te volgen weet je nu hoe je **een resource aan een project toevoegt**, **taakduur berekent**, en **resources aan taken toewijst** met behulp van het boomalgoritme van Aspose.Tasks. Deze methode stroomlijnt het beheer van hiërarchieën en houdt samenvattende werkwaarden nauwkeurig met minimale code.

## Veelgestelde vragen

### Q1: Wat is Aspose.Tasks voor .NET?

A1: Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars Microsoft Project‑bestanden programmatisch kunnen manipuleren met C#.

### Q2: Kan ik een gratis proefversie van Aspose.Tasks voor .NET downloaden?

A2: Ja, je kunt een gratis proefversie van Aspose.Tasks voor .NET downloaden vanaf [hier](https://releases.aspose.com/).

### Q3: Waar kan ik de documentatie voor Aspose.Tasks voor .NET vinden?

A3: Je kunt de documentatie voor Aspose.Tasks voor .NET vinden [hier](https://reference.aspose.com/tasks/net/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

A4: Voor ondersteuning met betrekking tot Aspose.Tasks voor .NET kun je het [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15) bezoeken.

### Q5: Is er een tijdelijke licentie beschikbaar voor testdoeleinden?

A5: Ja, je kunt een tijdelijke licentie voor testdoeleinden verkrijgen via [hier](https://purchase.aspose.com/temporary-license/).

## Veelgestelde vragen

**V: Kan ik deze aanpak gebruiken met een bestaand groot projectbestand?**  
A: Absoluut. Het boomalgoritme werkt op elke `Project`‑instantie, ongeacht de grootte.

**V: Werkt het algoritme ook de kostenwaarden bij?**  
A: Het voorbeeld richt zich op werk, maar je kunt het uitbreiden naar kosten door `Tsk.Cost` op een vergelijkbare manier te accumuleren.

**V: Welke .NET‑versies worden ondersteund?**  
A: Aspose.Tasks ondersteunt .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ en .NET 6+.

**V: Hoe ga ik om met meerdere resources per taak?**  
A: Voeg elke resource toe met `project.ResourceAssignments.Add(task, resource)`; de accumulator zal hun werk automatisch optellen.

---

**Laatst bijgewerkt:** 2026-03-19  
**Getest met:** Aspose.Tasks 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}