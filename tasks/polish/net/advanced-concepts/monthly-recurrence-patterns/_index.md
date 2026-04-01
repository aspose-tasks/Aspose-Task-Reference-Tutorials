---
date: 2026-03-08
description: Dowiedz się, jak utworzyć comiesięczne zadanie powtarzalne w Aspose.Tasks
  dla .NET, korzystając z tego samouczka krok po kroku.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak utworzyć miesięczne zadanie cykliczne w Aspose.Tasks
url: /pl/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz Miesięczne Zadanie Powtarzalne przy użyciu Aspose.Tasks

## Wprowadzenie

Aspose.Tasks for .NET umożliwia programowe manipulowanie plikami Microsoft Project, a jednym z najczęstszych rzeczywistych potrzeb jest **tworzenie miesięcznych zadań powtarzalnych**. Niezależnie od tego, czy budujesz narzędzie do śledzenia projektów, automatyzujesz przydział zasobów, czy generujesz powtarzalne zadania konserwacyjne, ten samouczek przeprowadzi Cię krok po kroku przez dodanie miesięcznego wzorca powtarzania do zadania.

W kolejnych sekcjach zobaczysz, jak skonfigurować projekt, zdefiniować parametry powtarzania i ostatecznie zapisać zaktualizowany plik — wszystko z jasnymi wyjaśnieniami i praktycznymi wskazówkami.

## Szybkie odpowiedzi
- **Co oznacza „miesięczne zadanie powtarzalne”?** Zadanie, które powtarza się w określonym wzorcu dzień‑lub‑tydzień każdego miesiąca.  
- **Która klasa API obsługuje powtarzanie?** `RecurringTaskParameters` razem z `MonthlyRecurrencePattern`.  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna wystarcza do oceny; licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zmienić interwał?** Tak – ustaw `RepetitionInterval` na liczbę miesięcy pomiędzy wystąpieniami.  
- **Jakie formaty plików są obsługiwane?** Zarówno pliki projektu `.mpp`, jak i `.xml` mogą być wczytywane i zapisywane.

## Czym jest Miesięczny Wzorzec Powtarzania?

Miesięczny wzorzec powtarzania informuje Microsoft Project (i Aspose.Tasks), jak często zadanie ma się powtarzać każdego miesiąca. Można określić stały dzień miesiąca (np. 1.) lub pozycję względną (np. ostatni piątek). API przetwarza te reguły na podstawową strukturę pliku Project.

## Dlaczego warto używać Aspose.Tasks w tym przypadku?

- **Pełna kontrola** – Brak ograniczeń interfejsu; definiujesz każdy aspekt wzorca w kodzie.  
- **Cross‑platform** – Działa na .NET Framework, .NET Core oraz .NET 5/6+.  
- **Brak wymaganego Microsoft Project** – Generuj lub modyfikuj pliki na serwerze lub w potoku CI.  

## Wymagania wstępne

- .NET 6 (lub .NET 5/Framework 4.7+) zainstalowany.  
- Pakiet NuGet Aspose.Tasks for .NET dodany do projektu.  
- Przykładowy plik Project (`Project1.mpp`) umieszczony w znanym folderze (`DataDir`).  

## Importowanie przestrzeni nazw

First, import the namespaces required for working with tasks and saving projects:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Krok 1: Inicjalizacja projektu

Utwórz instancję `Project`, która wskazuje na istniejący plik `.mpp`. Ładuje to plik do pamięci, abyś mógł go modyfikować.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Wskazówka:** Jeśli plik nie istnieje, Aspose.Tasks automatycznie utworzy nowy pusty projekt.

## Krok 2: Ustaw parametry zadania powtarzalnego

Zdefiniuj szczegóły zadania powtarzalnego, w tym jego nazwę, czas trwania oraz miesięczny wzorzec, który chcesz zastosować.

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

