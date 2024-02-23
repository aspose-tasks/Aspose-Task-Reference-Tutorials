---
title: Obsługa miesięcznych wzorców powtarzania w Aspose.Tasks
linktitle: Obsługa miesięcznych wzorców powtarzania w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak obsługiwać miesięczne wzorce powtarzania w Aspose.Tasks dla .NET, korzystając z tego samouczka krok po kroku.
type: docs
weight: 18
url: /pl/net/advanced-concepts/monthly-recurrence-patterns/
---
## Wstęp

Aspose.Tasks dla .NET to potężny interfejs API, który umożliwia programistom programowe manipulowanie plikami Microsoft Project. Jedną z podstawowych funkcjonalności, jakie oferuje, jest możliwość sprawnej obsługi powtarzających się zadań. W tym samouczku zajmiemy się krok po kroku pracą z miesięcznymi wzorcami powtarzania przy użyciu Aspose.Tasks.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz zainstalowane następujące wymagania wstępne:

## Importuj przestrzenie nazw

Najpierw upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do swojego projektu .NET:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Podzielmy teraz proces obsługi miesięcznych wzorców powtarzania na wiele kroków:

## Krok 1: Zainicjuj projekt

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Krok 2: Ustaw parametry zadania cyklicznego

Zdefiniuj parametry zadania cyklicznego, w tym nazwę zadania, czas trwania i wzorzec powtarzania:

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

## Krok 3: Dodaj parametry do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

## Krok 4: Zapisz projekt

Zapisz zmodyfikowany projekt z zadaniem cyklicznym:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Wniosek

Obsługa miesięcznych wzorców powtarzania w Aspose.Tasks dla .NET jest prosta i wydajna. Wykonując kroki opisane w tym samouczku, możesz łatwo tworzyć zadania cykliczne z określonymi miesięcznymi interwałami i zakresami powtarzania.

## Często zadawane pytania

### P1: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?

O1: Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym MPP, MPT, XML i MPX.

### P2: Czy mogę bardziej dostosować wzór powtarzania?

Odpowiedź 2: Tak, Aspose.Tasks zapewnia szerokie opcje dostosowywania wzorców powtarzania, w tym dzienne, tygodniowe, miesięczne i roczne.

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?

 Odpowiedź 3: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks ze strony internetowej[Tutaj](https://releases.aspose.com/).

### P4: Jak mogę uzyskać wsparcie dla Aspose.Tasks?

 Odpowiedź 4: Możesz szukać pomocy i brać udział w dyskusjach na temat[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P5: Gdzie mogę kupić licencję na Aspose.Tasks?

 Odpowiedź 5: Możesz kupić licencję na Aspose.Tasks ze strony internetowej[Tutaj](https://purchase.aspose.com/buy)