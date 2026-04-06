---
date: 2026-04-06
description: Dowiedz się, jak dodać zasób do projektu i ustawić okresy dostępności
  zasobu przy użyciu Aspose.Tasks dla .NET. Przewodnik krok po kroku dotyczący zarządzania
  kalendarzami zasobów.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Praca z okresami dostępności w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Dodaj zasób do projektu i ustaw dostępność w Aspose.Tasks
url: /pl/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj zasób do projektu i ustaw dostępność w Aspose.Tasks

## Wprowadzenie

W tym samouczku nauczysz się **jak dodać zasób do projektu** i następnie określić jego okresy dostępności przy użyciu biblioteki Aspose.Tasks .NET. Zarządzanie kalendarzami zasobów jest niezbędne do realistycznych harmonogramów projektów, a poniższe kroki przeprowadzą Cię przez cały proces — od utworzenia instancji projektu po wypisanie szczegółów każdego okresu.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Dodanie zasobu do projektu i skonfigurowanie jego okresów dostępności.  
- **Jaka biblioteka jest wymagana?** Aspose.Tasks dla .NET.  
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest licencja komercyjna.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czas implementacji?** Zazwyczaj poniżej 15 minut dla podstawowych scenariuszy.

## Co to jest „dodawanie zasobu do projektu”?

Dodanie zasobu do projektu tworzy miejsce dla osoby, sprzętu lub materiału, które mogą być przydzielane do zadań. Gdy zasób istnieje, możesz **ustawić dostępność zasobu**, zdefiniować jego kalendarz pracy i pozwolić harmonogramowi respektować te ograniczenia.

## Dlaczego konfigurować harmonogram pracy i okresy dostępności?

- **Dokładne planowanie:** Zadania są planowane tylko wtedy, gdy zasób jest rzeczywiście wolny.  
- **Kontrola kosztów:** Jednostki dostępności odzwierciedlają pracę w niepełnym wymiarze, pomagając prawidłowo obliczyć koszty pracy.  
- **Poziomowanie zasobów:** Silnik może automatycznie wyrównać nadmierne przydziały, gdy zna kalendarz każdego zasobu.

## Wymagania wstępne

1. Visual Studio (lub dowolne IDE zgodne z .NET).  
2. Aspose.Tasks for .NET – pobierz z [tutaj](https://releases.aspose.com/tasks/net/).  
3. Podstawowa znajomość C#.

## Importuj przestrzenie nazw

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Jak dodać zasób do projektu?

### Krok 1: Utwórz nową instancję `Project`

```csharp
var project = new Project();
```

Ten obiekt reprezentuje cały plik projektu w pamięci.

### Krok 2: Dodaj zasób do projektu

```csharp
var resource = project.Resources.Add("Work Resource");
```

Wywołanie tworzy **zasób** o nazwie *Work Resource*, który później możesz przypisać do zadań.

### Krok 3: Zdefiniuj okresy dostępności

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` jest metodą pomocniczą (implementacja nie pokazana), która zwraca kolekcję obiektów `AvailabilityPeriod`. Każdy okres określa datę rozpoczęcia, datę zakończenia oraz jednostki (procent pełnoetatowego nakładu), w których zasób jest dostępny.

### Krok 4: Dodaj okresy do zasobu

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Tutaj **ustawiamy dostępność zasobu** iterując po kolekcji i dodając każdy okres do kalendarza zasobu.

### Krok 5: Wyświetl szczegóły dostępności

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Wyjście konsoli pozwala zweryfikować, że okresy zostały poprawnie zapisane.

## Częste pułapki i wskazówki

- **Precyzja daty:** `AvailableFrom` i `AvailableTo` są wartościami `DateTime`; upewnij się, że są ustawione na północ, jeśli chcesz pełnodniowe okresy.  
- **Zakres jednostek:** Poprawne wartości to 0‑100 %; wartości poza tym zakresem spowodują wyjątek.  
- **Nakładające się okresy:** Nakładające się okresy są automatycznie łączone, ale lepiej jest zachować je odrębnie.

## Najczęściej zadawane pytania

### P1: Czy mogę używać Aspose.Tasks dla .NET w projektach komercyjnych?

A1: Tak, Aspose.Tasks dla .NET może być używany w projektach komercyjnych. Licencję możesz kupić [tutaj](https://purchase.aspose.com/buy).

### P2: Czy dostępna jest darmowa wersja próbna Aspose.Tasks dla .NET?

A2: Tak, darmową wersję próbną Aspose.Tasks dla .NET możesz uzyskać [tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

A3: Dokumentację znajdziesz [tutaj](https://reference.aspose.com/tasks/net/).

### P4: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

A4: Wsparcie możesz uzyskać na forum społeczności [tutaj](https://forum.aspose.com/c/tasks/15).

### P5: Czy oferujecie tymczasowe licencje dla Aspose.Tasks dla .NET?

A5: Tak, tymczasowe licencje są dostępne [tutaj](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-04-06  
**Testowano z:** Aspose.Tasks for .NET (najnowsze stabilne wydanie)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}