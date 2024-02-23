---
title: Zarządzanie bazą przydziału w Aspose.Tasks
linktitle: Zarządzanie bazą przydziału w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać planami bazowymi przydziałów za pomocą Aspose.Tasks dla .NET, zapewniając dokładne śledzenie postępu i wydajności projektu.
type: docs
weight: 14
url: /pl/net/advanced-features/assignment-baseline/
---
## Wstęp

Podczas pracy nad zadaniami związanymi z zarządzaniem projektami zarządzanie punktami odniesienia przydziałów ma kluczowe znaczenie dla dokładnego śledzenia postępu. Aspose.Tasks dla .NET zapewnia kompleksowy zestaw narzędzi do efektywnej obsługi linii bazowych przypisań. W tym samouczku krok po kroku omówimy proces zarządzania planami bazowymi przypisań.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany w systemie.
- Do Twojego projektu dodano bibliotekę Aspose.Tasks for .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
- Dostęp do pliku projektu w formacie MPP.

## Importuj przestrzenie nazw

Aby rozpocząć pracę z Aspose.Tasks, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#. Dodaj następujące przestrzenie nazw na początku pliku C#:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Załaduj projekt i ustaw linię bazową

 Najpierw załaduj plik projektu za pomocą`Project` klasa z Aspose.Tasks. Następnie ustaw typ planu bazowego dla projektu za pomocą`SetBaseline` metoda.

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Krok 2: Przeczytaj informacje podstawowe o przypisaniu

Wykonaj iterację po każdym przypisaniu zasobów w projekcie i pobierz informacje o poziomie bazowym dla każdego przydziału.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Krok 3: Sprawdź równość linii bazowej

Porównaj informacje bazowe dla różnych zadań, korzystając z różnych metod porównawczych dostarczonych przez Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Sprawdź równość linii bazowej
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Sprawdź porównanie linii bazowej
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Wyświetl podstawowe kody skrótu
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Wniosek

Zarządzanie bazowymi zadaniami jest integralną częścią zarządzania projektami, umożliwiając dokładne śledzenie postępów i wydajności. Dzięki Aspose.Tasks dla .NET obsługa podstawowych przydziałów staje się usprawniona i wydajna, zapewniając programistom potężne narzędzia usprawniające przepływ pracy w zarządzaniu projektami.

## Często zadawane pytania

### P1: Czy Aspose.Tasks może obsłużyć wiele planów bazowych w ramach jednego zadania?

Odpowiedź 1: Tak, Aspose.Tasks obsługuje wiele linii bazowych dla każdego zadania, umożliwiając kompleksowe śledzenie postępu projektu w czasie.

### P2: Czy Aspose.Tasks jest kompatybilny z różnymi formatami plików projektów innymi niż MPP?

Odpowiedź 2: Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików projektów, w tym XML, MPX i MPP, zapewniając kompatybilność z różnymi narzędziami do zarządzania projektami.

### P3: Czy mogę programowo modyfikować informacje bazowe za pomocą Aspose.Tasks?

Odpowiedź 3: Oczywiście, Aspose.Tasks zapewnia rozbudowane interfejsy API umożliwiające dynamiczną modyfikację informacji bazowych zgodnie z wymaganiami projektu, oferując elastyczność i kontrolę nad procesami zarządzania projektami.

### P4: Czy Aspose.Tasks oferuje dokumentację i zasoby wsparcia dla programistów?

Odpowiedź 4: Tak, programiści mogą uzyskać dostęp do obszernej dokumentacji, samouczków i forów na stronie internetowej Aspose.Tasks, ułatwiając płynną integrację i rozwiązywanie problemów.

### P5: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?

 Odpowiedź 5: Tak, programiści mogą uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/), umożliwiając im ocenę jego funkcji i możliwości przed podjęciem decyzji o zakupie.