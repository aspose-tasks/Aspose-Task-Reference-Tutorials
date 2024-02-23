---
title: Manipulacja kryteriami grupy projektowej MS w Aspose.Tasks
linktitle: Kryteria grupowe w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak programowo manipulować plikami MS Project w .NET przy użyciu Aspose.Tasks. Pobierz przykłady krok po kroku informacji o grupach zadań i kryteriach.
type: docs
weight: 27
url: /pl/net/tasks-project-management/group-criteria/
---
## Wstęp
Aspose.Tasks dla .NET to potężne API, które ułatwia pracę z plikami Microsoft Project w aplikacjach .NET. Niezależnie od tego, czy tworzysz oprogramowanie do zarządzania projektami, czy chcesz programowo manipulować danymi projektu, Aspose.Tasks oferuje kompleksowy zestaw funkcji spełniających Twoje potrzeby.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Znajomość C# i .NET Framework
Znajomość języka programowania C# i .NET Framework jest niezbędna do zrozumienia i wdrożenia przykładów podanych w tym samouczku.
### 2. Instalacja Aspose.Tasks dla .NET
 Upewnij się, że w środowisku programistycznym zainstalowano Aspose.Tasks for .NET. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/tasks/net/) i postępuj zgodnie z dostarczonymi instrukcjami instalacji.
### 3. Zintegrowane środowisko programistyczne (IDE)
Zainstaluj w swoim systemie środowisko IDE, takie jak Visual Studio, umożliwiające pisanie i wykonywanie kodu C#.

## Importuj przestrzenie nazw
Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego kodu C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Załaduj plik projektu Microsoft
Najpierw określ ścieżkę do pliku Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
 zastępować`"Your Document Directory"` ze ścieżką do pliku projektu.
## Krok 2: Pobierz informacje o grupach zadań
Następnie pobierz informacje o grupach zadań w projekcie:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
Ten fragment kodu drukuje całkowitą liczbę grup zadań, pobiera drugą grupę zadań, jej nazwę i liczbę spełnianych przez nią kryteriów.
## Krok 3: Uzyskaj informacje o kryteriach grupy zadaniowej
Zagłębmy się teraz w szczegóły konkretnego kryterium w ramach grupy zadaniowej:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
Segment ten wyświetla różne właściwości kryterium, takie jak jego indeks, pole, informacje o grupowaniu, kolor komórki, kolor czcionki, odstęp między grupami i punkt początkowy.
## Krok 4: Pobierz informacje o czcionce kryterium
Na koniec uzyskaj szczegółowe informacje dotyczące czcionki w kryterium:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
W tym kroku drukowana jest nazwa czcionki, jej rozmiar, styl oraz informacja, czy kryterium jest sortowane w kolejności rosnącej czy malejącej.

## Wniosek
W tym samouczku omówiliśmy, jak używać Aspose.Tasks dla .NET do pobierania informacji o grupach zadań i kryteriach z pliku Microsoft Project. Postępując zgodnie z przewodnikiem krok po kroku, możesz efektywnie pracować z danymi projektu programowo w aplikacjach .NET.
## Często zadawane pytania
### Czy Aspose.Tasks może obsługiwać duże pliki Microsoft Project?
Aspose.Tasks jest zoptymalizowany do wydajnej obsługi dużych plików projektów, zapewniając wysoką wydajność i niezawodność.
### Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Tak, Aspose.Tasks obsługuje różne wersje Microsoft Project, zapewniając kompatybilność z różnymi formatami plików.
### Czy mogę manipulować danymi projektu za pomocą Aspose.Tasks?
Absolutnie Aspose.Tasks zapewnia rozbudowane funkcje do manipulowania danymi projektu, w tym zadaniami, zasobami, kalendarzami i nie tylko.
### Czy Aspose.Tasks oferuje wsparcie dla różnych platform .NET?
Tak, Aspose.Tasks obsługuje wiele platform .NET, w tym .NET Framework, .NET Core i .NET Standard.
### Czy istnieje forum społecznościowe dla Aspose.Tasks, na którym mogę szukać pomocy?
 Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) zadawać pytania, dzielić się wiedzą i współpracować z innymi użytkownikami.