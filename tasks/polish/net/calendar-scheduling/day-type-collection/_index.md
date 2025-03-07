---
title: Zarządzanie kolekcją typów dni w Aspose.Tasks
linktitle: Zarządzanie kolekcją typów dni w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać kolekcjami typu dni w Aspose.Tasks dla .NET. Z łatwością twórz, modyfikuj i manipuluj wyjątkami kalendarza.
weight: 28
url: /pl/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzanie kolekcją typów dni w Aspose.Tasks

## Wstęp

 Aspose.Tasks dla .NET zapewnia solidną funkcjonalność do zarządzania kolekcjami typów dni, kluczową dla definiowania wyjątków kalendarza tygodniowego w aplikacjach do zarządzania projektami. W tym samouczku dowiemy się, jak wykorzystać plik`DayTypeCollection` klasę efektywnie. 

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# i koncepcji frameworku .NET.

## Importuj przestrzenie nazw

Aby rozpocząć, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#:

```csharp
using Aspose.Tasks;
using System;


```

Podzielmy teraz podany przykład na kilka kroków:

## Krok 1: Załaduj projekt i uzyskaj dostęp do kalendarza

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Ten krok inicjuje nową instancję projektu i pobiera kalendarz według jego UID.

## Krok 2: Iteruj po wyjątkach kalendarza

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Tutaj przeglądamy każdy wyjątek kalendarza i drukujemy jego nazwę i powiązane typy dni.

## Krok 3: Zmodyfikuj wyjątki kalendarza

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

W tym kroku pokazano, jak modyfikować wyjątki kalendarza, dodając, usuwając lub aktualizując typy dni.

## Krok 4: Utwórz i manipuluj nowymi wyjątkami kalendarza

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

W tym ostatnim kroku tworzymy nowe wyjątki kalendarza i manipulujemy nimi, dodając i kopiując typy dni.

## Wniosek

 Podsumowując, zarządzanie kolekcjami typów dni w Aspose.Tasks dla .NET jest niezbędne do definiowania i modyfikowania wyjątków kalendarza tygodniowego w aplikacjach do zarządzania projektami. Postępując zgodnie ze szczegółowym przewodnikiem zawartym w tym samouczku, możesz efektywnie wykorzystać`DayTypeCollection` klasa do obsługi różnych operacji na kalendarzu.

## Często zadawane pytania

### P1: Czy można używać programu Aspose.Tasks for .NET do programowego tworzenia wykresów Gantta?

O1: Tak, Aspose.Tasks dla .NET udostępnia interfejsy API do tworzenia i manipulowania wykresami Gantta w aplikacjach .NET.

### P2: Czy Aspose.Tasks dla .NET jest kompatybilny zarówno z .NET Core, jak i .NET Framework?

O2: Tak, Aspose.Tasks dla .NET obsługuje zarówno .NET Core, jak i .NET Framework.

### P3: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

 Odpowiedź 3: Możesz uzyskać wsparcie odwiedzając stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) gdzie możesz zadawać pytania i kontaktować się z innymi użytkownikami.

### P4: Czy Aspose.Tasks dla .NET oferuje bezpłatną wersję próbną?

 A4: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/).

### P5: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla .NET?

 Odpowiedź 5: Tak, licencje tymczasowe można kupić w witrynie[Strona Aspose](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
