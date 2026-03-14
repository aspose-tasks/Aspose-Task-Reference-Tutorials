---
date: 2026-03-14
description: Dowiedz się, jak filtrować zadania niebędące operacjami w Aspose.Tasks
  dla .NET i odkryj, jak używać filtru NOT z warunkiem NOT w elastycznych zapytaniach
  o zadania.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Filtruj zadania, nie operację w Aspose.Tasks
url: /pl/net/advanced-concepts/not-operation/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# filtrowanie zadań przy użyciu operacji NOT w Aspose.Tasks

## Wprowadzenie

W tym samouczku dowiesz się **jak filtrować zadania przy użyciu operacji NOT** za pomocą Aspose.Tasks dla .NET. Operacja NOT odwraca warunek filtru, dzięki czemu możesz wybrać każde zadanie, które **nie** spełnia określonego kryterium. Ta funkcja jest niezbędna, gdy musisz wykluczyć określone elementy — np. zadania bez wartości — lub gdy chcesz budować złożone zapytania bez pisania dodatkowego kodu.

## Szybkie odpowiedzi
- **Co robi operacja NOT?** Odwraca warunek filtru, zwracając elementy, które nie przeszły pierwotnego testu.  
- **Dlaczego używać operacji NOT przy filtrowaniu zadań?** Upraszcza logikę wykluczania i utrzymuje kod czytelnym.  
- **Która przestrzeń nazw udostępnia klasę NOT?** `Aspose.Tasks.Util`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Tak, wymagana jest ważna licencja Aspose.Tasks dla wersji nie‑trial.  
- **Czy mogę łączyć NOT z innymi warunkami?** Oczywiście — można łączyć go z `AndCondition`, `OrCondition` itp.

## Czym jest operacja NOT w filtrowaniu zadań?
**Operacja NOT w filtrowaniu zadań** to logiczna negacja zastosowana do filtru zadania. Zamiast wybierać zadania spełniające warunek, wybiera te, które *nie* spełniają tego warunku. Jest to szczególnie przydatne, gdy chcesz pominąć zadania z pustymi polami, określonymi statusami lub dowolnym innym atrybutem, który chcesz wykluczyć.

## Dlaczego stosować warunek NOT przy filtrowaniu zadań?
Zastosowanie **warunku NOT** zmniejsza potrzebę wielokrotnego przetwarzania danych projektu. Pozwala napisać zwięzły, łatwy do utrzymania kod i poprawia wydajność, delegując ocenę do zoptymalizowanego silnika Aspose.Tasks.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz następujące elementy:

1. Visual Studio: Potrzebujesz działającej instalacji Visual Studio, aby móc podążać za przykładami kodu.  
2. Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET ze [strony internetowej](https://releases.aspose.com/tasks/net/).  
3. Podstawowa znajomość C#: Znajomość języka programowania C# będzie pomocna przy rozumieniu przykładów kodu.

## Importowanie przestrzeni nazw

Najpierw zaimportuj niezbędne przestrzenie nazw dla naszego kodu:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Konfiguracja projektu i zadań

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Rozpoczynamy od wczytania pliku projektu o nazwie **Project2.mpp** przy użyciu klasy `Project` udostępnionej przez Aspose.Tasks. Upewnij się, że plik projektu istnieje w podanym katalogu.

## Krok 2: Zbieranie zadań projektu

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Tutaj tworzymy obiekt `ChildTasksCollector`, aby zebrać wszystkie zadania w projekcie. Następnie używamy `TaskUtils.Apply`, aby przejść przez hierarchię zadań projektu i zebrać każde zadanie podrzędne.

## Krok 3: Definiowanie warunku filtru

```csharp
var filter = new NullCondition();
```

Definiujemy warunek filtru przy użyciu własnej klasy o nazwie `NullCondition`. Ten warunek wybiera zadania, które mają **null** jako wartość.  

> **Wskazówka:** Zamień `NullCondition` na inny warunek (np. `EqualsCondition`), aby celować w różne atrybuty.

## Krok 4: Zastosowanie operacji NOT

```csharp
var condition = new Not<Task>(filter);
```

Stosujemy **operację NOT** do warunku filtru przy użyciu klasy `Not<T>` udostępnionej przez Aspose.Tasks. Odwraca to pierwotny warunek, więc filtr teraz wybiera zadania, które **nie** mają wartości null. To jest sedno techniki **jak używać filtru NOT**.

## Krok 5: Filtrowanie zadań

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

Filtujemy zebrane zadania na podstawie zastosowanego warunku przy użyciu własnej metody `Filter`. Metoda przyjmuje kolekcję zadań oraz warunek filtru, zwracając listę zadań spełniających **warunek NOT**.

## Krok 6: Przetwarzanie przefiltrowanych zadań

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Na koniec iterujemy po przefiltrowanych zadaniach i wykonujemy dowolne operacje. W tym przykładzie po prostu wypisujemy nazwy zadań w konsoli, ale możesz rozbudować ten blok, aby aktualizować pola, przenosić zadania lub generować raporty.

## Typowe przypadki użycia

- **Wyklucz zakończone zadania** przy generowaniu listy zaległych prac.  
- **Znajdź zadania brakujące w polach niestandardowych** (np. kolumna „Owner” o wartości null).  
- **Połącz z innymi warunkami**, aby budować zaawansowane zapytania, takie jak „zadania, które nie są null i mają datę rozpoczęcia wcześniejszą niż dzisiaj”.

## Rozwiązywanie problemów i wskazówki

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Brak zwróconych zadań | Oryginalny warunek może być zbyt restrykcyjny. | Zweryfikuj logikę warunku lub przetestuj prostszy filtr, np. `new TrueCondition()`. |
| `NullReferenceException` | Ścieżka `DataDir` jest nieprawidłowa. | Upewnij się, że `DataDir` wskazuje na folder zawierający *Project2.mpp*. |
| Nieoczekiwane wyniki | Niepoprawne łączenie `Not<T>` z innymi warunkami. | Użyj nawiasów: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks z innymi frameworkami .NET?**  
O: Tak, Aspose.Tasks obsługuje .NET Core, .NET Standard oraz klasyczny .NET Framework.

**P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
O: Tak, darmową wersję próbną możesz pobrać ze [strony internetowej](https://releases.aspose.com/).

**P: Jak mogę uzyskać wsparcie techniczne dla Aspose.Tasks?**  
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby zadać pytania lub uzyskać pomoc techniczną.

**P: Czy mogę kupić tymczasową licencję na Aspose.Tasks?**  
O: Tak, tymczasową licencję można nabyć na [stronie zakupu](https://purchase.aspose.com/temporary-license/).

**P: Gdzie znajdę pełną dokumentację Aspose.Tasks?**  
O: Kompletną dokumentację znajdziesz na [stronie dokumentacji Aspose.Tasks](https://reference.aspose.com/tasks/net/).

## Zakończenie

Opanowując **operację NOT przy filtrowaniu zadań** oraz ucząc się **jak używać filtru NOT** z **warunkiem NOT**, zyskujesz precyzyjną kontrolę nad wyborem zadań w Aspose.Tasks. Dzięki temu możesz pisać czystszy kod, unikać ręcznych wykluczeń i tworzyć potężne narzędzia do zarządzania projektami.

---

**Ostatnia aktualizacja:** 2026-03-14  
**Testowano z:** Aspose.Tasks 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}