---
date: 2026-03-24
description: Dowiedz się, jak ustawić obliczenia w Aspose.Tasks dla .NET, z przykładami
  obliczania wartości podsumowujących, definiowania formuły obliczeniowej i konfigurowania
  podsumowania rollup.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak ustawić typ obliczeń w Aspose.Tasks
url: /pl/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić typ obliczeń w Aspose.Tasks

## Wprowadzenie

Jeśli potrzebujesz **how to set calculation** reguł dla zadań i wierszy podsumowań w pliku Microsoft Project, ten tutorial pokaże Ci dokładnie, jak to zrobić przy użyciu Aspose.Tasks dla .NET. Przejdziemy przez kompletny **calculation type example**, pokażemy, jak **calculate summary values**, oraz wyjaśnimy, jak **define calculation formula** i **configure rollup summary** dla rozszerzonych atrybutów. Po zakończeniu będziesz w stanie dodać zadanie do projektu, ustawić własną logikę obliczeń i kontrolować zachowanie roll‑up z pewnością.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Aby kontrolować, jak wartości zadań i podsumowań są obliczane w pliku Project.  
- **Która klasa API jest używana?** `ExtendedAttributeDefinition` together with `CalculationType` and `SummaryRowsCalculationType`.  
- **Czy mogę użyć formuły?** Tak – set `CalculationType = CalculationType.Formula` and provide a formula string.  
- **Jak mogę roll‑upować wartości podsumowania?** Użyj `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` i określ `RollupType`, np. `Average`.  
- **Czy potrzebuję licencji?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.

## Co to jest Calculation Type i jak ustawić obliczenia?

`CalculationType` informuje Aspose.Tasks, jak obliczyć wartość rozszerzonego atrybutu. Możesz wybrać wartość statyczną, formułę lub pozwolić bibliotece roll‑upować wartości z zadań podrzędnych. Poprawne ustawienie obliczeń jest niezbędne, gdy chcesz, aby projekt odzwierciedlał własne reguły biznesowe bez ręcznych aktualizacji.

## Dlaczego używać typu obliczeń do obliczania wartości podsumowań?

Gdy projekt zawiera zadania podsumowujące, często potrzebujesz, aby wiersze podsumowań wyświetlały dane zagregowane (np. całkowity koszt, średni czas trwania). Konfigurując **calculate summary values** za pomocą `SummaryRowsCalculationType` i `RollupType`, Aspose.Tasks może automatycznie utrzymywać te agregaty w synchronizacji podczas modyfikacji poszczególnych zadań.

## Wymagania wstępne

1. Podstawowa znajomość C# i platformy .NET.  
2. Zainstalowany Visual Studio (dowolna nowsza wersja) na Twoim komputerze.  
3. Zainstalowana biblioteka Aspose.Tasks for .NET – możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/net/).  
4. Dostęp do oficjalnej dokumentacji Aspose.Tasks for .NET w celu odniesienia, dostępnej [tutaj](https://reference.aspose.com/tasks/net/).

## Importowanie przestrzeni nazw

Zanim przejdziesz do przykładu, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Utwórz nowy projekt

Najpierw tworzymy pusty obiekt `Project`, który będzie przechowywał nasze zadania i niestandardowe atrybuty.

```csharp
var project = new Project();
```

## Krok 2: Dodaj zadanie do projektu

Teraz **add task project** dane, tworząc proste zadanie, ustawiając jego datę rozpoczęcia i nadając mu jednodniowy czas trwania.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Krok 3: Zdefiniuj typ obliczeń dla rozszerzonego atrybutu (przykład formuły)

Tutaj tworzymy definicję rozszerzonego atrybutu, którego wartość jest obliczana z formuły. To demonstruje **calculation type example** i pokazuje, jak **define calculation formula**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Krok 4: Zdefiniuj typ obliczeń dla wierszy podsumowań (konfiguracja rollup summary)

Następnie tworzymy kolejną definicję rozszerzonego atrybutu, która instruuje Aspose.Tasks, aby **configure rollup summary** przy użyciu typu roll‑up *Average*. To typowy sposób na **calculate summary values** dla kosztu, pracy lub pól niestandardowych.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Formuła zwraca `null` | Nieprawidłowe odwołanie do pola w formule | Zweryfikuj nazwę pola w nawiasach (np. `[Start]` a nie `[stARt]`). |
| Wiersze podsumowań pokazują 0 | `SummaryRowsCalculationType` nie ustawiony lub niewłaściwy `RollupType` | Upewnij się, że `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` i wybierz odpowiedni `RollupType`. |
| Projekt nie ładuje się po dodaniu atrybutów | Niezgodność między definicją atrybutu a użyciem w zadaniu | Dodaj definicję atrybutu **przed** przypisaniem go do jakiegokolwiek zadania. |

## Podsumowanie

W tym tutorialu omówiliśmy **how to set calculation** reguły w Aspose.Tasks dla .NET, od tworzenia prostego zadania po definiowanie zarówno typów obliczeń opartych na formule, jak i roll‑up. Opanowując te ustawienia, zyskujesz precyzyjną kontrolę nad **calculate summary values**, umożliwiając bardziej zaawansowaną analizę projektu bez ręcznej pracy w arkuszach kalkulacyjnych.

## FAQ

### Q1: Co to jest Calculation Type w Aspose.Tasks?

Calculation Type w Aspose.Tasks określa, jak wartości są obliczane dla zadań i zadań podsumowujących w projekcie, oferując opcje takie jak Formula i Rollup.

### Q2: Jak ustawić Calculation Type dla rozszerzonego atrybutu?

Możesz ustawić Calculation Type dla rozszerzonego atrybutu, definiując odpowiednio jego właściwość CalculationType.

### Q3: Czy mogę dostosować Calculation Type dla wierszy podsumowań w projekcie?

Tak, Aspose.Tasks pozwala określić Calculation Type dla wierszy podsumowań, umożliwiając dostosowanie obliczeń wartości do Twoich wymagań.

### Q4: Czy dostępne są różne typy Rollup dla obliczeń zadań podsumowujących?

Tak, Aspose.Tasks oferuje różne Rollup Types, takie jak Average, Sum i Count, do obliczania wartości zadań podsumowujących.

### Q5: Gdzie mogę znaleźć więcej zasobów na temat Aspose.Tasks dla .NET?

Możesz przeglądać dokumentację i fora wsparcia społeczności dostępne na [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) w celu uzyskania kompleksowych wskazówek i pomocy.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}