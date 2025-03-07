---
title: Manipulatie van MS-projectgroepcriteria in Aspose.Tasks
linktitle: Groepscriteria in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek hoe u MS Project-bestanden programmatisch kunt manipuleren in .NET met behulp van Aspose.Tasks. Stapsgewijze voorbeelden van taakgroep- en criteriuminformatie ophalen.
weight: 27
url: /nl/net/tasks-project-management/group-criteria/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulatie van MS-projectgroepcriteria in Aspose.Tasks

## Invoering
Aspose.Tasks voor .NET is een krachtige API die het werken met Microsoft Project-bestanden in uw .NET-applicaties vergemakkelijkt. Of u nu projectmanagementsoftware ontwikkelt of projectgegevens programmatisch moet manipuleren, Aspose.Tasks biedt een uitgebreide reeks functies om aan uw behoeften te voldoen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Kennis van C# en .NET Framework
Bekendheid met de programmeertaal C# en .NET Framework is essentieel om de voorbeelden in deze tutorial te begrijpen en te implementeren.
### 2. Installatie van Aspose.Tasks voor .NET
 Zorg ervoor dat Aspose.Tasks voor .NET in uw ontwikkelomgeving is geïnstalleerd. U kunt de bibliotheek downloaden van[hier](https://releases.aspose.com/tasks/net/) en volg de meegeleverde installatie-instructies.
### 3. Geïntegreerde ontwikkelomgeving (IDE)
Zorg ervoor dat een IDE zoals Visual Studio op uw systeem is geïnstalleerd voor het schrijven en uitvoeren van C#-code.

## Naamruimten importeren
Importeer om te beginnen de benodigde naamruimten in uw C#-code:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Stap 1: Laad een Microsoft Project-bestand
Geef eerst het pad naar uw Microsoft Project-bestand op:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 Vervangen`"Your Document Directory"` met het pad naar uw projectbestand.
## Stap 2: Informatie over taakgroepen ophalen
Haal vervolgens informatie op over taakgroepen in het project:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Dit codefragment drukt het totale aantal taakgroepen af, haalt de tweede taakgroep op, de naam ervan en het aantal criteria dat deze groep bevat.
## Stap 3: Criteriuminformatie van de taakgroep ophalen
Laten we nu eens kijken naar de details van een specifiek criterium binnen de taakgroep:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Dit segment geeft verschillende eigenschappen van het criterium weer, zoals de index, het veld, de groeperingsinformatie, de celkleur, de kleur van het lettertype, het groepsinterval en het startpunt.
## Stap 4: Haal de lettertype-informatie van Criterion op
Verkrijg ten slotte lettertypegerelateerde details van het criterium:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
Met deze stap worden de naam van het lettertype, de grootte en de stijl afgedrukt en wordt aangegeven of het criterium in oplopende of aflopende volgorde is gesorteerd.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u Aspose.Tasks voor .NET kunt gebruiken om informatie over taakgroepen en criteria op te halen uit een Microsoft Project-bestand. Door de stapsgewijze handleiding te volgen, kunt u programmatisch efficiënt met projectgegevens werken in uw .NET-applicaties.
## Veelgestelde vragen
### Kan Aspose.Tasks grote Microsoft Project-bestanden verwerken?
Aspose.Tasks is geoptimaliseerd om grote projectbestanden efficiënt te verwerken, waardoor hoge prestaties en betrouwbaarheid worden gegarandeerd.
### Is Aspose.Tasks compatibel met alle versies van Microsoft Project?
Ja, Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, waardoor compatibiliteit tussen verschillende bestandsformaten wordt gegarandeerd.
### Kan ik projectgegevens manipuleren met Aspose.Tasks?
Absoluut, Aspose.Tasks biedt uitgebreide functionaliteiten om projectgegevens te manipuleren, inclusief taken, bronnen, kalenders en meer.
### Biedt Aspose.Tasks ondersteuning voor verschillende .NET-platforms?
Ja, Aspose.Tasks ondersteunt meerdere .NET-platforms, waaronder .NET Framework, .NET Core en .NET Standard.
### Is er een communityforum voor Aspose.Tasks waar ik hulp kan zoeken?
 Ja, u kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) om vragen te stellen, kennis te delen en samen te werken met andere gebruikers.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
