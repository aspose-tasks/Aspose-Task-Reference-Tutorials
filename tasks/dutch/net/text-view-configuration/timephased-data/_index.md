---
title: Beheers tijdgebonden gegevensverwerking met Aspose.Tasks voor .NET
linktitle: Tijdgebonden gegevens verwerken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek Aspose.Tasks voor .NET om moeiteloos tijdgebonden gegevens te verwerken, de projectplanning te verbeteren en het resourcebeheer te optimaliseren. #Aspose #Taken #MS-project
weight: 14
url: /nl/net/text-view-configuration/timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheers tijdgebonden gegevensverwerking met Aspose.Tasks voor .NET

## Invoering
In de wereld van projectmanagement is een effectieve omgang met tijdgebonden gegevens cruciaal voor de toewijzing van middelen, kostenraming en algemene projectplanning. Aspose.Tasks voor .NET biedt een krachtige oplossing om naadloos met aangepaste tijdgebonden gegevens te werken. Deze tutorial begeleidt u bij het verwerken van tijdgebonden gegevens met behulp van Aspose.Tasks, waardoor u het resourcebeheer in uw projecten kunt optimaliseren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een basiskennis van projectmanagementconcepten.
-  Aspose.Tasks voor .NET geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
- Een code-editor, zoals Visual Studio, voor het implementeren van de gegeven voorbeelden.
## Naamruimten importeren
Zorg ervoor dat u in uw .NET-project de benodigde naamruimten importeert om de Aspose.Tasks-functionaliteiten te benutten. Voeg de volgende regels toe aan het begin van uw codebestand:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Laten we het gegeven voorbeeld nu opsplitsen in meerdere stappen om u te begeleiden bij het verwerken van tijdgebonden gegevens met Aspose.Tasks:
## Stap 1: Stel het project in
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Hier initialiseren we een nieuw project en stellen we de berekeningsmodus in.
## Stap 2: Definieer bronnen en taken
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Creëer werk- en kostenresources, evenals een taak, om een projectstructuur te simuleren.
## Stap 3: Wijs resources toe aan een taak
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Wijs werk- en kostenresources toe aan de taak.
## Stap 4: Voeg aangepaste tijdgebonden gegevens toe
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Soortgelijke stappen voor costAssignment
costAssignment.TimephasedData.Clear();
```
Voeg aangepaste tijdgebonden gegevens toe voor zowel werk- als kostentoewijzingen.
## Stap 5: Tijdgebonden gegevens weergeven
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Geef relevante informatie weer over elke tijdgebonden gegevensinvoer
    }
}
```
Geef ten slotte de tijdgebonden gegevens voor elke toewijzing weer.
#
## Conclusie
Het effectief verwerken van tijdgebonden gegevens in Aspose.Tasks opent nieuwe mogelijkheden voor gedetailleerde projectplanning en resourcebeheer. Door deze stapsgewijze handleiding te volgen, heeft u geleerd hoe u tijdgebonden gegevens kunt manipuleren om aan de specifieke behoeften van uw projecten te voldoen.
## Veel Gestelde Vragen
### Kan ik Aspose.Tasks voor .NET gebruiken met andere projectbeheertools?
Aspose.Tasks is voornamelijk ontworpen voor .NET-ontwikkeling. De functionaliteiten ervan kunnen echter een aanvulling vormen op verschillende projectmanagementtools.
### Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor .NET?
 Ja, u kunt een gratis proefperiode uitproberen[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?
 Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapssteun.
### Wat is een tijdelijke licentie en hoe kan ik deze verkrijgen?
 Meer informatie over tijdelijke licenties[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik de documentatie voor Aspose.Tasks voor .NET vinden?
 Raadpleeg het uitgebreide[documentatie](https://reference.aspose.com/tasks/net/) voor gedetailleerde informatie.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
