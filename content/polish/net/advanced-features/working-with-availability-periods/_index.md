---
title: Praca z okresami dostępności w Aspose.Tasks
linktitle: Praca z okresami dostępności w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać okresami dostępności zasobów za pomocą Aspose.Tasks dla .NET. Ten samouczek zawiera przewodnik krok po kroku dotyczący pracy z okresami dostępności w projektach .NET.
type: docs
weight: 17
url: /pl/net/advanced-features/working-with-availability-periods/
---
## Wstęp

tym samouczku omówimy, jak pracować z okresami dostępności w Aspose.Tasks dla .NET. Okresy dostępności są kluczowe dla efektywnego zarządzania zasobami w scenariuszach zarządzania projektami. Krok po kroku przeprowadzimy Cię przez proces.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1. Visual Studio: Zainstaluj Visual Studio lub dowolne inne preferowane IDE do programowania .NET.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość programowania w języku C#: Pomocna będzie znajomość podstaw języka programowania C#.

## Importuj przestrzenie nazw

Zanim zagłębisz się w kod, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Podzielmy przykładowy kod na wiele kroków:

## Krok 1: Utwórz nową instancję projektu

```csharp
var project = new Project();
```

Ta linia inicjuje nową instancję klasy Project, która reprezentuje projekt w Aspose.Tasks.

## Krok 2: Dodaj zasób

```csharp
var resource = project.Resources.Add("Work Resource");
```

Tutaj dodajemy do projektu nowy zasób o nazwie „Zasób pracy”.

## Krok 3: Zdefiniuj okresy dostępności

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

 Nazywamy`GetPeriods()` metoda pobierania kolekcji okresów dostępności.

## Krok 4: Dodaj okresy dostępności do zasobu

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Iterujemy po kolekcji okresów dostępności uzyskanych w poprzednim kroku i dodajemy je do zasobu.

## Krok 5: Wyświetl szczegóły okresu dostępności

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Na koniec przeglądamy okresy dostępności powiązane z zasobem i drukujemy ich szczegóły, w tym datę początkową, datę końcową i dostępne jednostki.

## Wniosek

W tym samouczku nauczyliśmy się pracować z okresami dostępności w Aspose.Tasks dla .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz efektywnie zarządzać dostępnością zasobów w aplikacjach do zarządzania projektami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Tasks dla .NET w projektach komercyjnych?

 O1: Tak, Aspose.Tasks dla .NET może być wykorzystywane w projektach komercyjnych. Możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy).

### P2: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?

 A2: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

 Odpowiedź 3: Możesz znaleźć dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).

### P4: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

 Odpowiedź 4: Możesz uzyskać pomoc na forum społeczności.[Tutaj](https://forum.aspose.com/c/tasks/15).

### P5: Czy oferujecie tymczasowe licencje na Aspose.Tasks dla .NET?

 Odpowiedź 5: Tak, dostępne są licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).