---
date: 2026-03-16
description: Dowiedz się, jak łączyć wiele warunków i filtrować zadania projektu przy
  użyciu zaawansowanej operacji AND w Aspose.Tasks dla .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Jak połączyć wiele warunków przy użyciu zaawansowanej operacji AND w Aspose.Tasks
url: /pl/net/advanced-features/advanced-and-operation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zaawansowana operacja AND w Aspose.Tasks

## Wprowadzenie

W tym samouczku odkryjesz **jak łączyć wiele warunków** przy użyciu *zaawansowanej operacji AND* w Aspose.Tasks dla .NET. Po zakończeniu przewodnika będziesz w stanie **filtrować zadania projektu** na podstawie kilku kryteriów — co jest niezbędne, gdy musisz **filtrować zadania** takie jak elementy podsumowujące, nie‑puste wpisy lub niestandardowe flagi w jednym przebiegu.

## Szybkie odpowiedzi
- **Co robi zaawansowana operacja AND?** Łączy dwa lub więcej warunków filtru, tak że zwracane są tylko zadania spełniające *wszystkie* kryteria.  
- **Która klasa łączy warunki?** `Util.And<T>` (udostępniona jako `And<T>` w API).  
- **Czy potrzebna jest specjalna licencja?** Wymagana jest standardowa licencja Aspose.Tasks do użytku produkcyjnego; dostępna jest darmowa wersja próbna.  
- **Czy mogę połączyć więcej niż dwa warunki?** Tak — `And<T>` akceptuje dowolną liczbę warunków.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Co oznacza „łączenie wielu warunków” w Aspose.Tasks?

Łączenie wielu warunków oznacza tworzenie złożonego filtru, który ocenia każde zadanie względem kilku reguł jednocześnie. Takie podejście jest znacznie bardziej wydajne niż iterowanie listy zadań wielokrotnie, ponieważ biblioteka stosuje logikę w jednym przebiegu.

## Dlaczego używać zaawansowanej operacji AND?

- **Wydajność:** Zmniejsza liczbę przebiegów po kolekcji zadań.  
- **Czytelność:** Utrzymuje logikę filtru deklaratywną i łatwą w utrzymaniu.  
- **Elastyczność:** Możesz mieszać wbudowane warunki (np. `SummaryCondition`) z własnymi predykatami.  

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

1. Podstawową wiedzę programowania w C#.  
2. Zainstalowany Aspose.Tasks dla .NET. Jeśli jeszcze go nie pobrałeś, pobierz go **[tutaj](https://releases.aspose.com/tasks/net/)**.  
3. Środowisko IDE, takie jak Visual Studio (dowolna edycja).  

## Importowanie przestrzeni nazw

Najpierw zaimportuj przestrzenie nazw, które dostarczają model zadania i klasy pomocnicze:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Krok 1: Inicjalizacja projektu i zbieranie zadań

Utworzymy instancję `Project` i użyjemy `ChildTasksCollector`, aby zebrać każde zadanie w pliku. To pokazuje **jak używać kolektora** do pobrania płaskiej listy zadań.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Krok 2: Definiowanie warunków filtru

Tutaj definiujemy poszczególne warunki, które chcemy zastosować. W tym przykładzie **filtrujemy zadania podsumowujące** oraz zapewniamy, że obiekt zadania nie jest nullem.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Krok 3: Łączenie warunków operacją AND

Teraz **łączymy wiele warunków** przy użyciu klasy `And<T>`. To jest sedno **zaawansowanej operacji AND**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Krok 4: Zastosowanie warunku i filtrowanie zadań

Gdy złożony warunek jest gotowy, wywołujemy `Filter`, aby **filtrować zadania projektu** na podstawie połączonej logiki.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Krok 5: Wyświetlanie przefiltrowanych zadań

Na koniec wyświetlamy zadania, które spełniły **wszystkie** warunki. Możesz zamienić wywołania `Console.WriteLine` na dowolne własne przetwarzanie.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Szybka naprawa |
|---------|----------------------|----------------|
| `Filter` method not found | Brak `using Aspose.Tasks.Util;` | Upewnij się, że przestrzeń nazw Util jest zaimportowana (zobacz Importowanie przestrzeni nazw). |
| No tasks returned | Warunki są zbyt restrykcyjne (np. filtrowanie zadań podsumowujących, gdy ich nie ma) | Zweryfikuj, czy projekt rzeczywiście zawiera zadania podsumowujące lub dostosuj warunki. |
| NullReferenceException | `coll.Tasks` zawiera wpisy null | `NotNullCondition` już chroni przed tym; pozostaw go w łańcuchu AND. |

## FAQ

### Q1: Co to jest Aspose.Tasks dla .NET?

Aspose.Tasks for .NET to solidne API, które umożliwia programistom programowe manipulowanie plikami Microsoft Project w aplikacjach .NET.

### Q2: Czy mogę zastosować więcej niż dwa warunki używając Util.And?

Tak, Util.And może być użyty do połączenia dowolnej liczby warunków w celu stworzenia złożonych kryteriów filtrowania.

### Q3: Czy dostępna jest darmowa wersja próbna Aspose.Tasks dla .NET?

Tak, możesz pobrać darmową wersję próbną **[tutaj](https://releases.aspose.com/)**.

### Q4: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

Dokumentację znajdziesz **[tutaj](https://reference.aspose.com/tasks/net/)**.

### Q5: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

Wsparcie możesz uzyskać na forum społeczności Aspose.Tasks **[tutaj](https://forum.aspose.com/c/tasks/15)**.

**Additional Q&A**

**Q: Jak filtrować zadania według wartości pól niestandardowych?**  
A: Utwórz `CustomFieldCondition` (lub zaimplementuj `ICondition<Task>`) i dodaj go do łańcucha `And<T>`.

**Q: Czy mogę użyć tego samego podejścia do filtrowania zasobów?**  
A: Tak — zamień `Task` na `Resource` i użyj odpowiednich klas warunków.

## Podsumowanie

Postępując zgodnie z powyższymi krokami, teraz wiesz **jak łączyć wiele warunków** przy użyciu **zaawansowanej operacji AND** w Aspose.Tasks dla .NET. Ta technika pozwala **efektywnie filtrować zadania projektu**, niezależnie od tego, czy celujesz w elementy podsumowujące, nie‑puste wpisy czy dowolne niestandardowe kryteria.

---

**Ostatnia aktualizacja:** 2026-03-16  
**Testowano z:** Aspose.Tasks for .NET (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}