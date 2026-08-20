---
date: 2026-03-08
description: Dowiedz się, jak ustawić wyświetlanie etykiet i dostosować etykietę dnia
  w zarządzaniu projektami przy użyciu Aspose.Tasks dla .NET, poprawiając czytelność
  i przejrzystość.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak ustawić wyświetlanie etykiet w Aspose.Tasks dla .NET
url: /pl/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić wyświetlanie etykiet w Aspose.Tasks dla .NET

## Wprowadzenie

Kiedy budujesz rozwiązanie do zarządzania projektami przy użyciu **Aspose.Tasks for .NET**, możliwość **ustawiania etykiet** jest niezbędna, aby harmonogramy były łatwe do odczytania. Niezależnie od tego, czy potrzebujesz precyzji co do minuty, czy przeglądu rocznego na wysokim poziomie, dostosowanie wyświetlania etykiet pozwala przedstawić oś czasu dokładnie tak, jak oczekują tego interesariusze. W tym samouczku przeprowadzimy Cię krok po kroku przez proces ustawiania wyświetlania etykiet dla minut, godzin, dni, tygodni, miesięcy i lat, a także pokażemy, jak **dostosować formatowanie etykiety dnia** dla maksymalnej przejrzystości.

## Szybkie odpowiedzi
- **Co oznacza „how to set label”?** Odnosi się do konfigurowania właściwości `DisplayOptions`, które kontrolują, jak jednostki czasu wyświetlają się w pliku projektu.  
- **Jaką etykietę mogę zmienić?** Minuty, godziny, dni, tygodnie, miesiące i lata można konfigurować.  
- **Czy potrzebna jest licencja?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego; darmowa wersja próbna działa w testach.  
- **Czy jest to wspierane w .NET Core?** Tak, API działa z .NET Core, .NET 5/6 oraz pełnym .NET Framework.  
- **Czy mogę zmienić etykietę w czasie działania?** Oczywiście – możesz modyfikować opcje wyświetlania w dowolnym momencie przed zapisaniem projektu.

## Co to jest wyświetlanie etykiet w Aspose.Tasks?

Wyświetlanie etykiet określa tekstową reprezentację jednostek czasu (minuta, godzina, dzień itp.) na wykresie Gantta i skali czasu. Ustawiając odpowiednią właściwość `DisplayOptions`, instruujesz Aspose.Tasks, jak renderować te jednostki, co może znacząco poprawić czytelność projektu.

## Dlaczego dostosowywać wyświetlanie etykiet?

- **Poprawiona czytelność:** Interesariusze mogą natychmiast zrozumieć szczegółowość harmonogramu.  
- **Spójne raportowanie:** Dopasowuje wyjście wizualne do standardów korporacyjnych (np. używanie „Mo” dla miesięcy).  
- **Elastyczność:** Przełączaj się między szczegółowymi a wysokopoziomowymi widokami bez zmiany podstawowych danych harmonogramu.

## Wymagania wstępne

1. **Znajomość C#** – podstawowa znajomość składni C# i struktury projektu .NET.  
2. **Aspose.Tasks for .NET** – pobierz i zainstaluj bibliotekę z [tutaj](https://releases.aspose.com/tasks/net/).  
3. **Środowisko programistyczne** – Visual Studio, VS Code lub dowolne IDE obsługujące rozwój w .NET.

## Importowanie przestrzeni nazw

Przed rozpoczęciem zaimportuj wymagane przestrzenie nazw:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Jak ustawić wyświetlanie etykiet dla minut

### 1. Wyświetlanie etykiet minutowych

Aby ustawić etykietę minut, użyj właściwości `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Jak ustawić wyświetlanie etykiet dla godzin

### 2. Wyświetlanie etykiet godzinowych

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Dostosuj wyświetlanie etykiety dnia

### 3. Wyświetlanie etykiet dniowych

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Jak ustawić wyświetlanie etykiet dla tygodni

### 4. Wyświetlanie etykiet tygodniowych

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Jak ustawić wyświetlanie etykiet dla miesięcy

### 5. Wyświetlanie etykiet miesięcznych

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Jak ustawić wyświetlanie etykiet dla lat

### 6. Wyświetlanie etykiet rocznych

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Typowe pułapki i wskazówki

- **Wskazówka:** Zawsze ustaw wyświetlanie etykiet *przed* zapisaniem projektu; zmiany wprowadzone po zapisaniu nie będą odzwierciedlone w pliku.  
- **Pułapka:** Użycie nieobsługiwanej wartości wyliczenia spowoduje wyrzucenie `ArgumentException`. Trzymaj się dostarczonych wyliczeń `*LabelDisplay`.  
- **Wskazówka:** Jeśli potrzebujesz różnych stylów etykiet dla oddzielnych widoków, utwórz osobne instancje `Project` lub sklonuj obiekt `DisplayOptions`.

## Podsumowanie

Opanowując **ustawianie etykiet** w Aspose.Tasks, zyskujesz precyzyjną kontrolę nad wizualną prezentacją harmonogramów projektów. Niezależnie od tego, czy dostosowujesz etykietę dnia dla codziennego boardu scrum, czy modyfikujesz etykietę roku dla wieloletniej mapy drogowej, te ustawienia pomagają dostarczyć jaśniejszą, bardziej profesjonalną dokumentację projektu.

## FAQ

### P1: Czy mogę dostosować wyświetlanie etykiet dla konkretnych sekcji projektu?

A1: Tak, Aspose.Tasks for .NET umożliwia szczegółową kontrolę nad wyświetlaniem etykiet, pozwalając na dostosowanie ich dla konkretnych sekcji projektu w razie potrzeby.

### P2: Czy Aspose.Tasks jest kompatybilny z popularnymi frameworkami .NET?

A2: Tak, Aspose.Tasks for .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Framework.

### P3: Czy mogę dynamicznie zmieniać wyświetlanie etykiet w zależności od wymagań projektu?

A3: Absolutnie, elastyczność Aspose.Tasks for .NET pozwala na dynamiczne dostosowywanie wyświetlania etykiet w zależności od zmieniających się wymagań projektu.

### P4: Czy istnieją jakiekolwiek ograniczenia w dostosowywaniu wyświetlania etykiet?

A4: Aspose.Tasks for .NET oferuje rozbudowane opcje dostosowywania wyświetlania etykiet, z minimalnymi ograniczeniami, zapewniając użytkownikom dużą elastyczność.

### P5: Czy Aspose.Tasks wspiera integrację z innymi narzędziami do zarządzania projektami?

A5: Tak, Aspose.Tasks oferuje płynne możliwości integracji, ułatwiając interoperacyjność z innymi narzędziami i platformami do zarządzania projektami.

---

**Ostatnia aktualizacja:** 2026-03-08  
**Testowane z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}