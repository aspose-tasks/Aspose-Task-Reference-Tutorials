---
title: Beheersing van tijdgebonden gegevensverzameling in Aspose.Tasks
linktitle: Verzameling van tijdgebonden gegevens in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek tijdgebonden gegevensverzameling in Aspose.Tasks voor .NET. Stapsgewijze handleiding, veelgestelde vragen en meer. Verbeter vandaag nog uw projectmanagementmogelijkheden!
type: docs
weight: 15
url: /nl/net/text-view-configuration/timephased-data-collection/
---
## Invoering
Wilt u de kracht van tijdgebonden gegevens in uw .NET-applicaties benutten met behulp van Aspose.Tasks? Zoek niet verder! Deze uitgebreide gids leidt u door het proces van het verzamelen van tijdgebonden gegevens met Aspose.Tasks voor .NET, zodat u het meeste uit deze krachtige bibliotheek haalt.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET Library: Download en installeer de bibliotheek van[Aspose.Tasks .NET-documentatie](https://reference.aspose.com/tasks/net/).
2. .NET-ontwikkelomgeving: Zorg ervoor dat u een werkende .NET-ontwikkelomgeving hebt ingesteld.
3. Uw documentenmap: Vervang de tijdelijke aanduiding "Uw documentenmap" in de codefragmenten door het pad naar uw documentmap.
## Naamruimten importeren
Begin in uw .NET-project met het importeren van de benodigde naamruimten om de Aspose.Tasks-functionaliteiten te benutten:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Maak een project en bronnen
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Voeg taken toe aan het project
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Taakeigenschappen instellen...
var task2 = project.RootTask.Children.Add("Task 2");
// Eigenschappen van taak2 instellen...
```
## 3. Wijs bronnen toe aan taken
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Toewijzingseigenschappen instellen...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Eigenschappen van opdracht2 instellen...
```
## 4. Werk met tijdgebonden gegevens
```csharp
// Gecontourde werkcontour instellen
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Controleer of tijdgebonden gegevensverzameling alleen-lezen is
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Wis gegenereerde tijdgebonden gegevens
assignment.TimephasedData.Clear();
// Tijdgebonden gegevens maken en toevoegen
var td = new TimephasedData
{
    // Tijdgebonden gegevenseigenschappen instellen...
};
assignment.TimephasedData.Add(td);
// Voeg een lijst met tijdgebonden gegevens toe
var list = new List<TimephasedData>();
// Voeg meer tijdgebonden gegevensitems toe aan de lijst...
assignment.TimephasedData.AddRange(list);
// Filter tijdgebonden gegevens op type en datumbereik
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Gefilterde tijdgebonden gegevens afdrukken...
```
## 5. Manipuleer tijdgebonden gegevens
```csharp
//Voeg een verkeerd tijdgebonden gegevensitem toe en verwijder het vervolgens
var td4 = new TimephasedData
{
    // Verkeerde tijdgebonden gegevenseigenschappen instellen...
};
assignment.TimephasedData.Add(td4);
// Verwijder het verkeerde tijdgebonden gegevensitem
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Herhaal alle tijdgebonden items
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Tijdgebonden artikeldetails afdrukken...
}
```
## 6. Kopieer tijdgebonden gegevens naar een andere toewijzing
```csharp
// Kopieer tijdgebonden gegevens naar een andere opdracht
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Converteer de verzameling naar een gewone lijst
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Verwijder tijdgebonden gegevensitems één voor één
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusie
Concluderend: deze tutorial biedt een gedetailleerd overzicht van het verzamelen van tijdgebonden gegevens met behulp van Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u deze functionaliteit naadloos in uw projecten integreren, waardoor een effectieve tijdregistratie en resourcebeheer mogelijk wordt.
## Veel Gestelde Vragen
### Kan ik Aspose.Tasks voor .NET gebruiken met andere projectbeheertools?
Ja, Aspose.Tasks voor .NET is ontworpen om te werken met populaire projectmanagementtools en ondersteunt verschillende bestandsformaten.
### Is er een limiet aan het aantal bronnen en taken dat ik kan beheren met Aspose.Tasks?
Aspose.Tasks verwerkt projecten van verschillende omvang en er is geen strikte limiet op het aantal bronnen en taken.
### Hoe kan ik ondersteuning krijgen voor problemen of vragen met betrekking tot Aspose.Tasks voor .NET?
 Voor ondersteuning kunt u terecht op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) om verbinding te maken met de gemeenschap en hulp te krijgen.
### Kan ik Aspose.Tasks voor .NET uitproberen voordat ik het aanschaf?
 Ja, u kunt de functies van Aspose.Tasks voor .NET verkennen door naar de[gratis proefperiode](https://releases.aspose.com/).
### Waar kan ik een licentie kopen voor Aspose.Tasks voor .NET?
 U kunt een licentie kopen voor Aspose.Tasks voor .NET[hier](https://purchase.aspose.com/buy).