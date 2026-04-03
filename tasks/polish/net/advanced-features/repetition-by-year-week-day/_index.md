---
date: 2026-04-03
description: Dowiedz się, jak używać Aspose.Tasks do dodawania projektu z zadaniami
  powtarzającymi się i zapisywania projektu jako MPP. Ten przewodnik pokazuje funkcję
  Powtarzanie według roku, tygodnia i dnia krok po kroku.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Powtarzanie według roku, tygodnia, dnia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak używać Aspose.Tasks – Powtarzanie według roku, tygodnia i dnia
url: /pl/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Powtarzanie według roku, tygodnia, dnia w Aspose.Tasks

## Wprowadzenie

Kiedy potrzebujesz **how to use Aspose.Tasks** do obsługi złożonych harmonogramów powtarzalnych, biblioteka daje Ci precyzyjną kontrolę nad rocznymi wzorcami. W tym samouczku przejdziemy krok po kroku przez tworzenie zadania, które powtarza się w określony dzień tygodnia wybranego miesiąca, obejmując wiele lat. Po zakończeniu będziesz w stanie **add recurring task project** oraz **save project as MPP** przy użyciu kilku linii C#.

## Szybkie odpowiedzi
- **Co oznacza „Repetition by Year Week Day”?** Powtarza zadanie w wybrany dzień tygodnia (np. pierwszą niedzielę) danego miesiąca każdego roku.  
- **Które wersje .NET są obsługiwane?** Wszystkie nowoczesne wersje .NET Framework oraz .NET Core/5/6.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić zakres powtarzania?** Tak – możesz ustawić datę początkową, datę końcową lub stałą liczbę wystąpień.  
- **Czy wynikowy plik jest w formacie MPP?** Oczywiście – projekt jest zapisywany jako plik MPP gotowy do otwarcia w Microsoft Project.

## Czym jest funkcja „Repetition by Year Week Day”?

Funkcja pozwala zdefiniować roczne powtarzanie, które dotyczy konkretnego **dnia tygodnia** (np. niedzieli) oraz **pozycji** w miesiącu (pierwszy, drugi, ostatni itp.). Jest to idealne rozwiązanie dla zadań takich jak kwartalne przeglądy, coroczne audyty lub każde wydarzenie podążające za rytmem kalendarzowym.

## Dlaczego warto używać Aspose.Tasks do zadań powtarzalnych?

- **Precyzja** – Pełna kontrola nad miesiącami, dniami tygodnia i pozycjami porządkowymi.  
- **Kompatybilność** – Generuje natywne pliki MPP, które otwierają się bezbłędnie w Microsoft Project.  
- **Brak interfejsu COM** – Czyste API .NET, bez konieczności instalacji Office.  
- **Skalowalność** – Działa zarówno dla małych projektów, jak i harmonogramów na poziomie przedsiębiorstwa.

## Wymagania wstępne

Zanim zagłębisz się w kod, upewnij się, że masz:

1. **Podstawową wiedzę o .NET** – Znajomość C# i koncepcji programowania obiektowego.  
2. **Aspose.Tasks for .NET** – Pobierz go z [download link](https://releases.aspose.com/tasks/net/) i dodaj plik DLL do swojego projektu.  
3. **Dostęp do oficjalnej dokumentacji** – [documentation](https://reference.aspose.com/tasks/net/) zawiera wyczerpujące informacje o wszystkich klasach.  
4. **Środowisko IDE do programowania** – Visual Studio, Rider lub dowolny kompatybilny edytor .NET.

Teraz, gdy jesteś gotowy, zobaczmy implementację.

## Jak używać Aspose.Tasks do zadań powtarzalnych

### Importowanie wymaganych przestrzeni nazw

Najpierw wprowadź wymagane przestrzenie nazw, aby móc pracować z projektami, zadaniami i opcjami zapisu.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Krok 1: Inicjalizacja projektu i parametrów zadania

Utwórz nową instancję `Project`, a następnie zdefiniuj obiekt `RecurringTaskParameters`, który opisuje wzorzec powtarzania.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Porada:** Dostosuj `Month`, `WeekDay` i `Position`, aby pasowały do Twojego rzeczywistego harmonogramu.

### Krok 2: Dodaj parametry do projektu

Wstaw definicję zadania powtarzalnego do korzenia projektu.

```csharp
project.RootTask.Children.Add(parameters);
```

### Krok 3: Zapisz projekt jako MPP

Na koniec zapisz projekt do pliku MPP, aby można go było otworzyć w Microsoft Project lub dowolnym kompatybilnym przeglądarce.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> To demonstruje **save project as mpp** w jednej linii kodu.

## Typowe problemy i rozwiązania

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Brak zadań po otwarciu pliku MPP | Daty zakresu powtarzania znajdują się poza kalendarzem projektu | Sprawdź, czy daty `Start` i `Finish` mieszczą się w czasie pracy projektu |
| Wyjątek `ArgumentNullException` przy `Add` | `parameters` jest null lub nie w pełni zainicjowany | Upewnij się, że wszystkie wymagane właściwości (TaskName, Duration, RecurrencePattern) są ustawione |
| Wybrano niewłaściwy dzień tygodnia | Niezgodność wartości enum `WeekDay` | Użyj `DayOfWeek.Monday` … `DayOfWeek.Sunday` w razie potrzeby |

## Najczęściej zadawane pytania

**Q: Czy mogę dostosować wzorzec powtarzania poza podanym przykładem?**  
A: Tak, Aspose.Tasks pozwala łączyć `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` lub nawet własne obiekty `RecurrenceRange`, aby dopasować dowolny harmonogram.

**Q: Czy Aspose.Tasks for .NET jest kompatybilny z innym oprogramowaniem do zarządzania projektami?**  
A: Zdecydowanie – biblioteka odczytuje i zapisuje formaty MPP, XML i Primavera, umożliwiając płynną wymianę danych.

**Q: Jak mogę obsłużyć wyjątki lub modyfikacje zadań powtarzalnych?**  
A: Użyj klasy `ExceptionTask`, aby utworzyć nadpisania dla konkretnych wystąpień, lub edytuj `RecurringTaskParameters` i ponownie zapisz projekt.

**Q: Czy Aspose.Tasks obsługuje rozwiązania chmurowe?**  
A: Tak, możesz uruchomić API w Azure Functions, AWS Lambda lub dowolnej usłudze chmurowej kompatybilnej z .NET.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for .NET?**  
A: Tak, możesz uzyskać dostęp do darmowej wersji próbnej Aspose.Tasks for .NET ze [website](https://releases.aspose.com/), co pozwala przetestować funkcje przed podjęciem decyzji o zakupie.

**Q: Jak dodać zadanie powtarzalne do istniejącego projektu bez nadpisywania innych danych?**  
A: Wczytaj istniejący projekt za pomocą `new Project("Existing.mpp")`, dodaj `RecurringTaskParameters` do `RootTask.Children`, a następnie `Save` plik.

## Zakończenie

Opanowując **how to use Aspose.Tasks** w scenariuszu **Repetition by Year Week Day**, zyskasz możliwość **add recurring task project** wpisów, które idealnie pasują do rzeczywistych kalendarzy oraz **save project as MPP** dla płynnej współpracy. Włącz te fragmenty kodu do własnych rozwiązań, aby zwiększyć dokładność planowania i zredukować ręczną pracę.

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowane z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}