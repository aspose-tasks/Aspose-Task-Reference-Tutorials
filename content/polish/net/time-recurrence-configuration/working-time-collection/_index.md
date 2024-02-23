---
title: Opanowanie czasu pracy w Aspose.Tasks
linktitle: Zbiór czasów pracy w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Poznaj moc Aspose.Tasks dla .NET w efektywnym zarządzaniu harmonogramem projektów. Z łatwością dostosowuj kalendarze, ustalaj godziny pracy i usprawniaj swoje projekty.
type: docs
weight: 14
url: /pl/net/time-recurrence-configuration/working-time-collection/
---
## Wstęp
Czy chcesz opanować sztukę zarządzania czasem pracy w Aspose.Tasks dla .NET? Nie szukaj dalej! W tym przewodniku krok po kroku zagłębimy się w zawiłości gromadzenia czasu pracy za pomocą Aspose.Tasks, umożliwiając wydajną obsługę niestandardowych kalendarzy i usprawnianie harmonogramu projektów.
## Warunki wstępne
Zanim wyruszymy w tę podróż, upewnijmy się, że spełniliśmy następujące wymagania wstępne:
-  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Strona wydania Aspose.Tasks](https://releases.aspose.com/tasks/net/).
- Środowisko pracy: Skonfiguruj odpowiednie środowisko programistyczne, najlepiej używając IDE kompatybilnego z .NET.
## Importuj przestrzenie nazw
W swoim projekcie zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Podzielmy teraz samouczek na wiele kroków, aby zapewnić płynną naukę.
## Krok 1: Utwórz niestandardowy kalendarz
Zacznij od utworzenia nowego projektu i dodania do niego niestandardowego kalendarza:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Krok 2: Zdefiniuj dni robocze
Skonfiguruj domyślne dni robocze od poniedziałku do piątku:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Krok 3: Skonfiguruj sobotnie godziny pracy
Podaj godziny pracy w soboty:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Krok 4: Wydrukuj sobotnie okresy pracy
Wydrukuj skonfigurowane godziny pracy na sobotę:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Krok 5: Skonfiguruj niedzielne godziny pracy
Określ godziny pracy w niedziele:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Krok 6: Wydrukuj niedzielne okresy pracy
Wydrukuj skonfigurowane godziny pracy w niedzielę:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Krok 7: Dodaj niestandardowe dni do kalendarza
Uwzględnij skonfigurowaną sobotę i niedzielę w kalendarzu:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Krok 8: Przejdź przez czasy pracy
Przeglądaj czasy pracy i wyświetlaj je dla każdego dnia w kalendarzu:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Teraz, gdy pomyślnie wykonałeś wszystkie kroki, możesz wykorzystać moc Aspose.Tasks dla .NET w efektywnym zarządzaniu czasem pracy.
## Wniosek
Opanowanie gromadzenia czasów pracy w Aspose.Tasks umożliwia dostosowywanie kalendarzy projektów, zapewniając precyzyjne planowanie i efektywne wykorzystanie zasobów. Zanurz się w swoje projekty bez obaw, uzbrojony w wiedzę zdobytą z tego obszernego przewodnika.
## Często Zadawane Pytania
### Czy Aspose.Tasks nadaje się do zarządzania projektami na dużą skalę?
Tak, Aspose.Tasks jest przeznaczony do obsługi projektów o różnej wielkości, zapewniając solidne funkcje do wydajnego zarządzania projektami.
### Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami .NET?
Z pewnością! Aspose.Tasks bezproblemowo integruje się z innymi bibliotekami .NET, zwiększając jego wszechstronność i kompatybilność.
### Jak często aktualizowane jest Aspose.Tasks?
 Aspose.Tasks jest regularnie aktualizowany w celu uwzględnienia nowych funkcji, ulepszeń i ulepszeń kompatybilności. Sprawdź[strona wydania](https://releases.aspose.com/tasks/net/) w celu uzyskania najnowszych aktualizacji.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Tak, możesz przeglądać Aspose.Tasks w ramach bezpłatnej wersji próbnej, odwiedzając stronę[ten link](https://releases.aspose.com/).
### Gdzie mogę szukać wsparcia dla Aspose.Tasks?
 W razie jakichkolwiek pytań lub pomocy odwiedź stronę[Forum wsparcia Aspose.Tasks](https://forum.aspose.com/c/tasks/15).