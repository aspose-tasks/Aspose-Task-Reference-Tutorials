---
title: Opanuj maski konspektu projektu MS za pomocą Aspose.Tasks
linktitle: Zbiór masek konturowych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak manipulować maskami konturowymi kolekcji MS Project za pomocą Aspose.Tasks dla .NET. Zwiększ produktywność dzięki temu wszechstronnemu samouczkowi.
type: docs
weight: 15
url: /pl/net/outline-code-page-settings/outline-mask-collection/
---
## Wstęp
Czy chcesz wykorzystać moc masek konturowych Microsoft Project przy użyciu Aspose.Tasks dla .NET? Trafiłeś we właściwe miejsce! W tym obszernym samouczku poprowadzimy Cię krok po kroku przez proces, zapewniając solidną wiedzę na temat skutecznego manipulowania maskami konturu w Twoich projektach. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik wyposaży Cię w wiedzę i umiejętności potrzebne do optymalizacji przepływu pracy.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Instalacja Aspose.Tasks dla .NET
Upewnij się, że w środowisku programistycznym zainstalowano Aspose.Tasks for .NET. Bibliotekę można pobrać ze strony internetowej Aspose[Tutaj](https://releases.aspose.com/tasks/net/).
### 2. Podstawowa znajomość C# i .NET Framework
Zapoznaj się z językiem programowania C# i platformą .NET Framework, ponieważ w tym samouczku zostaną wykorzystane oba.
### 3. Plik projektu Microsoft
Przygotuj plik Microsoft Project (MPP) do celów testowych. Możesz użyć istniejącego pliku lub utworzyć nowy do eksperymentów.
## Importuj przestrzenie nazw
Zacznijmy od zaimportowania niezbędnych przestrzeni nazw do projektu C#. Ten krok gwarantuje, że masz dostęp do wymaganych klas i funkcjonalności udostępnianych przez Aspose.Tasks dla .NET.

Dodaj następujące przestrzenie nazw na początku pliku kodu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Podzielmy teraz podany przykład na wiele kroków i szczegółowo wyjaśnijmy każdy krok:
## Krok 1: Zainicjuj obiekt projektu
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
 Tutaj tworzymy nową instancję pliku`Project` class i załaduj istniejący plik Microsoft Project o nazwie „OutlineValues2010.mpp”.
## Krok 2: Uzyskaj dostęp do kodów konspektu
```csharp
var outline = project.OutlineCodes[0];
```
Uzyskujemy dostęp do kodów konspektu z projektu. Kody konspektu to niestandardowe pola w programie Microsoft Project, które umożliwiają kategoryzację i organizowanie zadań.
## Krok 3: Wyczyść maski konturowe
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
Ten krok gwarantuje, że wszelkie istniejące maski konturowe zostaną usunięte przed kontynuowaniem.
## Krok 4: Utwórz maski konturowe
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
Tworzymy nowe maski konturowe i określamy ich typy. W tym przykładzie tworzymy prawidłową maskę konturową i niewłaściwą.
## Krok 5: Wstaw i edytuj maski
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Tutaj wstawiamy do kolekcji niewłaściwą maskę i edytujemy długość maski za pomocą jej indeksu.
## Krok 6: Usuń maski
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
Usuwamy z kolekcji niewłaściwą maskę na podstawie jej indeksu.
## Krok 7: Iteruj po maskach
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
Ta pętla wykonuje iterację po każdej masce konturu w kolekcji i wypisuje jej właściwości, takie jak długość, poziom, separator i typ.
## Krok 8: Skopiuj maski do innego projektu
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Na koniec kopiujemy maski konturowe z jednego projektu do drugiego, zapewniając spójność między różnymi projektami.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się manipulować maskami konturowymi kolekcji MS Project za pomocą Aspose.Tasks dla .NET. Postępując zgodnie z tym samouczkiem, posiadasz teraz umiejętności skutecznego zarządzania maskami konturu w swoich projektach, co ostatecznie zwiększa produktywność i przepływ pracy.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks dla .NET z różnymi wersjami plików Microsoft Project?
O: Tak, Aspose.Tasks dla .NET obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### P2: Czy Aspose.Tasks dla .NET jest kompatybilny z .NET Core?
O: Tak, Aspose.Tasks dla .NET jest kompatybilny z .NET Core, co pozwala na używanie go w aplikacjach wieloplatformowych.
### P3: Czy mogę dostosować właściwości masek konturowych do wymagań mojego projektu?
Odp.: Absolutnie! Można dostosować maski konturu, dostosowując ich długość, poziom, separator i typ, aby dopasować je do konkretnych potrzeb projektu.
### P4: Czy Aspose.Tasks dla .NET zapewnia dokumentację i wsparcie?
Odp.: Tak, Aspose.Tasks dla .NET oferuje obszerną dokumentację i dedykowane wsparcie za pośrednictwem swojej strony internetowej i[fora](https://forum.aspose.com/c/tasks/15).
### P5: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks dla .NET z ich[strona internetowa](https://releases.aspose.com/tasks/net/). aby zapoznać się z jego cechami i funkcjonalnościami przed dokonaniem zakupu.