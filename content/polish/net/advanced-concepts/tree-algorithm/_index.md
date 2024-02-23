---
title: Korzystanie z algorytmu drzewa w Aspose.Tasks
linktitle: Korzystanie z algorytmu drzewa w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skutecznie manipulować hierarchiami zadań w projektach .NET za pomocą algorytmu drzewa Aspose.Tasks.
type: docs
weight: 13
url: /pl/net/advanced-concepts/tree-algorithm/
---
## Wstęp

Aspose.Tasks dla .NET zapewnia zaawansowane funkcje do pracy z zadaniami, zasobami i harmonogramami zarządzania projektami. Jedną z takich funkcji jest algorytm drzewa, który pozwala użytkownikom efektywnie manipulować hierarchiami zadań. W tym samouczku przyjrzymy się, jak wykorzystać algorytm drzewa w Aspose.Tasks dla .NET do gromadzenia typowych prac i aktualizowania wartości pracy w projekcie.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Wymagana jest znajomość języka programowania C#, aby postępować zgodnie z przykładami.

## Importuj przestrzenie nazw

W swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc pracować z funkcjonalnościami Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

Teraz podzielmy każdy przykład na wiele kroków:

## Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

 Załaduj plik projektu do pamięci za pomocą`Project` klasa.

## Krok 2: Zdefiniuj hierarchię zadań

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Zdefiniuj hierarchię zadań, dodając zadania nadrzędne i podrzędne.

## Krok 3: Ustaw właściwości zadania

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Ustaw właściwości, takie jak data rozpoczęcia, czas trwania i data zakończenia zadań.

## Krok 4: Dodaj zasób

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Dodaj zasoby do projektu i w razie potrzeby przypisz je do zadań.

## Krok 5: Zastosuj algorytm drzewa

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

 Zainicjuj`WorkAccumulator` class i zastosuj algorytm drzewa, aby zebrać wspólną pracę.

## Krok 6: Zaktualizuj pracę nad zadaniem

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Zaktualizuj wartości pracy dla zadań na podstawie zebranych informacji.

## Wniosek

tym samouczku nauczyliśmy się, jak wykorzystywać algorytm drzewa w Aspose.Tasks dla .NET do efektywnego manipulowania hierarchiami zadań. Postępując zgodnie z przewodnikiem krok po kroku, możesz efektywnie zarządzać zadaniami i zasobami w ramach swoich projektów.

## Często zadawane pytania

### P1: Co to jest Aspose.Tasks dla .NET?

O1: Aspose.Tasks dla .NET to potężny interfejs API, który umożliwia programistom programowe manipulowanie plikami Microsoft Project przy użyciu języka C#.

### P2: Czy mogę pobrać bezpłatną wersję próbną Aspose.Tasks dla .NET?

 A2: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/).

### P3: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

 O3: Możesz znaleźć dokumentację Aspose.Tasks dla .NET[Tutaj](https://reference.aspose.com/tasks/net/).

### P4: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

 O4: Aby uzyskać pomoc związaną z Aspose.Tasks dla .NET, możesz odwiedzić stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P5: Czy dostępna jest licencja tymczasowa do celów testowych?

 Odpowiedź 5: Tak, możesz uzyskać tymczasową licencję do celów testowych od[Tutaj](https://purchase.aspose.com/temporary-license/).