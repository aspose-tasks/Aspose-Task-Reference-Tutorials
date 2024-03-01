---
title: Praca z przypisaniami w Aspose.Tasks
linktitle: Praca z przypisaniami w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać przypisaniami projektów w .NET przy użyciu Aspose.Tasks. Poznaj różne kontury planowania zasobów.
type: docs
weight: 13
url: /pl/net/advanced-features/working-with-assignment/
---
## Wstęp

W tym samouczku omówimy, jak pracować z przypisaniami w Aspose.Tasks dla .NET. Zadania odgrywają kluczową rolę w zarządzaniu projektami, ponieważ przydzielają zasoby do zadań, pomagają w planowaniu i śledzeniu postępów. Skoncentrujemy się na generowaniu danych okresowych przydziału zasobów o różnych konturach za pomocą Aspose.Tasks.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1.  Instalacja Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
2. Podstawowa znajomość języków C# i .NET Framework: Znajomość języka programowania C# i koncepcji platformy .NET jest konieczna do śledzenia.

## Importuj przestrzenie nazw

Pamiętaj, aby zaimportować niezbędne przestrzenie nazw do projektu C#:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Krok 1: Utwórz projekt i zadanie

Zacznijmy od utworzenia nowego projektu i dodania do niego zadania. Ustaw datę rozpoczęcia, czas trwania i datę zakończenia zadania:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Krok 2: Dodaj zasób i przypisz do zadania

Następnie dodaj zasób do projektu i przypisz go do wcześniej utworzonego zadania:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Krok 3: Wygeneruj dane okresowe o różnych konturach

Teraz wygenerujmy dane okresowe z różnymi konturami dla przydziału zasobu:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Krok 4: Zmień kontury i wygeneruj dane

Możemy zmienić typ konturu i odpowiednio wygenerować dane okresowe. Oto kilka przykładów:

```csharp
// Zmień kontur
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generuj dane okresowe i drukuj
// Powtórz ten krok dla innych typów konturów
```

## Wniosek

tym samouczku nauczyliśmy się, jak pracować z przypisaniami w Aspose.Tasks dla .NET. Zbadaliśmy generowanie danych okresowych przydziału zasobów o różnych konturach. Wiedza ta może być niezwykle przydatna w scenariuszach zarządzania projektami.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Tasks do planowania zadań w mojej aplikacji .NET?

Odpowiedź 1: Tak, Aspose.Tasks zapewnia kompleksowe interfejsy API do planowania zadań i zarządzania nimi w aplikacjach .NET.

### P2: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?

 Odpowiedź 2: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).

### P3: Czy istnieją jakieś ograniczenia dotyczące liczby zadań lub zasobów w Aspose.Tasks?

Odpowiedź 3: Aspose.Tasks nie nakłada żadnych ograniczeń na liczbę zadań lub zasobów, którymi możesz zarządzać w swoich projektach.

### P4: Czy mogę dostosować kontury przydziału zasobów w Aspose.Tasks?

O4: Tak, jak pokazano w tym samouczku, możesz ustawić różne kontury, takie jak żółw, dzwon, szczyt itp., zgodnie z wymaganiami projektu.

### P5: Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Tasks?

Odpowiedź 5: Pomoc można znaleźć na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) gdzie eksperci i członkowie społeczności aktywnie angażują się w dyskusje.