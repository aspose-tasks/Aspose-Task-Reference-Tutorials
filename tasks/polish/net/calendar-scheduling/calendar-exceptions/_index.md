---
date: 2026-04-13
description: Dowiedz się, jak usunąć wyjątek kalendarza w Aspose.Tasks dla .NET oraz
  sprawdzić datę wyjątku podczas zarządzania harmonogramem kalendarza w ASP.NET.
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Usuwanie wyjątku kalendarza przy użyciu Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Usuń wyjątek kalendarza za pomocą Aspose.Tasks
url: /pl/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Usuń wyjątek kalendarza w Aspose.Tasks

## Wprowadzenie

W tym samouczku dowiesz się, jak **usunąć wyjątek kalendarza** i zarządzać innymi wyjątkami kalendarza w Aspose.Tasks przy użyciu platformy .NET. Wyjątki kalendarza pozwalają modelować święta, tymczasowe zamknięcia lub dowolne specjalne okresy, w których zmienia się normalny harmonogram pracy. Zrozumienie, jak dodawać, zapytywać i usuwać te wyjątki, jest niezbędne do dokładnego planowania projektu, szczególnie w scenariuszach **planowania kalendarza w ASP.NET**.

## Szybkie odpowiedzi
- **Jaka jest podstawowa metoda usuwania wyjątku?** Użyj metody `Delete()` na obiekcie `CalendarException`.  
- **Która klasa sprawdza datę względem wyjątku?** `CalendarException.CheckException()` — przydatna do **sprawdzenia daty wyjątku**.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Tak, ważna licencja Aspose.Tasks jest wymagana w środowisku produkcyjnym.  
- **Czy mogę dodać wiele wyjątków do jednego kalendarza?** Oczywiście; kolekcja `Exceptions` obsługuje wiele wpisów.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co to jest wyjątek kalendarza?

**Wyjątek kalendarza** reprezentuje odchylenie od regularnego kalendarza pracy — można to traktować jako regułę, która mówi „w tych datach godziny pracy są inne lub wcale nie ma pracy”. W Aspose.Tasks każdy wyjątek może mieć własne godziny pracy, wzorzec powtarzalności oraz flagi wskazujące, czy dany dzień jest pracujący.

## Dlaczego zarządzać wyjątkami kalendarza w planowaniu kalendarza ASP.NET?

- **Dokładne terminy:** Projekty automatycznie uwzględniają święta i specjalne zamknięcia, zapobiegając nierealistycznym terminom.  
- **Elastyczność:** Możesz definiować wzorce dzienne, tygodniowe, miesięczne lub roczne, dopasowując je do rzeczywistych kalendarzy firmowych.  
- **Automatyzacja:** Programowe sprawdzanie daty wyjątku pozwala budować dynamiczną logikę planowania w aplikacjach ASP.NET.

## Wymagania wstępne

- Podstawowa znajomość programowania w C#.  
- Visual Studio (dowolna aktualna wersja).  
- Biblioteka Aspose.Tasks for .NET dodana do projektu (przez NuGet lub ręczne odwołanie).  

## Importowanie przestrzeni nazw

Najpierw zaimportuj potrzebne przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Usuń wyjątek kalendarza

Usunięcie niechcianego wyjątku jest proste. Poniższy kod ładuje projekt, wybiera pierwszy kalendarz, wyświetla podstawowe informacje, usuwa pierwszy wyjątek, a następnie pokazuje zaktualizowaną liczbę.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Wskazówka:** Zawsze sprawdzaj, czy indeks wyjątku istnieje przed wywołaniem `Delete()`, aby uniknąć `IndexOutOfRangeException`.

## Krok 2: Pobierz czas pracy wyjątku kalendarza

Jeśli potrzebujesz przejrzeć godziny pracy zdefiniowane dla wyjątku, użyj `GetWorkingTime()`. Ten przykład również pokazuje, jak **sprawdzić datę wyjątku** przy pomocy `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Krok 3: Zdefiniuj wyjątki kalendarza

Poniżej znajduje się kompletny przewodnik, który pokazuje, jak **dodawać**, **sprawdzać** i **usuwać** wyjątki kalendarza. Zwróć uwagę na użycie `CheckException` do **sprawdzenia daty wyjątku** dla konkretnego momentu.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Typowe problemy i wskazówki

| Problem | Powód | Rozwiązanie |
|-------|--------|----------|
| **`IndexOutOfRangeException` przy usuwaniu** | Próba usunięcia nieistniejącego wyjątku. | Sprawdź, czy `calendar.Exceptions.Count` > indeks przed wywołaniem `Delete()`. |
| **Nieprawidłowe czasy pracy** | Nieprawidłowe ustawienie `DayWorking` lub `WorkingTimes`. | Użyj `exception.WorkingTimes.Add(new WorkingTime(...))`, aby zdefiniować wyraźne okresy. |
| **Wyjątek nie rozpoznany** | `CheckException` zwraca `false`, ponieważ data znajduje się poza określonym zakresem. | Sprawdź ponownie `FromDate`/`ToDate` oraz `Type` (Daily, Weekly, itp.). |

## Najczęściej zadawane pytania

**P: Czy mogę dodać wiele wyjątków do jednego kalendarza?**  
O: Tak, możesz dodać dowolną liczbę wyjątków, aby reprezentować święta, okna konserwacyjne lub dowolne specjalne reguły planowania.

**P: Jak **sprawdzić datę wyjątku** dla konkretnego dnia?**  
O: Użyj metody `CheckException(DateTime date)` na instancji `CalendarException`. Zwraca `true`, jeśli podana data mieści się w zakresie wyjątku.

**P: Czy można usunąć istniejący wyjątek z kalendarza?**  
O: Oczywiście. Uzyskaj dostęp do kolekcji `Exceptions` i wywołaj `Remove()` lub `Delete()` na konkretnym obiekcie `CalendarException`.

**P: Jakie typy wyjątków kalendarza są obsługiwane?**  
O: Aspose.Tasks obsługuje typy Daily, Weekly, Monthly i Yearly, dając elastyczność modelowania prawie każdego wzorca powtarzalności.

**P: Czy mogę dostosować godziny pracy dla konkretnych dat wyjątków?**  
O: Tak. Po utworzeniu wyjątku, wypełnij jego kolekcję `WorkingTimes` obiektami `WorkingTime`, które definiują godziny rozpoczęcia i zakończenia dla tego dnia.

## Zakończenie

Przeszliśmy przez pełny cykl operacji **usuwania wyjątku kalendarza**, od przeglądania istniejących wyjątków po dodawanie nowych i sprawdzanie dat. Opanowanie tych technik zapewnia, że harmonogramy projektów respektują rzeczywiste kalendarze, czyniąc implementacje planowania kalendarza w ASP.NET solidnymi i niezawodnymi.

---

**Ostatnia aktualizacja:** 2026-04-13  
**Testowano z:** Aspose.Tasks for .NET (latest release)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}