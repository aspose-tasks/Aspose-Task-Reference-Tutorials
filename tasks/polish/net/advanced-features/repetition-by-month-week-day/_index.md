---
date: 2026-04-01
description: Dowiedz się, jak ustawić powtarzalność w Aspose.Tasks dla .NET, dodać
  zadanie cykliczne i automatyzować zadania cykliczne według miesiąca, tygodnia i
  dnia.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Powtarzanie według miesiąca, tygodnia i dnia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak ustawić powtarzalność w Aspose.Tasks (Miesiąc, Tydzień, Dzień)
url: /pl/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić powtarzalność w Aspose.Tasks (Miesiąc, Tydzień, Dzień)

## Wprowadzenie

Jeśli potrzebujesz **jak ustawić powtarzalność** dla zadań w projekcie, Aspose.Tasks for .NET zapewnia czysty, programistyczny sposób dodawania definicji zadań powtarzalnych, które działają co miesiąc, tydzień lub dzień. W tym samouczku przeprowadzimy Cię przez rzeczywisty przykład, który pokaże, jak **dodać zadanie powtarzalne**, **zautomatyzować zadania powtarzalne** i zarządzać nimi bezpośrednio z kodu C#. Po zakończeniu będziesz gotowy, aby zintegrować tę funkcję z dowolnym rozwiązaniem do planowania lub zarządzania projektami.

## Szybkie odpowiedzi
- **Co oznacza „recurrence” w Aspose.Tasks?** Definiuje wzorzec (codzienny, tygodniowy, miesięczny), który automatycznie tworzy wystąpienia zadań w określonym przedziale dat.  
- **Która podstawowa metoda tworzy powtarzalność?** `RecurringTaskParameters` połączone z określonym `RecurrencePattern`.  
- **Czy potrzebuję licencji, aby uruchomić ten kod?** Wersja próbna działa w celach oceny; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę planować zadania tygodniowe zamiast miesięcznych?** Tak – zamień `MonthlyRecurrencePattern` na `WeeklyRecurrencePattern`.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 i późniejsze.

## Co to jest powtarzalność w Aspose.Tasks?

Powtarzalność to zestaw reguł, które instruują Aspose.Tasks, aby generował wystąpienia zadań w regularnych odstępach — codziennie, tygodniowo lub miesięcznie — bez ręcznego ich duplikowania. Ta funkcja jest niezbędna w projektach zawierających rutynowe działania, takie jak spotkania statusowe, inspekcje lub prace konserwacyjne.

## Dlaczego warto używać funkcji powtarzalności?

- **Oszczędzaj czas:** Nie ma potrzeby ręcznego kopiowania‑wklejania zadań.  
- **Redukuj błędy:** Biblioteka zapewnia spójne daty i czasy trwania.  
- **Elastyczność:** Łącz wzorce (np. „pierwsza niedziela co 2 miesiące”).  
- **Automatyzacja:** Idealne do generowania harmonogramów w pipeline’ach CI lub narzędziach raportujących.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

1. **Podstawowa znajomość C#** – będziesz pisać kilka linii kodu C#.
2. **Aspose.Tasks for .NET zainstalowane** – pobierz je ze [strony pobierania](https://releases.aspose.com/tasks/net/).
3. **Plik projektu .mpp** – użyjemy `Project1.mpp` jako pliku źródłowego.

## Importowanie przestrzeni nazw

Aby rozpocząć, zaimportuj wymagane przestrzenie nazw Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Krok 1: Załaduj plik projektu

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Tworzymy instancję `Project`, która wskazuje istniejący plik Microsoft Project.

### Krok 2: Zdefiniuj parametry zadania powtarzalnego

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

Tutaj **tworzymy parametry zadania powtarzalnego**:

- **TaskName** – nazwa generowanego zadania.
- **Duration** – jak długo trwa każde wystąpienie.
- **RecurrencePattern** – miesięczny wzorzec, który powtarza się co 2 miesiące w pierwszą niedzielę.
- **RecurrenceRange** – daty początkowa i końcowa określające zakres harmonogramu.

### Krok 3: Dodaj zadanie powtarzalne do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Ten wiersz **dodaje zadanie powtarzalne** do korzenia hierarchii projektu.

### Krok 4: Zapisz zaktualizowany projekt

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Projekt zostaje zapisany jako nowy plik `.mpp`, który teraz zawiera zautomatyzowany harmonogram.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **Zadanie nie pojawia się** | Zakres powtarzalności znajduje się poza datami projektu. | Sprawdź, czy wartości `Start` i `Finish` mieszczą się w kalendarzu projektu. |
| **Nieprawidłowy dzień tygodnia** | Niezgodność enumu `WeekDay`. | Użyj `DayOfWeek.Monday` … `DayOfWeek.Sunday` w razie potrzeby. |
| **Wyjątek licencyjny** | Uruchamianie bez ważnej licencji w środowisku produkcyjnym. | Zastosuj tymczasową lub pełną licencję przed zapisem. |

## Najczęściej zadawane pytania

### P1: Czy mogę dostosować wzorzec powtarzalności poza podanymi przykładami?

Tak, Aspose.Tasks for .NET oferuje rozbudowane opcje dostosowywania wzorców powtarzalności, umożliwiając ich dopasowanie do Twoich konkretnych wymagań.

### P2: Czy dostępna jest wersja próbna Aspose.Tasks for .NET?

Tak, możesz uzyskać darmową wersję próbną Aspose.Tasks for .NET ze [strony wydań](https://releases.aspose.com/).

### P3: Jak mogę uzyskać wsparcie dla Aspose.Tasks for .NET?

Możesz uzyskać pomoc i skontaktować się ze społecznością na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P4: Czy dostępne są tymczasowe licencje dla Aspose.Tasks for .NET?

Tak, możesz nabyć tymczasowe licencje ze [strony zakupu](https://purchase.aspose.com/temporary-license/) w celu testowania i oceny.

### P5: Gdzie mogę znaleźć pełną dokumentację Aspose.Tasks for .NET?

Możesz odwołać się do szczegółowej [dokumentacji](https://reference.aspose.com/tasks/net/) dostępnej na stronie Aspose, aby uzyskać dogłębne wskazówki dotyczące korzystania z biblioteki.

---

**Ostatnia aktualizacja:** 2026-04-01  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}