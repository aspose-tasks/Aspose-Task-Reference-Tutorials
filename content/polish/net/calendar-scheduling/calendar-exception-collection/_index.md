---
title: Zbiór wyjątków kalendarza w Aspose.Tasks
linktitle: Zbiór wyjątków kalendarza w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie obsługiwać wyjątki kalendarza w projektach .NET za pomocą Aspose.Tasks, zapewniając dokładne planowanie i zarządzanie zasobami.
type: docs
weight: 13
url: /pl/net/calendar-scheduling/calendar-exception-collection/
---
## Wstęp

zarządzaniu projektami precyzyjne planowanie ma kluczowe znaczenie dla osiągnięcia sukcesu. Jednak rzeczywiste scenariusze często wymagają odstępstw od standardowych harmonogramów ze względu na święta, wydarzenia specjalne lub inne czynniki. Aspose.Tasks dla .NET zapewnia solidne rozwiązanie do zarządzania takimi wyjątkami poprzez funkcję zbierania wyjątków kalendarza. Ten samouczek przeprowadzi Cię krok po kroku przez proces korzystania z tej funkcji.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

1.  Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowaną bibliotekę. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
2. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna w zrozumieniu przykładów.
3. Środowisko programistyczne: skonfiguruj preferowane środowisko programistyczne, takie jak Visual Studio lub JetBrains Rider.

## Importuj przestrzenie nazw

Zanim zaczniesz pracować z Aspose.Tasks dla .NET, musisz zaimportować wymagane przestrzenie nazw do swojego projektu. Ten krok umożliwia dostęp do klas i metod niezbędnych do zarządzania wyjątkami kalendarza.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Podzielmy teraz podany przykład na kilka kroków:

## Krok 1: Załaduj projekt i pobierz kalendarz

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

Na tym etapie ładujemy plik projektu i pobieramy żądany kalendarz według jego UID.

## Krok 2: Usuń istniejące wyjątki i ustaw kalendarz standardowy

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Ten krok usuwa wszelkie istniejące wyjątki z kalendarza i ustawia go do standardowej konfiguracji.

## Krok 3: Zdefiniuj i dodaj wyjątek dotyczący czasu pracy

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

W tym kroku definiuje się wyjątek czasu pracy z określonymi datami początkowymi i końcowymi oraz czasem pracy w tych datach i dodaje go do kalendarza.

## Krok 4: Zdefiniuj i dodaj wyjątki dotyczące czasu wolnego od pracy

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// W razie potrzeby dodaj więcej wyjątków

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

W tym kroku definiuje się wyjątki w czasie wolnym od pracy, takie jak święta, i dodaje je do kalendarza.

## Krok 5: Wyświetl wyjątki kalendarza

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

W tym kroku zostaną wyświetlone dodane wyjątki kalendarza wraz z ich szczegółami.

## Krok 6: Usuń wszystkie wyjątki

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Na koniec ten krok usuwa wszystkie wyjątki z kalendarza.

## Wniosek

Zarządzanie wyjątkami w kalendarzu ma kluczowe znaczenie dla dokładnego planowania projektu. Aspose.Tasks dla .NET upraszcza to zadanie, udostępniając kompleksowy zestaw funkcji, w tym kolekcję wyjątków kalendarza. Wykonując kroki opisane w tym samouczku, możesz efektywnie obsługiwać różne scenariusze planowania w swoich projektach.

## Często zadawane pytania

### P1: Czy mogę dodać wiele wyjątków do jednego kalendarza?

 O1: Tak, możesz dodać wiele wyjątków do kalendarza za pomocą`AddRange` metoda.

### P2: Jak sobie poradzić z powtarzającymi się wyjątkami, takimi jak cotygodniowe święta?

Odpowiedź 2: Możesz programowo obliczyć powtarzające się wyjątki i dodać je do kalendarza przy użyciu logiki niestandardowej.

### P3: Czy można importować wyjątki kalendarza ze źródeł zewnętrznych?

Odpowiedź 3: Tak, możesz czytać wyjątki kalendarza ze źródeł zewnętrznych, takich jak bazy danych lub pliki CSV i integrować je ze swoim projektem.

### P4: Co się stanie, jeśli w kalendarzu pojawią się nakładające się wyjątki?

O4: Aspose.Tasks dla .NET umożliwia obsługę nakładających się wyjątków poprzez definiowanie priorytetów lub rozwiązywanie konfliktów w oparciu o wymagania projektu.

### P5: Czy mogę dostosować godziny pracy na każdy dzień w ramach wyjątku?

Odpowiedź 5: Tak, możesz określić niestandardowe godziny pracy dla poszczególnych dni w ramach wyjątku, aby uwzględnić określone potrzeby związane z harmonogramem.