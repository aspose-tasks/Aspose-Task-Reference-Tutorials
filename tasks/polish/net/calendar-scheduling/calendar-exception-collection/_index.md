---
date: 2026-04-09
description: Dowiedz się, jak ustawić standardowy kalendarz i zarządzać dniami wolnymi
  w projektach .NET przy użyciu Aspose.Tasks, aby zapewnić dokładne harmonogramowanie.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Ustaw standardowy kalendarz i obsłuż wyjątki w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ustaw standardowy kalendarz i obsłuż wyjątki w Aspose.Tasks
url: /pl/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw standardowy kalendarz i obsłuż wyjątki w Aspose.Tasks

## Wprowadzenie

Dokładne planowanie jest podstawą każdego udanego projektu, a plany w rzeczywistości często muszą odbiegać od domyślnego kalendarza pracy z powodu świąt, specjalnych wydarzeń lub nieoczekiwanych przestojów. Aspose.Tasks dla .NET ułatwia **set standard calendar** ustawienia i następnie nakładanie własnych wyjątków. W tym samouczku nauczysz się, jak wczytać kalendarz projektu, ustawić standardowy kalendarz oraz zarządzać świętami projektowymi za pomocą funkcji Calendar Exception Collection.

## Szybkie odpowiedzi
- **Co robi „set standard calendar”?** Resetuje kalendarz do domyślnego czasu pracy (9 – 17, od poniedziałku do piątku) przed dodaniem własnych wyjątków.  
- **Która metoda usuwa istniejące wyjątki?** `Calendar.Exceptions.Clear()` usuwa wszystkie wcześniej zdefiniowane wyjątki.  
- **Jak dodać święto?** Utwórz `CalendarException` z `DayWorking = false` i dodaj go do kolekcji.  
- **Czy muszę ponownie wczytać projekt po zmianach?** Nie, zmiany są stosowane bezpośrednio do obiektu `Project` w pamięci.  
- **Jakie biblioteki są wymagane?** Aspose.Tasks dla .NET (dowolna obsługiwana wersja .NET) oraz przestrzenie nazw `System`.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz:

1. **Aspose.Tasks for .NET** – download it [here](https://releases.aspose.com/tasks/net/).  
2. Podstawową znajomość **C#** – będziesz pisać kilka krótkich fragmentów.  
3. Środowisko programistyczne, takie jak **Visual Studio** lub **JetBrains Rider**.

## Importowanie przestrzeni nazw

Te dyrektywy `using` zapewniają dostęp do klas potrzebnych do manipulacji kalendarzem.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Czym jest wyjątek kalendarza?

*Wyjątek kalendarza* reprezentuje okres, w którym normalny harmonogram pracy jest zmieniony – na przykład ogólnozakładowe święto lub tymczasowy harmonogram nadgodzin. Dodając wyjątki do kalendarza, możesz modelować rzeczywiste ograniczenia bez zmiany bazowego kalendarza.

## Jak ustawić standardowy kalendarz w Aspose.Tasks

Pierwszym krokiem jest wczytanie pliku projektu i pobranie kalendarza, z którym chcesz pracować.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Krok 1: Usuń istniejące wyjątki i zresetuj do standardowego kalendarza

Przed dodaniem nowych reguł, dobrą praktyką jest usunięcie starych wyjątków i **set standard calendar** ustawień. Zapewnia to czystą bazę.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Krok 2: Zdefiniuj wyjątek czasu pracy

Czasami trzeba stworzyć tymczasowy harmonogram (np. wydłużone godziny przy wprowadzaniu produktu). Poniższy fragment definiuje wyjątek czasu pracy obejmujący kilka dni i zawierający dwa dzienne okresy pracy.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Krok 3: Dodaj wyjątki czasu niepracującego (święta)

Aby **manage project holidays**, utwórz wyjątki, w których `DayWorking` jest `false`. Poniższy przykład dodaje dwudniowy blok świąteczny.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Krok 4: Wyświetl wyjątki kalendarza (weryfikacja)

Po dodaniu wyjątków często chcesz zweryfikować, czy zostały poprawnie zapisane. Poniższa pętla wypisuje szczegóły każdego wyjątku na konsolę.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Krok 5: Usuń wszystkie wyjątki (czyszczenie)

Jeśli potrzebujesz przywrócić kalendarz do pierwotnego stanu, możesz programowo usunąć wszystkie wyjątki.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| Wyjątki nie pojawiają się po zapisaniu | Projekt nie został zapisany po modyfikacjach | Wywołaj `project.Save("output.mpp")` po wprowadzeniu zmian. |
| Nakładające się wyjątki powodują nieoczekiwane godziny pracy | Aspose.Tasks używa ostatnio dodanego wyjątku dla nakładających się okresów | Ułóż wywołania `Add` ostrożnie lub ręcznie dostosuj priorytety. |
| `MakeStandardCalendar` resetuje niestandardowe godziny pracy | Celowo usuwa niestandardowe godziny; w razie potrzeby dodaj je ponownie po wywołaniu. | Dodaj własne obiekty `WorkingTime` po wywołaniu `MakeStandardCalendar`. |

## Najczęściej zadawane pytania

**Q: Czy mogę dodać wiele wyjątków do jednego kalendarza?**  
A: Tak, możesz dodać wiele wyjątków do kalendarza używając metody `AddRange`.

**Q: Jak obsłużyć powtarzające się wyjątki, takie jak cotygodniowe święta?**  
A: Możesz programowo obliczyć powtarzające się wyjątki i dodać je do kalendarza przy użyciu własnej logiki.

**Q: Czy można importować wyjątki kalendarza z zewnętrznych źródeł?**  
A: Tak, możesz odczytać wyjątki kalendarza z zewnętrznych źródeł, takich jak bazy danych czy pliki CSV i zintegrować je z projektem.

**Q: Co się stanie, jeśli w kalendarzu wystąpią nakładające się wyjątki?**  
A: Aspose.Tasks dla .NET pozwala obsłużyć nakładające się wyjątki, definiując priorytety lub rozwiązując konflikty zgodnie z wymaganiami projektu.

**Q: Czy mogę dostosować godziny pracy dla każdego dnia w ramach wyjątku?**  
A: Tak, możesz określić własne godziny pracy dla poszczególnych dni w ramach wyjątku, aby dopasować je do konkretnych potrzeb harmonogramu.

## Podsumowanie

Poprzez **setting a standard calendar** najpierw, a następnie nakładanie własnych wyjątków, zyskujesz pełną kontrolę nad planowaniem projektu, co ułatwia **manage project holidays** oraz inne specjalne terminy. Kolekcja Calendar Exception w Aspose.Tasks zapewnia czysty, programowy sposób modelowania rzeczywistych kalendarzy bezpośrednio w aplikacjach .NET.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}