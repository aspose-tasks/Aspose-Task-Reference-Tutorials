---
title: Opanowanie masek kodowych WBS za pomocą Aspose.Tasks dla .NET
linktitle: Zbiór masek kodów WBS w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Usprawnij zarządzanie projektami dzięki Aspose.Tasks dla .NET. Dzięki temu obszernemu samouczkowi nauczysz się bez wysiłku tworzyć, zarządzać i przesyłać maski kodów WBS.
type: docs
weight: 15
url: /pl/net/view-wbs-code-configuration/wbs-code-mask-collection/
---
## Wstęp
dynamicznym świecie zarządzania projektami sprawne organizowanie zadań jest kluczowe. Aspose.Tasks dla .NET zapewnia potężne rozwiązanie do łatwego zarządzania kodami struktury podziału pracy nad projektem (WBS). W tym samouczku zagłębimy się w kolekcję masek kodu WBS, badając, jak je wdrożyć i manipulować nimi za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim wyruszymy w tę podróż kodowania, upewnij się, że spełniasz następujące wymagania wstępne:
- Praktyczna znajomość języka programowania C#.
-  Aspose.Tasks dla .NET zainstalowany w Twoim środowisku programistycznym. Jeśli nie, pobierz go[Tutaj](https://releases.aspose.com/tasks/net/).
- Edytor kodu, taki jak Visual Studio, zapewniający płynne kodowanie.
## Importuj przestrzenie nazw
Na początek zaimportujmy niezbędne przestrzenie nazw:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Zainicjuj definicję projektu i kodu SPP
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. Zdefiniuj maski kodów WBS
Usuń wszystkie istniejące maski kodu i dodaj nowe:
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
## 3. Wyświetl informacje o maskach kodów
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
## 4. Dodaj zadania do projektu
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. Pobierz informacje o zadaniu
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. Manipuluj maskami kodu
Usuń maskę kodu i upewnij się, że została usunięta:
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. Skopiuj maski kodu do innego projektu
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
## 8. Wyświetl maski kodu w innym projekcie
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
## 9. Dodaj zadania do innego projektu
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. Wyświetl kody WBS w innym projekcie
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## Wniosek
Dzięki Aspose.Tasks dla .NET zarządzanie kodami WBS staje się zadaniem łatwym. W tym samouczku omówiono tworzenie, manipulowanie i przesyłanie masek kodów WBS, zapewniając kompleksowy przewodnik poprawiający doświadczenie w zarządzaniu projektami.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z innymi językami programowania?
Odp.: Aspose.Tasks obsługuje głównie języki .NET, ale możesz poznać opcje współdziałania z innymi językami.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Odp.: Tak, możesz pobrać wersję próbną.[Tutaj](https://releases.aspose.com/).
### P: Jak szukać pomocy lub zgłaszać problemy z Aspose.Tasks dla .NET?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie i dyskusje.
### P: Jaki jest cel kodów WBS w zarządzaniu projektami?
Odp.: Kody WBS pomagają organizować i strukturyzować zadania projektu w sposób hierarchiczny, zapewniając systematyczne podejście do planowania projektu.
### P: Czy mogę dostosować format kodów WBS w Aspose.Tasks dla .NET?
O: Oczywiście, masz pełną kontrolę nad formatem i strukturą kodów WBS przy użyciu Aspose.Tasks dla .NET.