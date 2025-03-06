---
title: Powtórzenie według miesiąca, tygodnia, dnia w Aspose.Tasks
linktitle: Powtórzenie według miesiąca, tygodnia, dnia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skonfigurować powtórzenia według miesiąca, tygodnia i dnia w Aspose.Tasks dla .NET, aby skutecznie automatyzować powtarzające się zadania.
weight: 26
url: /pl/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Powtórzenie według miesiąca, tygodnia, dnia w Aspose.Tasks

## Wstęp

W dziedzinie tworzenia oprogramowania, szczególnie w aplikacjach do zarządzania projektami, najważniejsza jest zdolność do efektywnej obsługi powtarzających się zadań. Aspose.Tasks dla .NET to potężna biblioteka zaprojektowana w celu usprawnienia tworzenia i zarządzania zadaniami projektowymi, w tym powtarzalnymi. Jedną z takich funkcjonalności udostępnianych przez Aspose.Tasks jest możliwość skonfigurowania powtórzeń według miesiąca, tygodnia i dnia, zapewniając wykonanie zadań zgodnie z harmonogramem bez ręcznej interwencji.

## Warunki wstępne

Zanim zagłębisz się w zawiłości konfigurowania powtórzeń według miesiąca, tygodnia i dnia za pomocą Aspose.Tasks dla .NET, upewnij się, że spełnione są następujące wymagania wstępne:

1. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna do zrozumienia i wdrożenia dostarczonych przykładów kodu.
   
2.  Instalacja Aspose.Tasks dla .NET: Upewnij się, że pobrałeś i zainstalowałeś bibliotekę Aspose.Tasks dla .NET. Bibliotekę można uzyskać z witryny[strona pobierania](https://releases.aspose.com/tasks/net/).

3. Dostęp do pliku projektu .mpp: Przygotuj plik Microsoft Project (.mpp), ponieważ będziemy go używać do zademonstrowania implementacji powtórzeń według miesiąca, tygodnia i dnia.

## Importuj przestrzenie nazw

Aby rozpocząć korzystanie z Aspose.Tasks dla .NET w aplikacji C#, musisz zaimportować niezbędne przestrzenie nazw. Oto jak możesz to zrobić:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Podzielmy dostarczony fragment kodu na wiele kroków, aby dokładnie zrozumieć każdą część.

## Krok 1: Załaduj plik projektu

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Ten krok polega na utworzeniu nowej instancji pliku`Project` class i ładowanie istniejącego pliku Microsoft Project (`Project1.mpp`) z określonego katalogu.

## Krok 2: Zdefiniuj parametry zadania cyklicznego

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Na tym etapie definiujemy parametry zadania cyklicznego. Określamy nazwę zadania, czas trwania, schemat powtarzania (co miesiąc) i zakres powtarzania (zakończenie w określonej dacie).

## Krok 3: Dodaj zadanie cykliczne do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Tutaj dodajemy zdefiniowane parametry zadania cyklicznego do zadania głównego projektu.

## Krok 4: Zapisz plik projektu

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Na koniec zapisujemy zmodyfikowany plik projektu z dodanym zadaniem cyklicznym.

## Wniosek

Podsumowując, konfigurowanie powtórzeń według miesiąca, tygodnia i dnia w Aspose.Tasks dla .NET to prosty proces, który umożliwia programistom efektywną automatyzację zarządzania powtarzającymi się zadaniami w ich projektach. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami C#, oszczędzając czas i wysiłek w zarządzaniu projektami.

## Często zadawane pytania

###P1: Czy mogę dostosować wzorzec powtarzania poza podanymi przykładami?

Odpowiedź 1: Tak, Aspose.Tasks dla .NET oferuje szerokie opcje dostosowywania wzorców powtarzania, umożliwiając dostosowanie ich do konkretnych wymagań.

###Q2: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?

 A2: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET ze strony[strona z wydaniami](https://releases.aspose.com/).

###Q3: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

 Odpowiedź 3: Możesz szukać pomocy i nawiązać kontakt ze społecznością na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###P4: Czy dostępne są licencje tymczasowe dla Aspose.Tasks dla .NET?

 Odpowiedź 4: Tak, możesz nabyć licencje tymczasowe od[strona zakupu](https://purchase.aspose.com/temporary-license/) do celów testowania i oceny.

###P5: Gdzie mogę znaleźć obszerną dokumentację Aspose.Tasks dla .NET?

 A5: Możesz zapoznać się ze szczegółami[dokumentacja](https://reference.aspose.com/tasks/net/) dostępne na stronie internetowej Aspose, gdzie znajdują się szczegółowe wskazówki dotyczące korzystania z biblioteki.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
