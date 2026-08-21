---
date: 2026-03-19
description: Dowiedz się, jak ustawić bazę projektu i efektywnie zarządzać bazami
  przydziałów za pomocą Aspose.Tasks dla .NET, zapewniając dokładne śledzenie postępu
  projektu.
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ustawienie linii bazowej projektu – zarządzanie linią bazową przydziału w Aspose.Tasks
url: /pl/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustawienie linii bazowej projektu – Zarządzanie linią bazową przydziału w Aspose.Tasks

## Wprowadzenie

Podczas pracy nad zadaniami zarządzania projektami, **ustawienie linii bazowej projektu** jest niezbędne do mierzenia rzeczywistego postępu w porównaniu z pierwotnym planem. Aspose.Tasks dla .NET nie tylko umożliwia **ustawienie linii bazowej projektu**, ale także daje pełną kontrolę nad liniami bazowymi przydziałów, umożliwiając precyzyjne śledzenie wydajności. W tym samouczku przeprowadzimy Cię przez cały proces — wczytanie projektu, ustawienie linii bazowej, odczyt danych linii bazowej przydziału oraz porównanie linii bazowych — abyś mógł pewnie monitorować swoje projekty.

## Szybkie odpowiedzi
- **Co oznacza „ustawienie linii bazowej projektu”?** Rejestruje oryginalny harmonogram i dane kosztowe do późniejszego porównania z rzeczywistą wydajnością.  
- **Która metoda API ustawia linię bazową?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Czy linie bazowe przydziałów wymagają osobnego wywołania?** Nie, są przechowywane automatycznie po ustawieniu linii bazowej projektu.  
- **Jakie formaty są obsługiwane?** MPP, XML, MPX i inne za pośrednictwem Aspose.Tasks.  
- **Czy wymagana jest licencja do produkcji?** Tak, potrzebna jest licencja komercyjna do użytku nie‑testowego.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- Podstawową znajomość programowania w C#.  
- Visual Studio (dowolna aktualna wersja).  
- Bibliotekę Aspose.Tasks dla .NET dodaną do projektu. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/net/).  
- Dostęp do pliku projektu w formacie MPP (np. `AssignmentBaseline2007.mpp`).

## Importowanie przestrzeni nazw

Dodaj wymagane przestrzenie nazw na początku pliku C#, aby kompilator wiedział, gdzie znaleźć klasy Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Załaduj projekt i ustaw linię bazową projektu

Najpierw wczytaj istniejący plik MPP, a następnie wywołaj `SetBaseline`, aby **ustawić linię bazową projektu** dla całego projektu.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Krok 2: Odczytaj informacje o linii bazowej przydziału

Po ustawieniu linii bazowej, każdy przydział zasobów zawiera własne rekordy linii bazowej. Pętla poniżej wyodrębnia i wypisuje te szczegóły, w tym daty rozpoczęcia/zakonczenia, koszty, pracę oraz ewentualne dane czasowo‑fazowe.

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

## Krok 3: Porównaj linie bazowe przydziałów

Możesz porównać linie bazowe różnych przydziałów używając wbudowanych operatorów równości i porównania. Jest to przydatne, gdy potrzebujesz wykryć przesunięcia w harmonogramie lub przekroczenia kosztów między zadaniami.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Dane linii bazowej są puste** | Plik projektu został otwarty w trybie tylko do odczytu lub linia bazowa nigdy nie została ustawiona. | Wywołaj `project.SetBaseline(BaselineType.Baseline)` przed odczytem linii bazowych przydziałów. |
| **`NullReferenceException` on `TimephasedData`** | Nie wszystkie linie bazowe zawierają wpisy czasowo‑fazowe. | Zawsze sprawdzaj `baseline.TimephasedData != null` (jak pokazano w kodzie). |
| **Nieprawidłowe pobranie UID** | Wartości UID różnią się między wersjami pliku. | Użyj `ResourceAssignments.GetByUid` z prawidłowym UID lub iteruj, aby znaleźć potrzebny przydział. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks obsługuje wiele linii bazowych dla jednego przydziału?**  
A: Tak, Aspose.Tasks obsługuje wiele linii bazowych dla każdego przydziału, co umożliwia kompleksowe śledzenie postępu projektu w czasie.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi formatami plików projektowych innymi niż MPP?**  
A: Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików projektowych, w tym XML, MPX i MPP, zapewniając kompatybilność z różnymi narzędziami do zarządzania projektami.

**Q: Czy mogę modyfikować informacje o linii bazowej programowo przy użyciu Aspose.Tasks?**  
A: Zdecydowanie, Aspose.Tasks udostępnia rozbudowane API do dynamicznej modyfikacji informacji o linii bazowej zgodnie z wymaganiami projektu, oferując elastyczność i kontrolę nad procesami zarządzania projektami.

**Q: Czy Aspose.Tasks oferuje dokumentację i zasoby wsparcia dla programistów?**  
A: Tak, programiści mają dostęp do obszernej dokumentacji, samouczków i forów na stronie Aspose.Tasks, co ułatwia płynną integrację i rozwiązywanie problemów.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?**  
A: Tak, programiści mogą pobrać darmową wersję próbną Aspose.Tasks dla .NET [tutaj](https://releases.aspose.com/), co pozwala ocenić jej funkcje i możliwości przed podjęciem decyzji o zakupie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-19  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose