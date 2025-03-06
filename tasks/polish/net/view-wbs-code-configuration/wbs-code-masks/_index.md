---
title: Konfiguracja kodu WBS krok po kroku w Aspose.Tasks .NET
linktitle: Konfigurowanie masek kodów WBS w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Poznaj krok po kroku konfigurację masek kodu WBS w projektach .NET przy użyciu Aspose.Tasks. Zwiększaj możliwości zarządzania projektami bez wysiłku.
weight: 14
url: /pl/net/view-wbs-code-configuration/wbs-code-masks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfiguracja kodu WBS krok po kroku w Aspose.Tasks .NET

## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom efektywne manipulowanie danymi zarządzania projektami w aplikacjach .NET. W tym samouczku omówimy proces konfigurowania masek kodu struktury podziału pracy (WBS) za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Tasks dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[Aspose.Tasks dla dokumentacji .NET](https://reference.aspose.com/tasks/net/).
- Środowisko programistyczne: Upewnij się, że masz skonfigurowane działające środowisko programistyczne .NET.
- Katalog dokumentów: Wybierz katalog w swoim systemie, w którym będą przechowywane pliki projektu.
## Importuj przestrzenie nazw
W swoim projekcie .NET uwzględnij przestrzenie nazw niezbędne do pracy z Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## Krok 1: Utwórz instancję projektu
Rozpocznij od utworzenia nowej instancji projektu:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Krok 2: Zdefiniuj definicję kodu SPP
Skonfiguruj definicję kodu SPP dla swojego projektu:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Krok 3: Dodaj maski kodu WBS
Zdefiniuj maski kodu SPP i dodaj je do projektu:
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
## Krok 4: Utwórz zadania
Dodaj zadania do projektu:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Krok 5: Oblicz ponownie
Przelicz projekt ponownie, aby upewnić się, że kody WBS zostały zastosowane prawidłowo:
```csharp
project.Recalculate();
```
## Krok 6: Wyświetl informacje o masce WBS
Wyprowadź informacje o maskach WBS do konsoli:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Krok 7: Zapisz projekt
Zapisz projekt z dodanymi kodami WBS:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Gratulacje! Pomyślnie skonfigurowałeś maski kodu WBS w projekcie Aspose.Tasks.
## Wniosek
W tym samouczku omówiliśmy krok po kroku proces konfigurowania masek kodu WBS przy użyciu Aspose.Tasks dla .NET. Ta potężna biblioteka zapewnia programistom płynny sposób zwiększania możliwości zarządzania projektami w aplikacjach .NET.

## Często zadawane pytania
### Czy mogę korzystać z Aspose.Tasks za darmo?
 Aspose.Tasks oferuje bezpłatną wersję próbną, którą możesz pobrać[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkowe wsparcie?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności.
### Jak mogę uzyskać licencję tymczasową?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy dostępna jest szczegółowa dokumentacja?
 Tak, dostępna jest obszerna dokumentacja[Tutaj](https://reference.aspose.com/tasks/net/).
### Gdzie mogę kupić Aspose.Tasks?
 Kup Aspose.Tasks[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
