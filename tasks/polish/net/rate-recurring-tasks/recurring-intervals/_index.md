---
title: Bezproblemowe powtarzające się interwały projektu MS w Aspose.Tasks
linktitle: Zarządzanie powtarzającymi się interwałami w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Odkryj, jak bez wysiłku zarządzać powtarzającymi się interwałami w MS Project przy użyciu Aspose.Tasks dla .NET.
type: docs
weight: 12
url: /pl/net/rate-recurring-tasks/recurring-intervals/
---
## Wstęp
Czy chcesz efektywnie zarządzać powtarzającymi się interwałami w plikach Microsoft Project za pomocą Aspose.Tasks dla .NET? Ten kompleksowy samouczek poprowadzi Cię krok po kroku przez proces, dzięki czemu możesz bez wysiłku poradzić sobie z powtarzającymi się interwałami w swoich projektach. Zanim przejdziesz do samouczka, przyjrzyjmy się kilku wymaganiom wstępnym, aby upewnić się, że jesteś gotowy, aby zacząć.
## Warunki wstępne
Przed kontynuowaniem tego samouczka upewnij się, że posiadasz następujące elementy:
1. Znajomość programowania C#: Wymagana jest podstawowa znajomość języka programowania C# i jego składni.
2. Zainstalowany program Visual Studio: Upewnij się, że w systemie zainstalowano program Visual Studio do kodowania i kompilowania aplikacji .NET.
3. Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET. Możesz to dostać od[Tutaj](https://releases.aspose.com/tasks/net/).

## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności udostępnianych przez bibliotekę Aspose.Tasks dla .NET.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Podzielmy teraz każdy przykład na wiele kroków i szczegółowo je wyjaśnijmy.
## Krok 1: Zainicjuj obiekt projektu:
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Tutaj inicjujemy nową instancję klasy`Project` class, podając ścieżkę do pliku Microsoft Project.
## Krok 2: Ustaw datę statusu:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Ten krok ustawia datę statusu projektu na datę jego rozpoczęcia.
## Krok 3: Uzyskaj dostęp do widoku wykresu Gantta:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Uzyskujemy dostęp do widoku Wykresu Gantta projektu.
## Krok 4: Przeczytaj linię postępu:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Ten krok pobiera powtarzający się interwał dla linii postępu z widoku Wykres Gantta.
## Krok 5: Wyświetlanie informacji o interwałach:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Tutaj wyświetlamy informacje o interwale, numerze tygodnia tygodnia i dniach tygodnia.
## Krok 6: Zdefiniuj ponownie interwał powtarzania:
```csharp
var newInterval = new RecurringInterval();
```
 Tworzymy nową instancję`RecurringInterval` w celu ponownego zdefiniowania powtarzającego się interwału.
## Krok 7: Ustaw miesięczne linie postępu:
```csharp
// Ustaw miesięczne linie postępu według dnia.
interval.MonthlyDay = true;
// Ustaw numer dnia miesięcznych linii postępu.
interval.MonthlyDayDayNumber = 1;
// Ustaw numer miesiąca miesięcznych linii postępu.
interval.MonthlyDayMonthNumber = 1;
// Ustaw linie postępu według pierwszego lub ostatniego predefiniowanego dnia.
interval.MonthlyFirstLast = true;
// Ustaw typ pierwszego lub ostatniego dnia miesięcznych linii postępu.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Ustaw liczbę miesięcznych linii postępu.
interval.MonthlyFirstLastMonthNumber = 1;
```
Te kroki konfigurują miesięczne linie postępu zgodnie z określonymi parametrami.
## Krok 8: Zaktualizuj linie postępu:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Aktualizujemy linie postępu w widoku Wykresu Gantta o nowo zdefiniowany okres powtarzania.
## Krok 9: Zapisz projekt jako plik PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Na koniec zapisujemy projekt ze zaktualizowanym interwałem cyklicznym jako plik PDF.

## Wniosek
Podsumowując, zarządzanie powtarzającymi się interwałami w plikach Microsoft Project przy użyciu Aspose.Tasks dla .NET stało się proste dzięki kompleksowym funkcjom zapewnianym przez bibliotekę. Postępując zgodnie ze szczegółowym przewodnikiem opisanym w tym samouczku, możesz skutecznie radzić sobie z powtarzającymi się interwałami w swoich projektach, zwiększając produktywność i organizację.
### Często zadawane pytania
### Czy mogę używać Aspose.Tasks dla .NET z innymi językami programowania?
Tak, Aspose.Tasks dla .NET może być używany z dowolnym językiem obsługiwanym przez .NET, takim jak C# i VB.NET.
### Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?
 Możesz uzyskać pomoc na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### Czy mogę kupić tymczasową licencję na Aspose.Tasks dla .NET?
 Tak, możesz kupić tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć pełną dokumentację Aspose.Tasks dla .NET?
 Można znaleźć pełną dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).