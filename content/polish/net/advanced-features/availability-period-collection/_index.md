---
title: Zbiór okresów dostępności w Aspose.Tasks
linktitle: Zbiór okresów dostępności w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać okresami dostępności zasobów w Aspose.Tasks dla .NET. Ten samouczek krok po kroku przeprowadzi Cię przez proces dodawania, aktualizowania i usuwania okresów dostępności, zapewniając efektywne planowanie zasobów projektu.
type: docs
weight: 18
url: /pl/net/advanced-features/availability-period-collection/
---
## Wstęp

tym samouczku omówimy, jak pracować z kolekcją okresów dostępności zasobu w Aspose.Tasks dla .NET. Zarządzanie okresami dostępności ma kluczowe znaczenie w zarządzaniu projektami, ponieważ pozwala nam określić, kiedy zasoby są dostępne dla zadań w ramach projektu.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa wiedza: Znajomość C# i frameworku .NET.

## Importuj przestrzenie nazw

Najpierw musimy zaimportować niezbędne przestrzenie nazw do naszego projektu:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Podzielmy przykładowy kod na wiele kroków i poznajmy każdą część:

## Krok 1: Zainicjuj projekt i zasób

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Tutaj ładujemy plik projektu i uzyskujemy konkretny zasób według jego identyfikatora.

## Krok 2: Wyczyść istniejące okresy dostępności

```csharp
resource.AvailabilityPeriods.Clear();
```

Usuwamy wszelkie istniejące okresy dostępności powiązane z zasobem.

## Krok 3: Dodaj okresy dostępności

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Wykonujemy iterację kolekcji okresów dostępności i dodajemy je do zasobu.

## Krok 4: Wstaw nowy okres dostępności

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Tworzymy nowy okres dostępności na rok 2013 i włączamy go do kolekcji.

## Krok 5: Wyświetl okresy dostępności

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Drukujemy liczbę i szczegóły każdego okresu dostępności powiązanego z zasobem.

## Krok 6: Skopiuj okresy dostępności do innego zasobu

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Kopiujemy okresy dostępności z jednego zasobu do drugiego.

## Krok 7: Zaktualizuj i usuń okresy dostępności

```csharp
// Aktualizuj dostępne jednostki na określony okres
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Usuń określony okres
otherResource.AvailabilityPeriods.Remove(period2013);
```

Aktualizujemy dostępne jednostki dla okresu i usuwamy określone okresy z kolekcji.

## Wniosek

W tym samouczku nauczyliśmy się, jak pracować z kolekcjami okresów dostępności w Aspose.Tasks dla .NET. Zarządzanie dostępnością zasobów jest niezbędne do skutecznego planowania i realizacji projektów.

## Często zadawane pytania

### P1: Czy mogę dodać niestandardowe pola do okresów dostępności?

O1: Nie, okresy dostępności w Aspose.Tasks dla .NET nie obsługują pól niestandardowych.

### Pytanie 2: Czy okresy dostępności są powiązane z konkretnymi zadaniami?

Odpowiedź 2: Nie, okresy dostępności są powiązane z zasobami i ogólnie określają, kiedy są one dostępne dla zadań.

### P3: Czy mogę importować okresy dostępności ze źródeł zewnętrznych?

O3: Tak, możesz importować okresy dostępności z różnych źródeł danych za pomocą Aspose.Tasks dla interfejsów API .NET.

### P4: Jak sobie poradzić z nakładającymi się okresami dostępności?

O4: Aspose.Tasks dla .NET nie zapewnia wbudowanych mechanizmów do obsługi nakładających się okresów. Aby zarządzać takimi scenariuszami, może być konieczne zaimplementowanie logiki niestandardowej.

### P5: Czy istnieje ograniczenie liczby okresów dostępności zasobu?

Odpowiedź 5: Nie ma z góry określonego limitu liczby okresów dostępności zasobu, ale w przypadku dużej liczby okresów wydajność może się pogorszyć.