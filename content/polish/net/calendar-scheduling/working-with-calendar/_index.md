---
title: Praca z kalendarzem w Aspose.Tasks
linktitle: Praca z kalendarzem w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zarządzaj kalendarzami projektów, obliczaj czas trwania i z łatwością obsługuj wyjątki za pomocą Aspose.Tasks dla .NET.
type: docs
weight: 10
url: /pl/net/calendar-scheduling/working-with-calendar/
---
## Wstęp

Aspose.Tasks dla .NET zapewnia zaawansowane funkcje do pracy z kalendarzami, umożliwiając programistom efektywne zarządzanie harmonogramami projektów i alokacją zasobów. W tym samouczku przyjrzymy się, jak wykorzystać Aspose.Tasks do interakcji z kalendarzami, obejmując podstawowe operacje, takie jak pobieranie informacji z kalendarza, definiowanie tygodni pracy, obliczanie godzin pracy i wiele innych.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz skonfigurowane następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
-  Instalacja Aspose.Tasks dla .NET. Jeśli nie jest zainstalowany, pobierz go z[Tutaj](https://releases.aspose.com/tasks/net/).
- Znajomość Visual Studio lub innego preferowanego środowiska programistycznego .NET.

## Importuj przestrzenie nazw

Zanim zaczniesz kodować, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Podzielmy teraz każdy przykład na wiele kroków w formie przewodnika krok po kroku:

## Krok 1: Pobierz informacje z kalendarza

Aby pobrać informacje z kalendarza z projektu, wykonaj następujące kroki:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Pobierz informacje z kalendarzy
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Wykonaj iterację po każdym kalendarzu w projekcie.
- Wydrukuj UID i nazwę każdego kalendarza.

## Krok 2: Przeczytaj informacje o tygodniach pracy

Aby odczytać informacje o tygodniach pracy z kalendarza, wykonaj następujące kroki:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Wykonaj iterację po każdym tygodniu pracy w kalendarzu.
- Wydrukuj nazwę, datę rozpoczęcia i datę zakończenia każdego tygodnia roboczego.
- Przeglądaj dni robocze i godziny pracy w każdym tygodniu.

## Krok 3: Przeczytaj właściwości kalendarza

Aby przeczytać właściwości kalendarzy projektu, wykonaj następujące kroki:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Wykonaj iterację po każdym kalendarzu w projekcie.
- Wydrukuj UID, nazwę i czy jest to kalendarz bazowy.
- Wydrukuj godziny pracy dla każdego typu dnia.

## Krok 4: Oblicz godziny pracy

Aby obliczyć godziny pracy dla zadania, wykonaj następujące kroki:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Uzyskaj szczegółowe informacje o zadaniu, takie jak kalendarz, data rozpoczęcia i data zakończenia.
- Oblicz godziny pracy, przeglądając każdy dzień i sprawdzając, czy jest to dzień roboczy.
- Podsumuj całkowity czas trwania w minutach.

## Krok 5: Zdefiniuj dni tygodnia dla kalendarza

Aby zdefiniować dni tygodnia dla kalendarza, wykonaj następujące kroki:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Wyjaśnienie:
- Utwórz nowy projekt i kalendarz.
- Dodaj domyślne dni robocze (od poniedziałku do czwartku) i niestandardowe godziny pracy w piątek.
- Ustaw sobotę i niedzielę jako dni wolne od pracy.

## Krok 6: Zapisz zaktualizowane dane kalendarza w MPP

Aby zapisać zaktualizowane dane kalendarza do pliku MPP, wykonaj następujące kroki:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://zakup.aspose.com/tymczasowa-licencja/.”);
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu i pobierz standardowy kalendarz.
- Modyfikuj dane kalendarza, takie jak wyjątki i godziny pracy.
- Zapisz zaktualizowany projekt ze zmodyfikowanymi danymi kalendarza.

## Krok 7: Oblicz datę zakończenia podzielonego zadania

Aby obliczyć datę zakończenia podzielonego zadania, wykonaj następujące kroki:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Wyjaśnienie:
- Załaduj plik projektu i pobierz podzielone zadanie.
- Pobierz kalendarz projektu.
- Oblicz datę zakończenia na podstawie niestandardowego czasu trwania.

## Krok 8: Pobierz wyjątki kalendarza

Aby pobrać informacje o wyjątkach kalendarza, wykonaj następujące kroki:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Wykonaj iterację po każdym kalendarzu i jego wyjątkach.
- Wydrukuj daty rozpoczęcia i zakończenia każdego wyjątku.

## Krok 9: Uzyskaj kalendarz zasobów podstawowych

Aby pracować z kalendarzem podstawowym kalendarza zasobu, wykonaj następujące kroki:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Dodaj zasób i jego kalendarz.
- Wydrukuj podstawową nazwę kalendarza dla wszystkich zasobów.

## Krok 10: Usuń kalendarz

Aby usunąć kalendarz z projektu, wykonaj następujące kroki:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Zdobądź kalendarz według nazwy.
- Usuń kalendarz.

## Krok 11: Uzyskaj datę zakończenia według rozpoczęcia i pracy

Aby obliczyć datę zakończenia według daty rozpoczęcia i pracy, wykonaj następujące kroki:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Zdobądź standardowy kalendarz.
- Określ datę rozpoczęcia i czas pracy.
- Oblicz datę zakończenia na podstawie daty rozpoczęcia i pracy.

## Krok 12: Rozpocznij następny dzień roboczy

Aby rozpocząć kolejny dzień roboczy za pomocą kalendarza, wykonaj następujące kroki:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Uzyskaj godzinę rozpoczęcia następnego dnia roboczego.

## Krok 13: Uzyskaj koniec poprzedniego dnia roboczego

Aby zakończyć poprzedni dzień roboczy za pomocą kalendarza, wykonaj następujące kroki:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Uzyskaj godzinę zakończenia poprzedniego dnia roboczego.

## Krok 14: Uzyskaj datę rozpoczęcia z zakończenia i czasu trwania

Aby uzyskać datę rozpoczęcia według daty zakończenia i czasu trwania, wykonaj następujące kroki:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Oblicz datę rozpoczęcia na podstawie daty zakończenia i czasu trwania.

## Krok 15: Uzyskaj godziny pracy

Aby uzyskać godziny pracy na konkretny dzień, wykonaj następujące kroki:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Uzyskaj godziny pracy dla określonej daty.

## Krok 16: Uzyskaj czasy pracy

Aby uzyskać godziny pracy na konkretny dzień, wykonaj następujące kroki:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Wyjaśnienie:
- Załaduj plik projektu.
- Pobierz kalendarz według UID.
- Uzyskaj godziny pracy dla określonej daty.

## Wniosek

Praca z kalendarzami w Aspose.Tasks for .NET jest kluczowa dla efektywnego zarządzania harmonogramami projektów. Dzięki dostarczonym przykładom i przewodnikom krok po kroku możesz łatwo manipulować danymi kalendarza, obliczać czas trwania zadań i efektywnie obsługiwać wyjątki. Integrując te funkcjonalności ze swoimi aplikacjami, możesz usprawnić procesy zarządzania projektami i zapewnić dokładne planowanie.

## Często zadawane pytania

### P1: Czy potrzebuję licencji, aby używać Aspose.Tasks dla .NET?

 Odpowiedź 1: Tak, potrzebujesz ważnej licencji, aby używać Aspose.Tasks dla .NET w swoich aplikacjach. Możesz kupić pełną licencję lub uzyskać 30-dniową licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).

### P2: Czy mogę programowo modyfikować wyjątki kalendarza?

O2: Tak, możesz programowo dodawać, aktualizować lub usuwać wyjątki kalendarza za pomocą Aspose.Tasks dla interfejsów API .NET.

### P3: Jak mogę obliczyć daty zakończenia zadań przy użyciu niestandardowych czasów trwania?

 O3: Aspose.Tasks dla .NET udostępnia metody takie jak`GetTaskFinishDateFromDuration()` do obliczania dat zakończenia zadań na podstawie niestandardowych czasów trwania.

### P4: Czy możliwe jest tworzenie kalendarzy niestandardowych, np. kalendarzy na nocną zmianę?

O4: Tak, możesz tworzyć niestandardowe kalendarze, takie jak kalendarze nocnej zmiany, używając Aspose.Tasks dla interfejsów API .NET.

### P5: Czy mogę uzyskać informacje o wyjątkach kalendarza z plików projektu?

O5: Tak, możesz łatwo uzyskać informacje o wyjątkach kalendarza z plików projektu za pomocą Aspose.Tasks dla .NET.