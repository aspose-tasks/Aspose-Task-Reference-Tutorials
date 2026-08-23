---
date: 2026-03-21
description: Dowiedz się, jak zarządzać okresami dostępności zasobów i osiągnąć efektywną
  dostępność zasobów projektu przy użyciu Aspose.Tasks dla .NET. Ten przewodnik krok
  po kroku pokazuje, jak dodać, zaktualizować i usunąć okresy dostępności.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Dostępność zasobów projektu – zarządzanie okresami dostępności w Aspose.Tasks
url: /pl/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostępność zasobów projektu: Zbiór okresów dostępności w Aspose.Tasks

Zarządzanie **dostępnością zasobów projektu** jest kluczową częścią skutecznego planowania projektu. W tym samouczku nauczysz się **zarządzać dostępnością** zasobów przy użyciu API Aspose.Tasks dla .NET, krok po kroku, od wczytania projektu po kopiowanie okresów między zasobami.

## Szybkie odpowiedzi
- **Jaka jest główna klasa dla okresów dostępności?** `AvailabilityPeriod` w przestrzeni nazw `Aspose.Tasks`.  
- **Czy mogę wyczyścić istniejące okresy?** Tak, wywołaj `resource.AvailabilityPeriods.Clear()`.  
- **Jak dodać nowy okres?** Utwórz obiekt `AvailabilityPeriod` i użyj `Add` lub `Insert`.  
- **Czy można skopiować okresy do innego zasobu?** Oczywiście – użyj `CopyTo`, a następnie dodaj każdy element do docelowego zasobu.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak, wymagana jest komercyjna licencja Aspose.Tasks dla wdrożeń nie‑testowych.

## Czym jest dostępność zasobów projektu?
Dostępność zasobów projektu określa daty i jednostki (procent pojemności), w których zasób może być przydzielany do zadań. Kontrolując te okresy, zapobiegasz nadmiernemu przydziałowi i poprawiasz dokładność harmonogramu.

## Dlaczego warto używać Aspose.Tasks do zarządzania okresami dostępności?
- **Pełna integracja z .NET** – brak interfejsu COM, czysty kod zarządzany.  
- **Precyzyjna kontrola** – ustaw dokładne daty rozpoczęcia/zakończenia oraz jednostki ułamkowe.  
- **Łatwe kopiowanie** – przenoszenie danych dostępności między zasobami bez ręcznego parsowania.  
- **Wydajność zoptymalizowana** – efektywnie działa z dużymi plikami MPP.

## Prerequisites
1. **Visual Studio** – dowolna aktualna wersja (2019, 2022 lub nowsza).  
2. **Aspose.Tasks for .NET** – pobierz z [tutaj](https://releases.aspose.com/tasks/net/).  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z klasami, kolekcjami i LINQ.

## Importowanie przestrzeni nazw

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importujemy podstawową przestrzeń nazw Aspose.Tasks wraz ze standardowymi kolekcjami .NET, które będą potrzebne później.

## Krok 1: Inicjalizacja projektu i zasobu

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Tutaj wczytujemy istniejący plik MPP i pobieramy zasób, którego dostępność chcemy edytować (ID = 1).

## Krok 2: Wyczyść istniejące okresy dostępności

```csharp
resource.AvailabilityPeriods.Clear();
```

Czyszczenie usuwa wszystkie wcześniej zdefiniowane okresy, dając nam czystą kartę.

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

Pobieramy kolekcję obiektów `AvailabilityPeriod` (zakładamy, że pomocnicza metoda `GetPeriods` jest zdefiniowana gdzie indziej) i dodajemy każdy z nich, sprawdzając, czy kolekcja jest zapisywalna.

## Krok 4: Wstaw nowy okres dostępności

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Tworzy to niestandardowy okres na rok 2013 i wstawia go na pozycję 1 (drugi slot), jeśli nie jest już obecny.

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

Szybkie wypisanie w konsoli pokazuje łączną liczbę i szczegóły każdego okresu – przydatne do debugowania lub weryfikacji.

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

Kopiujemy całą kolekcję do tablicy, czyscimy okresy docelowego zasobu, a następnie ponownie je wypełniamy. To pokazuje, jak duplikować dane dostępności między zasobami.

## Krok 7: Aktualizuj i usuń okresy dostępności

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Tutaj dostosowujemy `AvailableUnits` dla przedostatniego okresu, a następnie usuwamy okres z 2013 roku, który dodaliśmy wcześniej.

## Częste problemy i rozwiązania
- **Błąd kolekcji tylko do odczytu** – Upewnij się, że projekt nie jest otwarty w trybie tylko do odczytu lub że wywołałeś `resource.AvailabilityPeriods.Clear()` przed dodaniem nowych elementów.  
- **Nakładające się okresy** – Aspose.Tasks nie łączy automatycznie nakładających się okresów; może być konieczne napisanie własnej logiki wykrywania i rozwiązywania ich.  
- **Nieprawidłowy format daty** – Zawsze używaj obiektów `DateTime`; parsowanie łańcuchów może prowadzić do błędów zależnych od ustawień regionalnych.

## Najczęściej zadawane pytania

**P:** Czy mogę dodać pola niestandardowe do okresów dostępności?  
**O:** Nie, okresy dostępności w Aspose.Tasks dla .NET nie obsługują pól niestandardowych.

**P:** Czy okresy dostępności są powiązane z konkretnymi zadaniami?  
**O:** Nie, są powiązane z zasobami i określają, kiedy zasób jest ogólnie dostępny dla zadań.

**P:** Czy mogę importować okresy dostępności z zewnętrznych źródeł?  
**O:** Tak, możesz importować okresy z CSV, XML lub bazy danych, tworząc obiekty `AvailabilityPeriod` i dodając je do kolekcji.

**P:** Jak radzić sobie z nakładającymi się okresami dostępności?  
**O:** Nakładania nie są rozwiązywane automatycznie; musisz zaimplementować własną walidację, aby scalić lub odrzucić konflikujące okresy.

**P:** Czy istnieje limit liczby okresów dostępności, które może mieć zasób?  
**O:** Nie ma sztywnego limitu, ale bardzo duże kolekcje mogą wpływać na wydajność; rozważ konsolidację okresów, gdzie to możliwe.

## Zakończenie

W tym przewodniku omówiliśmy wszystko, co musisz wiedzieć, aby zarządzać **dostępnością zasobów projektu** przy użyciu Aspose.Tasks dla .NET — od inicjalizacji projektu i czyszczenia starych danych, po dodawanie, wstawianie, kopiowanie, aktualizowanie i usuwanie okresów dostępności. Opanowanie tych kroków pomaga utrzymać kalendarze zasobów w dokładności oraz realistyczne harmonogramy projektów.

---

**Ostatnia aktualizacja:** 2026-03-21  
**Testowano z:** Aspose.Tasks for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}