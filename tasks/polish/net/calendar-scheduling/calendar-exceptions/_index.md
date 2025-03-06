---
title: Obsługa wyjątków kalendarza w Aspose.Tasks
linktitle: Obsługa wyjątków kalendarza w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać wyjątkami kalendarza w Aspose.Tasks dla .NET, korzystając ze szczegółowych samouczków i przykładów.
weight: 12
url: /pl/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa wyjątków kalendarza w Aspose.Tasks

## Wstęp

W tym samouczku przyjrzymy się, jak zarządzać wyjątkami kalendarza w Aspose.Tasks przy użyciu platformy .NET. Wyjątki kalendarzowe pozwalają na zdefiniowanie w kalendarzu projektu specjalnych dat lub okresów, w których następuje zmiana normalnego harmonogramu pracy, np. święta czy tymczasowe zamknięcia. Omówimy krok po kroku różne metody obsługi wyjątków kalendarza, używając Aspose.Tasks dla .NET.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany w systemie.
- Do Twojego projektu dodano bibliotekę Aspose.Tasks for .NET.

## Importuj przestrzenie nazw

Na początek zaimportujmy niezbędne przestrzenie nazw dla naszego projektu:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Usuwanie wyjątku kalendarza

Aby usunąć wyjątek kalendarza, wykonaj następujące kroki:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Wyświetlanie informacji z kalendarza
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Usuń pierwszy wyjątek
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Krok 2: Pobieranie czasu pracy wyjątku kalendarzowego

Aby pobrać czas pracy wyjątku kalendarza, wykonaj następujące kroki:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Wyświetlanie informacji o kalendarzu i wyjątkach
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Uzyskaj czas pracy i wyświetl szczegóły
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Krok 3: Definiowanie wyjątków kalendarza

Aby dodać lub usunąć wyjątki kalendarza, wykonaj następujące kroki:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Utwórz nowy wyjątek kalendarza
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Ustaw szczegóły wyjątku
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Sprawdź, czy dana data jest wyjątkiem
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Dodaj wyjątek do kalendarza
    calendar.Exceptions.Add(exception);

    // Usuń wyjątek, jeśli istnieje
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Dodaj nowy wyjątek
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Drukuj wyjątki
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Wniosek

tym artykule omówiliśmy różne aspekty obsługi wyjątków kalendarza w Aspose.Tasks dla .NET. Postępując zgodnie z podanymi krokami, możesz skutecznie zarządzać wyjątkami w harmonogramach projektów, zapewniając dokładne odwzorowanie godzin pracy i wydarzeń specjalnych.

## Często zadawane pytania

### P1: Czy mogę dodać wiele wyjątków do jednego kalendarza?

Odpowiedź 1: Tak, możesz dodać wiele wyjątków do kalendarza, aby uwzględnić różne specjalne daty lub okresy.

### P2: Jak mogę sprawdzić, czy dana data jest wyjątkiem?

 Odpowiedź 2: Możesz użyć`CheckException()` metoda sprawdzania, czy dana data podlega wyjątkowi.

### P3: Czy można usunąć istniejący wyjątek z kalendarza?

 Odpowiedź 3: Tak, możesz usunąć wyjątki, uzyskując dostęp do pliku`Exceptions` zbieranie kalendarza i korzystanie z niego`Remove()` metoda.

### P4: Jakie typy wyjątków kalendarza są obsługiwane?

O4: Aspose.Tasks obsługuje różne typy wyjątków, w tym wyjątki dzienne, tygodniowe, miesięczne i roczne, zapewniając elastyczność w definiowaniu reguł wyjątków.

### P5: Czy mogę dostosować godziny pracy do konkretnych dat wyjątków?

O5: Tak, możesz zdefiniować niestandardowe godziny pracy dla poszczególnych dat wyjątków, korzystając z odpowiednich metod dostarczonych przez Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
