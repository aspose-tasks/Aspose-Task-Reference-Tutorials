---
title: Verzameling van resourcetoewijzingen in Aspose.Tasks
linktitle: Verzameling van resourcetoewijzingen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u resourcetoewijzingen in Microsoft Project beheert met Aspose.Tasks voor .NET. Stapsgewijze zelfstudie met codevoorbeelden.
type: docs
weight: 12
url: /nl/net/resource-risk-analysis/resource-assignment-collection/
---
## Invoering
Welkom bij deze uitgebreide zelfstudie over het beheren van resourcetoewijzingen in Microsoft Project met Aspose.Tasks voor .NET. In deze zelfstudie gaan we stap voor stap dieper in op het proces, zodat u goed begrijpt hoe u resourcetoewijzingen efficiënt kunt manipuleren. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze gids leidt u door alles wat u moet weten.
## Vereisten
Voordat we in de code duiken, moet je ervoor zorgen dat je het volgende hebt ingesteld:
1.  Aspose.Tasks voor .NET geïnstalleerd: Zorg ervoor dat Aspose.Tasks voor .NET in uw ontwikkelomgeving is geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van[hier](https://releases.aspose.com/tasks/net/).
2. Basiskennis van C#: Deze tutorial gaat ervan uit dat je een basiskennis hebt van de programmeertaal C#.
3. Microsoft Project-bestand: Zorg ervoor dat u een Microsoft Project-bestand gereed heeft voor testdoeleinden. Als u er geen heeft, kunt u een voorbeeldbestand maken.

## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Stap 1: Laad het projectbestand
Begin met het laden van het Microsoft Project-bestand:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Stap 2: Taak en resource toevoegen
Laten we nu een taak en een bron aan het project toevoegen:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Stap 3: Wijs een resource toe aan een taak
Vervolgens wijzen we de resource toe aan de taak:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Stap 4: Werken met verschillende opdrachttypen
Je kunt ook werken met opgaven met eenheden of kosten:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Stel eigenschappen voor toewijzingen met eenheden en kosten in op dezelfde manier als weergegeven in stap 3
```
## Stap 5: Opdrachten afdrukken
Print de opdrachten voor het project:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Opdrachtgegevens afdrukken
}
```
## Stap 6: Toewijzing ophalen via UID
U kunt toewijzingen ophalen via UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Stap 7: Controleer de alleen-lezenstatus
Controleer of de verzameling resourcetoewijzingen alleen-lezen is:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Stap 8: Converteer verzameling naar lijst en herhaal
Converteer de verzameling naar een lijst en herhaal deze:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusie
Gefeliciteerd! U hebt geleerd hoe u resourcetoewijzingen in Microsoft Project beheert met Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u taken en bronnen efficiënt manipuleren, waardoor projectbeheer een fluitje van een cent wordt.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met verschillende versies van Microsoft Project-bestanden?
A: Ja, Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project-bestanden, waaronder MPP-, MPT- en XML-formaten.
### Vraag: Is er een proefversie beschikbaar voordat u Aspose.Tasks voor .NET aanschaft?
 A: Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET krijgen van[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen als ik problemen ondervind tijdens het gebruik van Aspose.Tasks voor .NET?
 A: U kunt ondersteuning zoeken op het Aspose.Tasks-forum[hier](https://forum.aspose.com/c/tasks/15).
### Vraag: Kan ik tijdelijke licenties gebruiken voor Aspose.Tasks voor .NET?
 A: Ja, er zijn tijdelijke licenties beschikbaar voor evaluatiedoeleinden. Je kunt er een krijgen van[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Waar kan ik een volledige licentie kopen voor Aspose.Tasks voor .NET?
 A: U kunt een volledige licentie kopen in de Aspose online winkel[hier](https://purchase.aspose.com/buy).