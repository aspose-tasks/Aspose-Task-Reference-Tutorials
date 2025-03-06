---
title: Bemästra WBS-kodmasker med Aspose.Tasks för .NET
linktitle: Samling av WBS-kodmasker i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Förbättra projektledning med Aspose.Tasks för .NET. Lär dig att skapa, hantera och överföra WBS-kodmasker utan ansträngning i denna omfattande handledning.
weight: 15
url: /sv/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemästra WBS-kodmasker med Aspose.Tasks för .NET

## Introduktion
I den dynamiska värld av projektledning är det avgörande att organisera uppgifter effektivt. Aspose.Tasks för .NET tillhandahåller en kraftfull lösning för att hantera koder för projektarbete, sammanbrottsstruktur (WBS) utan ansträngning. I den här handledningen kommer vi att fördjupa oss i samlingen av WBS-kodmasker, och utforska hur man implementerar och manipulerar dem med Aspose.Tasks för .NET.
## Förutsättningar
Innan vi ger oss ut på denna kodningsresa, se till att du har följande förutsättningar på plats:
- Har praktiska kunskaper i programmeringsspråket C#.
-  Aspose.Tasks för .NET installerat i din utvecklingsmiljö. Om inte, ladda ner den[här](https://releases.aspose.com/tasks/net/).
- En kodredigerare som Visual Studio för en sömlös kodningsupplevelse.
## Importera namnområden
För att komma igång, låt oss importera de nödvändiga namnrymden:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Initiera projekt- och WBS-koddefinition
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Definiera WBS-kodmasker
Rensa alla befintliga kodmasker och lägg till nya:
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
## 3. Visa information om kodmasker
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
## 4. Lägg till uppgifter i projektet
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Hämta uppgiftsinformation
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipulera kodmasker
Ta bort en kodmask och se till att den är borttagen:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Kopiera kodmasker till ett annat projekt
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
## 8. Visa kodmasker i ett annat projekt
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
## 9. Lägg till uppgifter i det andra projektet
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Visa WBS-koder i det andra projektet
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Slutsats
Med Aspose.Tasks för .NET blir det en enkel uppgift att hantera WBS-koder. Den här handledningen täckte skapandet, manipuleringen och överföringen av WBS-kodmasker, vilket ger dig en omfattande guide för att förbättra din projektledningsupplevelse.
## Vanliga frågor
### F: Kan jag använda Aspose.Tasks för .NET med andra programmeringsspråk?
S: Aspose.Tasks stöder främst .NET-språk, men du kan utforska interoperabilitetsalternativ med andra språk.
### F: Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan ladda ner testversionen[här](https://releases.aspose.com/).
### F: Hur söker jag hjälp eller rapporterar problem med Aspose.Tasks för .NET?
 A: Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för stöd och diskussioner.
### F: Vad är syftet med WBS-koder i projektledning?
S: WBS-koder hjälper till att organisera och strukturera projektuppgifter hierarkiskt, vilket ger ett systematiskt tillvägagångssätt för projektplanering.
### F: Kan jag anpassa formatet för WBS-koder i Aspose.Tasks för .NET?
S: Absolut, du har full kontroll över formatet och strukturen för WBS-koder med Aspose.Tasks för .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
