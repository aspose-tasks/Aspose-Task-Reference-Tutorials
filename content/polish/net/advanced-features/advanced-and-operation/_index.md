---
title: Zaawansowane operacje AND w Aspose.Tasks
linktitle: Zaawansowane operacje AND w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak wykonywać zaawansowane operacje AND w Aspose.Tasks dla .NET, aby efektywnie filtrować zadania projektu w oparciu o wiele kryteriów.
type: docs
weight: 10
url: /pl/net/advanced-features/advanced-and-operation/
---
## Wstęp

 W tym samouczku zagłębimy się w zaawansowaną operację AND w Aspose.Tasks dla .NET, potężnym narzędziu do zarządzania zadaniami i projektami. Zbadamy, jak filtrować zadania projektu na podstawie wielu warunków za pomocą`Util.And` klasa.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Podstawowa znajomość języka programowania C#.
2.  Zainstalowano Aspose.Tasks dla .NET. Jeśli nie, możesz go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw do naszego projektu C#:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Krok 1: Zainicjuj projekt i zbierz zadania

Rozpocznij od zainicjowania nowego projektu Aspose.Tasks i zebrania w nim wszystkich zadań:

```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Krok 2: Zdefiniuj warunki filtra

Następnie zdefiniuj warunki filtra. Na potrzeby tego przykładu utworzymy dwa warunki: jeden do filtrowania zadań sumarycznych, a drugi do filtrowania zadań innych niż null:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Krok 3: Połącz warunki za pomocą operacji AND

 Teraz połącz warunki za pomocą`Util.And` klasę, aby utworzyć warunek złożony:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Krok 4: Zastosuj zadania warunku i filtra

Zastosuj połączony warunek do zebranych zadań i odpowiednio je przefiltruj:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Krok 5: Wyprowadź filtrowane zadania

Na koniec wyprowadź przefiltrowane zadania:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Tutaj można wykonać dodatkowe przetwarzanie
}
```

## Wniosek

 W tym samouczku nauczyliśmy się wykonywać zaawansowane operacje AND w Aspose.Tasks dla .NET. Łącząc warunki za pomocą`Util.And`class, możemy efektywnie filtrować zadania w oparciu o wiele kryteriów.

## Często zadawane pytania

### P1: Co to jest Aspose.Tasks dla .NET?

O: Aspose.Tasks dla .NET to solidny interfejs API, który pozwala programistom programowo manipulować plikami Microsoft Project w aplikacjach .NET.

### P2: Czy mogę zastosować więcej niż dwa warunki za pomocą narzędzia Util.And?

O: Tak, narzędzia Util.And można używać do łączenia dowolnej liczby warunków w celu utworzenia złożonych kryteriów filtrowania.

### P3: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?

 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).

### P4: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?

 Odp.: Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).

### P5: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?

Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).