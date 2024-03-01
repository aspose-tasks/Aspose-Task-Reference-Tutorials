---
title: Dostosuj tygodnie pracy w Aspose.Tasks
linktitle: Zbiór tygodni pracy w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak dostosować tygodnie pracy w Aspose.Tasks dla .NET. Przewodnik krok po kroku dotyczący tworzenia spersonalizowanych kalendarzy projektów. Pobierz teraz!
type: docs
weight: 17
url: /pl/net/time-recurrence-configuration/workweek-collection/
---
## Wstęp
Witamy w naszym samouczku na temat tworzenia niestandardowego tygodnia pracy przy użyciu Aspose.Tasks dla .NET! W tym przewodniku krok po kroku przeprowadzimy Cię przez proces definiowania spersonalizowanego tygodnia pracy dla kalendarza w Twoim projekcie. Aspose.Tasks to potężna biblioteka, która umożliwia programistom efektywną pracę z dokumentami Microsoft Project w aplikacjach .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Visual Studio: Upewnij się, że na komputerze jest zainstalowany program Visual Studio.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.
## Importuj przestrzenie nazw
W projekcie C# pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Utwórz projekt i kalendarz
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Krok 2: Zdefiniuj niestandardowy tydzień pracy
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Krok 3: Ustaw dni robocze
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Krok 4: Wyświetl informacje o tygodniach pracy
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Ten kompleksowy przewodnik umożliwia efektywne tworzenie niestandardowych tygodni pracy i zarządzanie nimi za pomocą Aspose.Tasks dla .NET.
## Wniosek
Podsumowując, Aspose.Tasks dla .NET zapewnia solidne rozwiązanie do obsługi kalendarzy projektów z niestandardowymi tygodniami pracy. Wykonując ten samouczek, nauczyłeś się tworzyć i wyświetlać informacje o niestandardowych tygodniach pracy w swoim projekcie.
## Często zadawane pytania
### Czy mogę mieć wiele niestandardowych tygodni pracy w jednym projekcie?
Tak, możesz dodać wiele niestandardowych tygodni pracy do kalendarza projektu.
### Jak mogę zmodyfikować istniejące tygodnie pracy?
 Skorzystaj z podanego`WorkWeek`właściwości i metody modyfikacji istniejących tygodni pracy.
### Czy Aspose.Tasks jest kompatybilny z .NET Core?
Tak, Aspose.Tasks obsługuje .NET Core.
### Czy mogę wyeksportować projekt z niestandardowymi tygodniami pracy do formatu pliku Microsoft Project?
Absolutnie Aspose.Tasks umożliwia zapisanie projektu w różnych formatach, w tym Microsoft Project.
### Gdzie mogę szukać pomocy w przypadku zapytań związanych z Aspose.Tasks?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za jakiekolwiek wsparcie lub pomoc.