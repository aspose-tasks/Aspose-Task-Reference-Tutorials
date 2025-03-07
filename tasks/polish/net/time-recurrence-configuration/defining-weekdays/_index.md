---
title: Opanowanie dni powszednich w Aspose.Tasks dla .NET
linktitle: Definiowanie dni tygodnia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odkryj moc definiowania dni tygodnia w Aspose.Tasks .NET. Postępuj zgodnie z naszym szczegółowym samouczkiem, aby efektywnie zarządzać kalendarzami projektów, dostosowywać godziny pracy i nie tylko.
weight: 10
url: /pl/net/time-recurrence-configuration/defining-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie dni powszednich w Aspose.Tasks dla .NET

## Wstęp
Jeśli zagłębiasz się w świat zarządzania projektami przy użyciu Aspose.Tasks dla .NET, zrozumienie dni tygodnia i manipulowanie nimi jest kluczowym aspektem. Efektywne zarządzanie dniami tygodnia i dostosowywanie ich w kalendarzu projektu może znacząco wpłynąć na harmonogram projektu. W tym samouczku przeprowadzimy Cię przez proces definiowania dni tygodnia za pomocą Aspose.Tasks, dostarczając instrukcje krok po kroku i przykłady dla większej przejrzystości.
## Warunki wstępne
Zanim wyruszymy w tę podróż, upewnijmy się, że spełniamy następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C#.
-  Zainstalowana biblioteka Aspose.Tasks dla .NET. Jeśli nie, pobierz go z[Tutaj](https://releases.aspose.com/tasks/net/).
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Sprawdź równość w dni powszednie
```csharp
// Twój katalog dokumentów
String DataDir = "Your Document Directory";
// Załaduj plik projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Dostęp w dni powszednie
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Sprawdź równość w oparciu o różne właściwości
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Sklonuj dzień powszedni
```csharp
// Załaduj plik projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Utwórz głęboką kopię dnia powszedniego
var weekDay2 = weekDay1.Clone();
// Właściwości wyjściowe obu dni tygodnia
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Uzyskaj kod skrótu dnia powszedniego
```csharp
// Załaduj plik projektu
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Właściwości wyjściowe obu dni tygodnia
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Utwórz nowy kalendarz ze zdefiniowanymi dniami tygodnia
```csharp
// Utwórz nowy projekt
var project = new Project();
// Zdefiniuj kalendarz
var calendar = project.Calendars.Add("Calendar1");
// Dodaj dni robocze i dzień wyjątkowy
// Dodaj podobne instrukcje wyjściowe dla FromDate i ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Ustaw godziny pracy na piątek
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Ustaw domyślny czas pracy na dany dzień
```csharp
// Utwórz nowy projekt
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Dodaj domyślne godziny pracy od poniedziałku do piątku
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Powtórz tę czynność dla wtorku, środy, czwartku i piątku
// Ustaw dni wolne od pracy na sobotę i niedzielę
// Dodaj podobne instrukcje wyjściowe dla DayWorking, FromDate, ToDate i WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Wniosek
W tym samouczku omówiliśmy podstawowe aspekty definiowania dni tygodnia w Aspose.Tasks dla .NET. Manipulowanie dniami tygodnia jest kluczową umiejętnością skutecznego zarządzania projektami. Eksperymentuj z dostarczonymi przykładami, dostosuj je do potrzeb swojego projektu i odblokuj pełny potencjał Aspose.Tasks.
## Często zadawane pytania
### Czy mogę zdefiniować niestandardowe godziny pracy na każdy dzień?
Tak, możesz ustawić niestandardowe godziny pracy dla konkretnych dni tygodnia, korzystając z podanych przykładów.
### Czy można dodać do kalendarza wiele dni wyjątkowych?
Absolutnie. Zmodyfikuj kod w czwartym przykładzie, aby uwzględnić dodatkowe dni wyjątków.
### Jak usunąć konkretny dzień tygodnia z kalendarza?
Skorzystaj z odpowiednich metod udostępnianych przez bibliotekę Aspose.Tasks, aby w razie potrzeby usunąć dni tygodnia.
### Czy zmiany wprowadzone w dniach tygodnia są trwałe w pliku projektu?
Tak, wszelkie zmiany dni tygodnia zostaną odzwierciedlone w pliku projektu po zapisaniu.
### Czy mogę używać Aspose.Tasks z innymi językami programowania?
Aspose.Tasks obsługuje różne języki programowania, ale przykłady tutaj dotyczą specjalnie .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
