---
title: Zarządzaj kryteriami grupy MS Project za pomocą Aspose.Tasks
linktitle: Zarządzanie zbiorem kryteriów grupy w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać kolekcją projektów MS Project Group Criterion przy użyciu Aspose.Tasks dla .NET. Przewodnik krok po kroku dla programistów.
type: docs
weight: 28
url: /pl/net/tasks-project-management/group-criterion-collection/
---
## Wstęp
Aspose.Tasks dla .NET to potężny interfejs API, który umożliwia programistom programową pracę z plikami Microsoft Project. W tym samouczku przyjrzymy się, jak zarządzać kolekcją kryteriów grupy w programie MS Project za pomocą Aspose.Tasks.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1.  Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Tasks w swoim projekcie .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).

2. Plik projektu Microsoft: Przygotuj plik Microsoft Project (MPP), z którym będziesz mógł pracować.

## Importuj przestrzenie nazw

Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#. Ten krok jest kluczowy dla uzyskania dostępu do funkcjonalności zapewnianych przez Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Krok 1: Załaduj plik projektu

 Zainicjuj a`Project` obiekt poprzez załadowanie pliku MPP. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Krok 2: Kryteria grupy dostępu

Pobierz grupę z projektu i uzyskaj dostęp do jej kryteriów.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Krok 3: Iteruj po kryteriach grupowych

Przejdź przez każde kryterium w grupie i wyświetl jego właściwości.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Krok 4: Wyczyść kryteria grupy

Wyczyść istniejące kryteria grupy, jeśli nie jest ona przeznaczona tylko do odczytu.

```csharp
group.GroupCriteria.Clear();
```

## Krok 5: Dodaj nowe kryterium

Utwórz nowe kryterium grupy i dodaj je do grupy.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Krok 6: Skopiuj kryteria do innej grupy

Skopiuj kryteria z jednej grupy do drugiej.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Wniosek

W tym samouczku nauczyliśmy się, jak zarządzać kolekcją projektu MS Project Group Criterion przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, można skutecznie programowo manipulować kryteriami grupowymi w plikach programu Microsoft Project.

## Często zadawane pytania

### P1: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?

O: Tak, Aspose.Tasks obsługuje pliki Microsoft Project w różnych wersjach, w tym 2003, 2007, 2010, 2013 i 2016.

### Pytanie 2: Czy mogę zastosować wiele kryteriów do jednej grupy?

O: Oczywiście możesz dodać wiele kryteriów do grupy, przeglądając każde z nich i odpowiednio je dodając.

### P3: Czy dostępna jest wersja próbna Aspose.Tasks?

 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks od[Tutaj](https://releases.aspose.com/).

### P4: Gdzie mogę znaleźć dokumentację dla Aspose.Tasks?

 Odpowiedź: Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/net/).

### P5: Jak mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy?

 Odp.: Jeśli masz jakieś pytania lub napotkasz jakiekolwiek problemy, możesz zwrócić się o pomoc na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).