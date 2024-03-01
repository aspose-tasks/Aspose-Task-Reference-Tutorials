---
title: WBS-codemaskers beheersen met Aspose.Tasks voor .NET
linktitle: Verzameling WBS-codemaskers in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Verbeter projectbeheer met Aspose.Tasks voor .NET. Leer moeiteloos WBS-codemaskers maken, beheren en overdragen in deze uitgebreide zelfstudie.
type: docs
weight: 15
url: /nl/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Invoering
In de dynamische wereld van projectmanagement is het efficiënt organiseren van taken cruciaal. Aspose.Tasks voor .NET biedt een krachtige oplossing voor het moeiteloos beheren van WBS-codes (project Work Breakdown Structure). In deze zelfstudie verdiepen we ons in de verzameling WBS-codemaskers en onderzoeken we hoe we deze kunnen implementeren en manipuleren met Aspose.Tasks voor .NET.
## Vereisten
Voordat we aan dit codeertraject beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een praktische kennis van de programmeertaal C#.
-  Aspose.Tasks voor .NET geïnstalleerd in uw ontwikkelomgeving. Zo niet, download het dan[hier](https://releases.aspose.com/tasks/net/).
- Een code-editor zoals Visual Studio voor een naadloze codeerervaring.
## Naamruimten importeren
Laten we om te beginnen de benodigde naamruimten importeren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Initialiseer de project- en WBS-codedefinitie
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definieer WBS-codemaskers
Wis eventuele bestaande codemaskers en voeg nieuwe toe:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. Informatie over codemaskers weergeven
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. Voeg taken toe aan het project
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Taakinformatie ophalen
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipuleer codemaskers
Verwijder een codemasker en zorg ervoor dat het wordt verwijderd:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Kopieer codemaskers naar een ander project
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. Geef codemaskers weer in een ander project
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. Voeg taken toe aan het andere project
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Geef WBS-codes weer in het andere project
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Conclusie
Met Aspose.Tasks voor .NET wordt het beheren van WBS-codes een moeiteloze taak. Deze tutorial behandelde het maken, manipuleren en overbrengen van WBS-codemaskers en biedt u een uitgebreide handleiding om uw projectmanagementervaring te verbeteren.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere programmeertalen?
A: Aspose.Tasks ondersteunt voornamelijk .NET-talen, maar u kunt interoperabiliteitsopties met andere talen verkennen.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u kunt de proefversie downloaden[hier](https://releases.aspose.com/).
### Vraag: Hoe zoek ik hulp of meld ik problemen met Aspose.Tasks voor .NET?
 A: Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning en discussies.
### Vraag: Wat is het doel van WBS-codes in projectmanagement?
A: WBS-codes helpen bij het hiërarchisch organiseren en structureren van projecttaken, waardoor een systematische benadering van de projectplanning ontstaat.
### Vraag: Kan ik de indeling van WBS-codes in Aspose.Tasks voor .NET aanpassen?
A: Absoluut, u heeft volledige controle over het formaat en de structuur van WBS-codes met behulp van Aspose.Tasks voor .NET.