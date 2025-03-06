---
title: Praca z operacją NOT w Aspose.Tasks
linktitle: Praca z operacją NOT w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak używać operacji NOT w Aspose.Tasks dla .NET, aby skutecznie filtrować zadania. Zwiększ swoje możliwości zarządzania projektami już teraz.
type: docs
weight: 20
url: /pl/net/advanced-concepts/not-operation/
---
## Wstęp

W tym samouczku omówimy, jak wykorzystać operację NOT w Aspose.Tasks dla .NET. Operacja NOT umożliwia odwrócenie warunku filtru, dzięki czemu możemy wybrać elementy, które nie spełniają określonych kryteriów.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Visual Studio: Aby postępować zgodnie z przykładami kodu, potrzebujesz działającej instalacji programu Visual Studio.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna w zrozumieniu przykładów kodu.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw dla naszego kodu:

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

## Krok 1: Skonfiguruj projekt i zadania

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

 Zaczynamy od załadowania pliku projektu o nazwie „Project2.mpp” za pomocą rozszerzenia`Project` klasa dostarczona przez Aspose.Tasks. Upewnij się, że plik projektu istnieje w określonym katalogu.

## Krok 2: Zbierz zadania projektowe

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

 Tutaj tworzymy`ChildTasksCollector` obiekt, aby zebrać wszystkie zadania w ramach projektu. Następnie używamy`TaskUtils.Apply` metoda przeglądania hierarchii zadań projektu i zbierania wszystkich zadań podrzędnych.

## Krok 3: Zdefiniuj stan filtra

```csharp
var filter = new NullCondition();
```

 Definiujemy warunek filtra za pomocą niestandardowej klasy o nazwie`NullCondition`. Ten warunek wybiera zadania, które mają wartość null.

## Krok 4: Zastosuj operację NIE

```csharp
var condition = new Not<Task>(filter);
```

 Stosujemy operację NOT do warunku filtra za pomocą`Not<T>`klasa dostarczona przez Aspose.Tasks. Spowoduje to odwrócenie warunku filtru i wybranie zadań, które nie mają wartości null.

## Krok 5: Filtruj zadania

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

 Filtrujemy zebrane zadania na podstawie zastosowanego warunku za pomocą niestandardowego`Filter` metoda. Ta metoda przyjmuje jako parametry wejściowe wyliczalną kolekcję zadań i warunek filtru, a następnie zwraca listę zadań spełniających ten warunek.

## Krok 6: Przetwarzaj filtrowane zadania

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Pracuj z innymi właściwościami...
}
```

Na koniec iterujemy po przefiltrowanych zadaniach i wykonujemy dowolne operacje. W tym przykładzie po prostu wypisujemy nazwy zadań na konsoli.

## Wniosek

W tym samouczku nauczyliśmy się, jak pracować z operacją NOT w Aspose.Tasks dla .NET. Odwracając warunki filtrowania, możemy selektywnie wybierać elementy, które nie spełniają określonych kryteriów, zwiększając naszą elastyczność w manipulacji zadaniami w projektach.

## Często zadawane pytania

### P1: Czy mogę używać Aspose.Tasks z innymi frameworkami .NET?

O: Tak, Aspose.Tasks obsługuje różne platformy .NET, w tym .NET Core, .NET Standard i .NET Framework.

### P2: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?

 O: Tak, możesz pobrać bezpłatną wersję próbną ze strony[strona internetowa](https://releases.aspose.com/).

### P3: Jak mogę uzyskać wsparcie dla Aspose.Tasks?

 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w przypadku jakichkolwiek pytań dotyczących wsparcia lub pomocy technicznej.

### P4: Czy mogę kupić tymczasową licencję na Aspose.Tasks?

 Odp.: Tak, możesz kupić tymczasową licencję w witrynie[strona zakupu](https://purchase.aspose.com/temporary-license/).

### P5: Gdzie mogę znaleźć obszerną dokumentację dla Aspose.Tasks?

 O: Możesz uzyskać dostęp do pełnej dokumentacji na stronie[Strona dokumentacji Aspose.Tasks](https://reference.aspose.com/tasks/net/).