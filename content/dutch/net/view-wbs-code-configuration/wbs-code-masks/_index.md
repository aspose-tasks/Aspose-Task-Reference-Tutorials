---
title: Stapsgewijze WBS-codeconfiguratie in Aspose.Tasks .NET
linktitle: Configureer WBS-codemaskers in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de stapsgewijze configuratie van WBS-codemaskers in .NET-projecten met behulp van Aspose.Tasks. Verbeter moeiteloos de mogelijkheden voor projectmanagement.
type: docs
weight: 14
url: /nl/net/view-wbs-code-configuration/wbs-code-masks/
---
## Invoering
Aspose.Tasks voor .NET is een krachtige bibliotheek waarmee ontwikkelaars projectmanagementgegevens in .NET-applicaties efficiënt kunnen manipuleren. In deze zelfstudie verkennen we het proces van het configureren van Work Breakdown Structure (WBS)-codemaskers met behulp van Aspose.Tasks.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Tasks voor .NET Library: Download en installeer de bibliotheek van[Aspose.Tasks voor .NET-documentatie](https://reference.aspose.com/tasks/net/).
- Ontwikkelomgeving: Zorg ervoor dat u een werkende .NET-ontwikkelomgeving hebt ingesteld.
- Documentmap: Kies een map op uw systeem om de projectbestanden op te slaan.
## Naamruimten importeren
Neem in uw .NET-project de benodigde naamruimten op voor het werken met Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Stap 1: Maak een projectinstantie
Begin met het maken van een nieuw projectexemplaar:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Stap 2: Definieer WBS-codedefinitie
Stel de WBS-codedefinitie voor uw project in:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Stap 3: WBS-codemaskers toevoegen
Definieer WBS-codemaskers en voeg ze toe aan het project:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Stap 4: Taken maken
Taken toevoegen aan het project:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Stap 5: Herbereken
Bereken het project opnieuw om ervoor te zorgen dat WBS-codes correct worden toegepast:
```csharp
project.Recalculate();
```
## Stap 6: WBS-maskerinformatie weergeven
Voer informatie over WBS-maskers uit naar de console:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Stap 7: Sla het project op
Sla het project op met de toegevoegde WBS-codes:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Gefeliciteerd! U hebt met succes WBS-codemaskers geconfigureerd in uw Aspose.Tasks-project.
## Conclusie
In deze zelfstudie hebben we het stapsgewijze proces van het configureren van WBS-codemaskers met Aspose.Tasks voor .NET onderzocht. Deze krachtige bibliotheek biedt ontwikkelaars een naadloze manier om de projectmanagementmogelijkheden binnen hun .NET-applicaties te verbeteren.

## Veelgestelde vragen
### Kan ik Aspose.Tasks gratis gebruiken?
 Aspose.Tasks biedt een gratis proefversie, die u kunt downloaden[hier](https://releases.aspose.com/).
### Waar kan ik aanvullende ondersteuning vinden?
 bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15)voor gemeenschapssteun.
### Hoe kan ik een tijdelijke licentie verkrijgen?
 U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Is er gedetailleerde documentatie beschikbaar?
 Ja, de uitgebreide documentatie is beschikbaar[hier](https://reference.aspose.com/tasks/net/).
### Waar kan ik Aspose.Tasks kopen?
 Koop Aspose.Tasks[hier](https://purchase.aspose.com/buy).