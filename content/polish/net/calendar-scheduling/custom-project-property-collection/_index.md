---
title: Zarządzanie niestandardową kolekcją właściwości projektu w Aspose.Tasks
linktitle: Zarządzanie niestandardową kolekcją właściwości projektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skutecznie zarządzać niestandardowymi właściwościami projektu w Aspose.Tasks dla .NET, poprawiając swoje doświadczenie w zarządzaniu projektami.
type: docs
weight: 24
url: /pl/net/calendar-scheduling/custom-project-property-collection/
---
## Wstęp

Czy jesteś gotowy, aby ulepszyć swoje doświadczenie w zarządzaniu projektami dzięki Aspose.Tasks dla .NET? Zarządzanie niestandardowymi właściwościami projektu jest kluczowym aspektem zarządzania projektami, umożliwiającym dodawanie określonych metadanych dostosowanych do wymagań projektu. W tym samouczku omówimy, jak efektywnie pracować z niestandardowymi kolekcjami właściwości projektu za pomocą Aspose.Tasks dla .NET.

## Warunki wstępne

Zanim przejdziemy dalej, upewnij się, że masz skonfigurowane następujące wymagania wstępne:

1. Środowisko Visual Studio: Zainstaluj program Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.

## Importuj przestrzenie nazw

Zacznij od zaimportowania niezbędnych przestrzeni nazw do pracy z Aspose.Tasks dla .NET:

```csharp
using Aspose.Tasks;
using System;


```

Podzielmy przykładowy kod na wiele kroków, aby uzyskać kompleksowe zrozumienie:

## Krok 1: Zainicjuj projekt

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

Ten krok inicjuje nowy projekt przy użyciu Aspose.Tasks.

## Krok 2: Sprawdź gotowość gromadzenia właściwości niestandardowych

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

Ten kod sprawdza, czy kolekcja właściwości niestandardowych jest tylko do odczytu.

## Krok 3: Dodaj właściwości niestandardowe

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

Tutaj dodajemy do projektu niestandardowe właściwości, obsługujące typy Boolean, DateTime, Double i String.

## Krok 4: Uzyskaj dostęp do właściwości niestandardowych

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

Ta pętla umożliwia iterację po niestandardowych właściwościach i wyświetlanie ich typu, nazwy i wartości.

## Krok 5: Pobierz wartość właściwości niestandardowej

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

Ten kod pobiera wartość określonej właściwości niestandardowej o nazwie „Nazwa niestandardowa”.

## Krok 6: Iteruj po nazwach właściwości niestandardowych

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

Tutaj iterujemy po nazwach niestandardowych właściwości i wyświetlamy je.

## Krok 7: Usuń lub wyczyść właściwości niestandardowe

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

Możesz usunąć konkretną właściwość niestandardową według jej nazwy lub wyczyścić całą kolekcję.

## Wniosek

Opanowanie niestandardowych kolekcji właściwości projektu w Aspose.Tasks dla .NET umożliwia wydajne zarządzanie metadanymi projektu. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz bezproblemowo zintegrować niestandardowe właściwości z przepływem pracy związanym z zarządzaniem projektami, poprawiając organizację i wydajność.

## Często zadawane pytania

### P1: Czy mogę dodać niestandardowe właściwości dowolnego typu danych do mojego projektu za pomocą Aspose.Tasks dla .NET?

O1: Tak, możesz dodać niestandardowe właściwości obsługujące typy Boolean, DateTime, Double i String.

### P2: Czy można iterować po niestandardowych nazwach właściwości w Aspose.Tasks dla .NET?

 Odpowiedź 2: Oczywiście możesz iterować po nazwach niestandardowych właściwości za pomocą metody`Names` nieruchomość.

### P3: Jak mogę usunąć określoną właściwość niestandardową z mojego projektu?

 Odpowiedź 3: Możesz usunąć właściwość niestandardową według jej nazwy, używając przycisku`Remove` metoda.

### P4: Czy Aspose.Tasks dla .NET zapewnia obsługę licencji tymczasowych?

A4: Tak, możesz uzyskać tymczasową licencję ze strony Aspose do celów ewaluacyjnych.

### P5: Gdzie mogę znaleźć wsparcie lub dalszą pomoc dotyczącą Aspose.Tasks dla .NET?

 O5: Możesz odwiedzić forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15) w przypadku jakichkolwiek pytań lub pomocy.