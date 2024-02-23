---
title: Verzameling MS-project van overzichtscodes in Aspose.Tasks
linktitle: Verzameling van overzichtscodes in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Microsoft Project-overzichtscodes verzamelt met Aspose.Tasks voor .NET. Deze uitgebreide tutorial biedt stapsgewijze instructies.
type: docs
weight: 11
url: /nl/net/outline-code-page-settings/outline-code-collection/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u Microsoft Project-overzichtscodes kunt verzamelen met Aspose.Tasks voor .NET. We zullen het proces opsplitsen in stapsgewijze instructies om duidelijkheid en begrip te garanderen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Visual Studio: Installeer Visual Studio op uw systeem.
2.  Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van programmeren in C#: Bekendheid met C# is een voordeel.

## Naamruimten importeren
Importeer eerst de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteit in uw C#-project.
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## Stap 1: Laad het projectbestand
 Begin met het laden van het Microsoft Project-bestand met behulp van de`Project` klas.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Stap 2: Verzamel overzichtscodes
Maak een verzamelprogramma om de overzichtscodes van de projecttaken te verzamelen.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Stap 3: Herhaal de taken en overzichtscodes
Doorloop de verzamelde taken en schetscodes en druk de details ervan af.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Stap 4: Voeg een aangepaste overzichtscodedefinitie toe
Voeg een aangepaste overzichtscodedefinitie toe aan het project.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Stap 5: Maak een overzichtscode en voeg deze in
Maak een overzichtscode en voeg deze in een taak in.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Stap 6: Overzichtscodes manipuleren
Manipuleer de overzichtscodes indien nodig, zoals invoegen, verwijderen of wissen.
```csharp
// Voorbeeld van manipulatie
// ,
// Voer code in met 2 op de juiste positie
task.OutlineCodes.Insert(2, code2);
// Controleer of de code is ingevoerd
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u Microsoft Project-overzichtscodes kunt verzamelen met Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u de overzichtscodes binnen uw projecten effectief beheren, waardoor de organisatie en duidelijkheid worden verbeterd.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere programmeertalen?
A: Ja, Aspose.Tasks for .NET richt zich primair op het .NET-platform, maar biedt ook ondersteuning voor andere programmeertalen via Aspose.Tasks for Cloud.
### Vraag: Zijn er beperkingen op de grootte van de projectbestanden die Aspose.Tasks voor .NET kan verwerken?
A: Aspose.Tasks voor .NET kan grote projectbestanden efficiënt verwerken, maar de prestaties kunnen variëren afhankelijk van de complexiteit en grootte van het bestand.
### Vraag: Is Aspose.Tasks voor .NET compatibel met de nieuwste versies van Microsoft Project?
A: Ja, Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project, inclusief de nieuwste versies.
### Vraag: Kan ik het uitvoerformaat aanpassen als ik met Aspose.Tasks voor .NET werk?
A: Absoluut, Aspose.Tasks voor .NET biedt uitgebreide opties om het uitvoerformaat aan te passen aan uw vereisten.
### Vraag: Waar kan ik aanvullende ondersteuning of bronnen vinden voor Aspose.Tasks voor .NET?
 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor hulp of vragen over Aspose.Tasks voor .NET.