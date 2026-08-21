---
date: 2026-03-19
description: Dowiedz się, jak dodać zasób do projektu i obliczyć czas trwania zadania
  przy użyciu algorytmu drzewa Aspose.Tasks oraz przydzielić zasoby do zadań w .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Dodaj zasób do projektu za pomocą algorytmu drzewa w Aspose.Tasks
url: /pl/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj zasób do projektu przy użyciu algorytmu drzewa w Aspose.Tasks

## Wprowadzenie

W tym samouczku odkryjesz **jak dodać zasób do projektu** wykorzystując potężny algorytm drzewa dostarczany przez Aspose.Tasks dla .NET. Przejdziemy przez tworzenie hierarchii zadań, obliczanie czasu trwania zadania oraz przypisywanie zasobów do zadań — wszystko w przejrzysty, krok po kroku sposób, który możesz skopiować do własnego rozwiązania.

## Szybkie odpowiedzi
- **Co robi algorytm drzewa?** Przechodzi przez hierarchię zadań, aby efektywnie agregować wartości pracy.  
- **Jaką główną operację obejmuje ten przewodnik?** Dodawanie zasobu do projektu i aktualizacja sumarycznej pracy.  
- **Czy potrzebna jest licencja?** Wymagana jest tymczasowa lub pełna licencja do użytku produkcyjnego.  
- **Czy mogę używać tego z .NET Core?** Tak, Aspose.Tasks obsługuje .NET Framework i .NET Core.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego pliku projektu.

## Co oznacza „dodaj zasób do projektu” w Aspose.Tasks?

Dodanie zasobu do projektu oznacza utworzenie obiektu `Resource`, określenie jego typu (np. praca) i powiązanie go z jednym lub wieloma zadaniami za pomocą `ResourceAssignments`. Umożliwia to harmonogramowi obliczanie nakładu pracy, kosztów oraz całkowitego czasu trwania projektu.

## Dlaczego używać algorytmu drzewa do obliczeń pracy zasobów?

Algorytm drzewa przechodzi drzewo zadań raz, gromadząc pracę od zadań liściowych aż do ich zadań podsumowujących. To podejście jest znacznie bardziej wydajne niż iterowanie po każdym zadaniu osobno, szczególnie w dużych projektach z głęboką hierarchią. Zapewnia również, że wartości pracy podsumowującej pozostają zsynchronizowane z ich elementami podrzędnymi.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. **Visual Studio** – dowolna aktualna edycja (2019, 2022 lub nowsza).  
2. **Aspose.Tasks for .NET** – pobierz go z [tutaj](https://releases.aspose.com/tasks/net/).  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z klasami, obiektami i prostym LINQ.

## Importuj przestrzenie nazw

W swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby pracować z funkcjami Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Teraz rozbijmy każdy przykład na kilka kroków:

## Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Załaduj plik projektu do pamięci przy użyciu klasy `Project`.

## Krok 2: Zdefiniuj hierarchię zadań

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Zdefiniuj hierarchię zadań, dodając zadania nadrzędne i podrzędne.

## Krok 3: Ustaw właściwości zadania (w tym **oblicz czas trwania zadania**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Tutaj **obliczamy czas trwania zadania** poprzez konwersję godzin pracy na obiekt `Duration`, a następnie wyznaczamy datę zakończenia.

## Krok 4: Dodaj zasób (**przypisz zasoby do zadań**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Ten fragment **dodaje zasób do projektu** i **przypisuje zasoby do zadań**, dzięki czemu harmonogram wie, kto jest odpowiedzialny za pracę.

## Krok 5: Zastosuj algorytm drzewa

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Zainicjalizuj klasę `WorkAccumulator` i zastosuj algorytm drzewa, aby zebrać wspólną pracę w całej hierarchii.

## Krok 6: Zaktualizuj pracę zadania

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Zaktualizuj wartości pracy dla zadań na podstawie zebranych informacji.

## Typowe problemy i wskazówki

- **Brak ustawień kalendarza:** Jeśli data zakończenia wydaje się nieprawidłowa, upewnij się, że kalendarz projektu jest poprawnie skonfigurowany przed wywołaniem `GetFinishDateByStartAndWork`.  
- **Niezgodność typu zasobu:** Zawsze ustaw `Rsc.Type` na `ResourceType.Work` dla zasobów opartych na nakładzie pracy; w przeciwnym razie sumowanie pracy może zwrócić zero.  
- **Porada:** Po zaktualizowaniu pracy, wywołaj `project.Save("UpdatedProject.mpp")`, aby zapisać zmiany.

## Podsumowanie

Postępując zgodnie z tymi krokami, teraz wiesz, jak **dodać zasób do projektu**, **obliczyć czas trwania zadania** i **przypisać zasoby do zadań** przy użyciu algorytmu drzewa Aspose.Tasks. Ta metoda upraszcza zarządzanie hierarchią i utrzymuje dokładne wartości pracy podsumowującej przy minimalnej ilości kodu.

## FAQ

### Q1: Co to jest Aspose.Tasks dla .NET?

A1: Aspose.Tasks for .NET to potężne API, które umożliwia programistom programowe manipulowanie plikami Microsoft Project przy użyciu C#.

### Q2: Czy mogę pobrać darmową wersję próbną Aspose.Tasks dla .NET?

A2: Tak, możesz pobrać darmową wersję próbną Aspose.Tasks dla .NET z [tutaj](https://releases.aspose.com/).

### Q3: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

A3: Dokumentację Aspose.Tasks dla .NET znajdziesz [tutaj](https://reference.aspose.com/tasks/net/).

### Q4: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

A4: Aby uzyskać wsparcie związane z Aspose.Tasks dla .NET, możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Czy dostępna jest tymczasowa licencja do celów testowych?

A5: Tak, tymczasową licencję do celów testowych możesz uzyskać z [tutaj](https://purchase.aspose.com/temporary-license/).

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego podejścia z istniejącym dużym plikiem projektu?**  
A: Zdecydowanie tak. Algorytm drzewa działa na dowolnej instancji `Project`, niezależnie od rozmiaru.

**Q: Czy algorytm aktualizuje również wartości kosztów?**  
A: Przykład koncentruje się na pracy, ale możesz go rozszerzyć o koszty, sumując `Tsk.Cost` w podobny sposób.

**Q: Jakie wersje .NET są obsługiwane?**  
A: Aspose.Tasks obsługuje .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ oraz .NET 6+.

**Q: Jak obsłużyć wiele zasobów na zadanie?**  
A: Dodaj każdy zasób za pomocą `project.ResourceAssignments.Add(task, resource)`; akumulator automatycznie zsumuje ich pracę.

---

**Ostatnia aktualizacja:** 2026-03-19  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}