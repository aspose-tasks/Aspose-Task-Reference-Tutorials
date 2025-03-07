---
title: Typ obliczenia w Aspose.Tasks
linktitle: Typ obliczenia w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak dostosować obliczenia wartości w projektach .NET za pomocą typu obliczenia w bibliotece Aspose.Tasks.
weight: 30
url: /pl/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Typ obliczenia w Aspose.Tasks

## Wstęp

W tym samouczku omówimy funkcję Typu obliczeń w Aspose.Tasks dla .NET. Aspose.Tasks to potężna biblioteka, która umożliwia programistom .NET pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project w ich systemach. Typ obliczeń pozwala nam zdefiniować sposób obliczania wartości dla zadań i zadań sumarycznych w ramach projektu.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

1. Podstawowa znajomość C# i frameworku .NET.
2. Program Visual Studio zainstalowany w systemie.
3.  Zainstalowana biblioteka Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
4.  Dostępny jest dostęp do dokumentacji Aspose.Tasks for .NET w celach informacyjnych[Tutaj](https://reference.aspose.com/tasks/net/).

## Importuj przestrzenie nazw

Zanim zagłębisz się w przykład, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:

```csharp
using Aspose.Tasks;
using System;


```

## Krok 1: Utwórz nowy projekt

Najpierw utwórzmy nowy obiekt projektu:

```csharp
var project = new Project();
```

## Krok 2: Dodaj zadanie

Dodajmy teraz zadanie do naszego projektu:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Krok 3: Zdefiniuj typ obliczeń dla atrybutu rozszerzonego

Utworzymy rozszerzoną definicję atrybutu z typem obliczenia ustawionym na Formuła:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Krok 4: Zdefiniuj typ obliczeń dla wierszy podsumowań

Następnie utworzymy kolejną rozszerzoną definicję atrybutu, w której wartości zadań sumarycznych będą obliczane przy użyciu typu zestawienia Średnia:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Wniosek

W tym samouczku omówiliśmy, jak pracować z typem obliczeń w Aspose.Tasks dla .NET. Definiując typy obliczeń dla atrybutów rozszerzonych, możemy dostosować sposób obliczania wartości dla zadań i zadań sumarycznych w projekcie, zapewniając większą elastyczność i kontrolę.

## Często zadawane pytania

### P1: Jaki jest typ obliczeń w Aspose.Tasks?

O1: Typ obliczeń w Aspose.Tasks określa sposób obliczania wartości dla zadań i zadań sumarycznych w projekcie, oferując opcje takie jak Formuła i Zestawienie.

### P2: Jak ustawić typ obliczeń dla atrybutu rozszerzonego?

O2: Można ustawić typ obliczenia dla atrybutu rozszerzonego, odpowiednio definiując jego właściwość CalculationType.

### P3: Czy mogę dostosować typ obliczeń dla wierszy podsumowań w projekcie?

O3: Tak, Aspose.Tasks pozwala określić typ obliczeń dla wierszy podsumowań, umożliwiając dostosowanie obliczeń wartości w oparciu o Twoje wymagania.

### P4: Czy dostępne są różne typy zestawień do obliczeń zadań sumarycznych?

O4: Tak, Aspose.Tasks udostępnia różne typy zestawień, takie jak średnia, suma i liczba, do obliczania wartości zadań sumarycznych.

### P5: Gdzie mogę znaleźć więcej zasobów w Aspose.Tasks dla .NET?

 Odpowiedź 5: Możesz zapoznać się z dokumentacją i forami pomocy społeczności dostępnymi na stronie[Aspose.Tasks dla .NET](https://reference.aspose.com/tasks/net/) w celu uzyskania kompleksowych wskazówek i pomocy.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
