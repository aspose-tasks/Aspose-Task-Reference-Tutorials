---
title: Praca z kolekcją linii bazowych w Aspose.Tasks
linktitle: Praca z kolekcją linii bazowych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać poziomami bazowymi w Aspose.Tasks dla .NET. Skorzystaj z naszego obszernego samouczka, aby uzyskać wskazówki krok po kroku.
type: docs
weight: 20
url: /pl/net/advanced-features/working-with-baseline-collection/
---
## Wstęp

Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom płynną pracę z plikami Microsoft Project w aplikacjach .NET. Wśród wielu funkcji zapewnia solidne wsparcie w zarządzaniu poziomami bazowymi w projektach. Linie bazowe są niezbędne w zarządzaniu projektami, ponieważ pozwalają porównać pierwotny plan projektu z bieżącym statusem, umożliwiając lepsze śledzenie i analizę postępu projektu.

## Warunki wstępne

Zanim zaczniemy pracować z kolekcjami bazowymi w Aspose.Tasks, upewnij się, że masz spełnione następujące wymagania wstępne:

1. Visual Studio: Zainstaluj Visual Studio IDE w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z językiem programowania C#.
4. Plik Microsoft Project: przygotuj plik Microsoft Project (.mpp) do celów testowych.

## Importuj przestrzenie nazw

Aby rozpocząć pracę z kolekcjami bazowymi w Aspose.Tasks, musisz zaimportować następujące przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Teraz podzielmy każdy przykład na wiele kroków:

## Krok 1: Załaduj plik projektu

Najpierw załaduj plik Microsoft Project za pomocą Aspose.Tasks:

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Krok 2: Zdobądź zasób

Następnie pobierz żądany zasób z projektu:

```csharp
var resource = project.Resources.GetByUid(1);
```

## Krok 3: Wyświetl informacje podstawowe

Teraz wyświetl informacje o liniach bazowych powiązanych z zasobem:

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Krok 4: Iteruj po liniach bazowych

Wykonaj iterację po każdej linii bazowej powiązanej z zasobem i wydrukuj odpowiednie informacje:

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Krok 5: Usuń linie bazowe

Usuń wszystkie plany bazowe powiązane z zasobem:

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## Wniosek

tym samouczku omówiliśmy, jak pracować z kolekcjami linii bazowych w Aspose.Tasks dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, można łatwo zarządzać poziomami bazowymi w aplikacjach .NET, umożliwiając efektywne śledzenie i analizę projektu.

## Często zadawane pytania

### P1: Czy Aspose.Tasks obsługuje duże pliki projektu?

Odpowiedź 1: Tak, Aspose.Tasks jest zoptymalizowany do wydajnej obsługi dużych plików projektów, zapewniając płynną wydajność.

### P2: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?

O2: Aspose.Tasks obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P3: Czy mogę dostosować linie bazowe w Aspose.Tasks?

O3: Tak, możesz dostosować linie bazowe zgodnie z wymaganiami projektu, używając Aspose.Tasks dla .NET.

### P4: Czy Aspose.Tasks oferuje wsparcie dla platform chmurowych?

Odpowiedź 4: Tak, Aspose.Tasks zapewnia wsparcie integracji z popularnymi platformami chmurowymi, oferując elastyczność we wdrażaniu.

### P5: Czy istnieje forum społecznościowe, na którym użytkownicy Aspose.Tasks mogą szukać pomocy i dzielić się wiedzą?

 A5: Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) nawiązać kontakt ze społecznością i uzyskać pomoc od ekspertów.