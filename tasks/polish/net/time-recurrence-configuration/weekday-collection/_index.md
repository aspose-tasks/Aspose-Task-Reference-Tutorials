---
title: Opanowanie dni powszednich w Aspose.Tasks
linktitle: Zbiór dni powszednich w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odkryj moc Aspose.Tasks dla .NET w łatwym zarządzaniu dniami powszednimi. Dostosuj dni robocze, usuń weekendy i z łatwością twórz specjalistyczne kalendarze.
weight: 11
url: /pl/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie dni powszednich w Aspose.Tasks

## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka ułatwiająca efektywne manipulowanie danymi zarządzania projektami. W tym samouczku przyjrzymy się kolekcji dni tygodnia w Aspose.Tasks, umożliwiając dostosowywanie dni roboczych, usuwanie weekendów i tworzenie wyspecjalizowanych kalendarzy spełniających wymagania projektu. Niezależnie od tego, czy jesteś doświadczonym programistą, czy nowicjuszem, ten przewodnik krok po kroku przeprowadzi Cię przez proces pracy z dniami powszednimi w Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Zainstaluj bibliotekę Aspose.Tasks dla .NET. Można go pobrać z[Strona pobierania Aspose.Tasks dla platformy .NET](https://releases.aspose.com/tasks/net/).
- Znajomość języka programowania C#.
- Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu C#:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Utwórz instancję projektu
Zainicjuj nowy projekt Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Krok 2: Uzyskaj dostęp do kalendarza
Pobierz kalendarz projektu:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Krok 3: Dostosuj dni powszednie
Wyczyść istniejące dni tygodnia i ustaw domyślne dni robocze:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Dodaj inne dni tygodnia w podobny sposób...
```
## Krok 4: Dodaj godziny pracy
Dodaj godziny pracy dla określonych dni tygodnia:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Krok 5: Wyświetl informacje z kalendarza
Wyprowadź szczegóły kalendarza do konsoli:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Wyświetl każdy dzień tygodnia i godziny pracy...
```
## Krok 6: Usuń weekendy
Usuń sobotę i niedzielę z dni powszednich:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Krok 7: Wyświetl zaktualizowane czasy pracy
Wyprowadź zaktualizowane czasy pracy po usunięciu weekendów:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Wyświetl każdy zaktualizowany dzień tygodnia i godziny pracy...
```
## Krok 8: Utwórz kalendarz 24-godzinny
Utwórz kalendarz 24-godzinny i skopiuj dni tygodnia:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Wniosek
W tym samouczku zbadaliśmy potężne możliwości Aspose.Tasks dla .NET w zarządzaniu dniami tygodnia w kalendarzach projektów. Od dostosowywania dni roboczych po tworzenie wyspecjalizowanych 24-godzinnych kalendarzy, Aspose.Tasks upraszcza proces, oferując elastyczność i kontrolę w zarządzaniu projektami.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z innymi językami programowania?
Odp.: Aspose.Tasks obsługuje przede wszystkim języki .NET, ale oferuje także wersje dla Java.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 O: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Strona z wydaniami Aspose.Tasks](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) o wsparcie społeczne lub rozważ zakup planu wsparcia.
### P: Gdzie mogę znaleźć obszerną dokumentację Aspose.Tasks dla .NET?
 Odp.: Patrz[Aspose.Tasks dla dokumentacji .NET](https://reference.aspose.com/tasks/net/) aby uzyskać szczegółowe informacje.
### P: Jak uzyskać tymczasową licencję na Aspose.Tasks dla .NET?
 Odpowiedź: Możesz nabyć tymczasową licencję od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
