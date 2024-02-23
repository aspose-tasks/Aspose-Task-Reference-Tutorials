---
title: Powtórzenie według miesiąca dnia w Aspose.Tasks
linktitle: Powtórzenie według miesiąca dnia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać powtarzającymi się zadaniami w projektach .NET za pomocą Aspose.Tasks. Przewodnik krok po kroku dotyczący obsługi powtórzeń według dni miesiąca.
type: docs
weight: 25
url: /pl/net/advanced-features/repetition-by-month-day/
---
## Wstęp

W dziedzinie programowania .NET Aspose.Tasks jest potężnym narzędziem do zarządzania zadaniami i harmonogramami projektów. Oferuje mnóstwo funkcjonalności usprawniających przepływ pracy w zarządzaniu projektami, w tym obsługę zadań powtarzalnych. Powtarzanie według dni miesiąca jest powszechnym wymogiem w planowaniu projektów, a Aspose.Tasks zapewnia solidną obsługę tego scenariusza.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

1. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest konieczna, aby zrozumieć koncepcje omówione w tym samouczku.
2. Instalacja Aspose.Tasks dla .NET: Upewnij się, że zainstalowałeś Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Zintegrowane środowisko programistyczne (IDE): Zainstaluj w swoim systemie środowisko IDE, takie jak Visual Studio, aby zapewnić wygodę kodowania.

## Importuj przestrzenie nazw

swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Podzielmy podany przykład kodu na format przewodnika krok po kroku:

## Krok 1: Załaduj plik projektu

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Ta linia kodu inicjuje nową instancję klasy`Project` class, ładując plik projektu o nazwie „Project1.mpp”.

## Krok 2: Zdefiniuj parametry zadania cyklicznego

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

W tej sekcji zdefiniowano parametry zadania cyklicznego, w tym jego nazwę, czas trwania, wzorzec powtarzania i zakres powtarzania.

## Krok 3: Dodaj zadanie do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Tutaj dodajemy do projektu parametry zadania cyklicznego.

## Krok 4: Zapisz plik projektu

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Na koniec zmodyfikowany projekt zostaje zapisany z dodanym zadaniem cyklicznym.

## Wniosek

tym samouczku omówiliśmy, jak obsługiwać powtarzanie według dni miesiąca w Aspose.Tasks dla .NET. Postępując zgodnie z podanymi krokami, możesz efektywnie zarządzać powtarzającymi się zadaniami w ramach harmonogramów projektów.

## Często zadawane pytania

### P1: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami .NET?

O1: Aspose.Tasks obsługuje różne wersje platformy .NET, zapewniając kompatybilność w różnych środowiskach.

### P2: Czy mogę bardziej dostosować wzór powtarzania?

Odpowiedź 2: Tak, Aspose.Tasks oferuje szerokie opcje dostosowywania w celu definiowania wzorców powtarzania zgodnie z konkretnymi wymaganiami projektu.

### P3: Czy Aspose.Tasks zapewnia wsparcie dla innych funkcjonalności zarządzania projektami?

Odpowiedź 3: Oczywiście, Aspose.Tasks oferuje szeroką gamę funkcji do zarządzania projektami, w tym śledzenie zadań, alokację zasobów i generowanie wykresów Gantta.

### P4: Czy dostępna jest wersja próbna Aspose.Tasks?

 A4: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/) aby poznać możliwości Aspose.Tasks przed podjęciem decyzji o zakupie.

### P5: Gdzie mogę szukać pomocy, jeśli napotkam problemy lub mam pytania?

 A5: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) szukać wsparcia ze strony społeczności lub zespołu Aspose.