---
title: Opanowanie wartości zarysu projektu MS za pomocą Aspose.Tasks
linktitle: Zarządzanie wartościami konspektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać wartościami konspektu MS Project za pomocą Aspose.Tasks dla .NET. Z łatwością dostosowuj kontury projektu.
weight: 16
url: /pl/net/outline-code-page-settings/outline-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie wartości zarysu projektu MS za pomocą Aspose.Tasks

## Wstęp
W tym samouczku omówimy, jak zarządzać wartościami konspektu programu Microsoft Project przy użyciu biblioteki Aspose.Tasks dla platformy .NET. Dzięki Aspose.Tasks możesz łatwo manipulować kodami konspektu, tworzyć nowe wartości konspektu i dostosowywać konspekty projektu zgodnie z własnymi wymaganiami.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1.  Instalacja Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET ze strony[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne, takie jak Visual Studio, zgodne z platformą .NET.
3. Podstawowa znajomość programowania w C#: Zapoznaj się z podstawami języka programowania C#, ponieważ będziemy używać C# do pracy z biblioteką Aspose.Tasks.

## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do kodu C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Załaduj plik projektu
```csharp
// Ścieżka do katalogu dokumentów.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Ten krok inicjuje nowy obiekt Project i ładuje plik Microsoft Project z określonego katalogu.
## Krok 2: Zdefiniuj definicje kodu konspektu
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Tutaj definiujemy dwa obiekty OutlineCodeDefinition i dodajemy je do kolekcji OutlineCodes projektu.
## Krok 3: Zdefiniuj maskę konturu
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
W tym kroku konfigurowana jest maska konturu dla definicji kodu konspektu.
## Krok 4: Utwórz wartości konspektu
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
W tym kroku tworzymy dwa obiekty OutlineValue i ustawiamy ich właściwości, takie jak wartość, identyfikator wartości, typ, opis i stan zwinięcia.

## Wniosek
Zarządzanie wartościami zarysu MS Project za pomocą Aspose.Tasks dla .NET jest proste dzięki dostarczonym funkcjom. Wykonując kroki opisane w tym samouczku, możesz efektywnie manipulować kodami i wartościami konspektu, aby dostosować konspekty projektu do swoich potrzeb.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi frameworkami .NET?
O: Tak, Aspose.Tasks jest kompatybilny z różnymi frameworkami .NET, zapewniając elastyczność w Twoim środowisku programistycznym.
### P: Czy dostępna jest wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks z[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?
 Odp.: Aby uzyskać wsparcie i pomoc, możesz odwiedzić forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks?
Odp.: Tak, możesz kupić tymczasową licencję na Aspose.Tasks od[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę znaleźć szczegółową dokumentację dla Aspose.Tasks?
 Odp.: Możesz zapoznać się z dostępną obszerną dokumentacją[Tutaj](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