- `DayPosition = 1` oznacza, że zadanie występuje w **pierwszym dniu** miesiąca.  
- `RepetitionInterval = 2` sprawia, że zadanie powtarza się **co dwa miesiące**.  
- `Start` i `Finish` definiują ogólne okno, w którym powtarzanie jest aktywne.

## Krok 3: Dodaj parametry do projektu

Dołącz obiekt `RecurringTaskParameters` do kolekcji dzieci zadania głównego. To skutecznie tworzy zadanie powtarzalne w hierarchii projektu.

```csharp
project.RootTask.Children.Add(parameters);
```

## Krok 4: Zapisz projekt

Zachowaj zmiany, zapisując projekt do nowego pliku. Możesz wybrać dowolny obsługiwany format; tutaj używamy natywnego formatu `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Po uruchomieniu kodu otwórz powstały plik w Microsoft Project, aby zobaczyć utworzone miesięczne zadanie powtarzalne.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| Zadanie nie pojawia się po zapisaniu | Projekt nie odświeżony w UI | Ponownie otwórz plik lub wywołaj `project.UpdateTaskLinks()` przed zapisem. |
| Nieprawidłowa data rozpoczęcia | `Start` ustawiony na weekend | Użyj `DateTime` przypadającego na dzień roboczy lub dostosuj kalendarz. |
| Ignorowany interwał powtarzania | Użycie `ByMonthDayRepetition` z `DayPosition` = 0 | Upewnij się, że `DayPosition` wynosi 1‑31. |

## Podsumowanie

Postępując zgodnie z tymi krokami, teraz wiesz, jak **tworzyć miesięczne zadania powtarzalne** przy użyciu Aspose.Tasks dla .NET. API zapewnia szczegółową kontrolę nad interwałami powtarzania, zakresami start/finish oraz konkretnym wzorcem dni, umożliwiając automatyzację złożonych scenariuszy planowania projektów.

## FAQ

### Q1: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?

A1: Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym MPP, MPT, XML i MPX.

### Q2: Czy mogę dalej dostosować wzorzec powtarzania?

A2: Tak, Aspose.Tasks oferuje rozbudowane opcje dostosowywania wzorców powtarzania, w tym dzienne, tygodniowe, miesięczne i roczne.

### Q3: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?

A3: Tak, możesz uzyskać darmową wersję próbną Aspose.Tasks ze strony [here](https://releases.aspose.com/).

### Q4: Jak mogę uzyskać wsparcie dla Aspose.Tasks?

A4: Możesz szukać pomocy i uczestniczyć w dyskusjach na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Gdzie mogę kupić licencję na Aspose.Tasks?

A5: Licencję na Aspose.Tasks możesz kupić na stronie [here](https://purchase.aspose.com/buy).

## Często zadawane pytania

**Q: Czy mogę używać tego kodu w aplikacji .NET Core?**  
A: Oczywiście. Aspose.Tasks for .NET w pełni obsługuje .NET Core 3.1 i późniejsze wersje.

**Q: Jak zmienić powtarzanie na „ostatni dzień roboczy miesiąca”?**  
A: Użyj `ByMonthDayRepetition` z `DayPosition = -1` (wartości ujemne liczą od końca miesiąca) i odpowiednio ustaw `WeekDay`.

**Q: Co się stanie, jeśli zakres powtarzania przekracza kalendarz projektu?**  
A: API respektuje kalendarz projektu; wystąpienia przypadające w dni niepracujące są pomijane lub przenoszone zgodnie z ustawieniami kalendarza.

**Q: Czy można usunąć konkretne wystąpienie zadania powtarzalnego?**  
A: Tak. Po dodaniu zadania powtarzalnego możesz pobrać poszczególne wystąpienia za pomocą `Task.GetOccurrences()` i usunąć te, które nie są potrzebne.

**Q: Czy Aspose.Tasks automatycznie obsługuje różnice stref czasowych?**  
A: Biblioteka przechowuje daty w UTC; w razie potrzeby możesz przekształcić je na czas lokalny przy użyciu standardowych metod .NET `DateTime`.

**Ostatnia aktualizacja:** 2026-03-08  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}