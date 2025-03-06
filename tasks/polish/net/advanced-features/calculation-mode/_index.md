---
title: Tryb obliczeń w Aspose.Tasks
linktitle: Tryb obliczeń w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać trybami obliczeń w Aspose.Tasks dla .NET, aby usprawnić planowanie projektów i zależności między zadaniami.
type: docs
weight: 29
url: /pl/net/advanced-features/calculation-mode/
---
## Wstęp

Aspose.Tasks dla .NET to potężny interfejs API, który umożliwia programistom programową pracę z plikami Microsoft Project w aplikacjach .NET. Jednym z kluczowych aspektów pracy z plikami projektów jest zarządzanie trybami obliczeń, które określają sposób obliczania i aktualizowania zadań i harmonogramów projektów. W tym samouczku zagłębimy się w różne tryby obliczeń obsługiwane przez Aspose.Tasks dla .NET i pokażemy, jak efektywnie z nich korzystać.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

1. Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość programowania w języku C#: Zapoznaj się z koncepcjami programowania w języku C#.

## Importuj przestrzenie nazw

Zanim zaczniemy pracować z Aspose.Tasks dla .NET, zaimportujmy niezbędne przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;


```

## Stosowanie trybu automatycznego obliczania

### Krok 1: Utwórz nową instancję projektu

 Zainicjuj nowy`Project` obiekt i ustaw go`CalculationMode` własność do`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Krok 2: Ustaw datę rozpoczęcia projektu i dodaj zadania

Określ datę rozpoczęcia projektu i dodaj do niego zadania.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Krok 3: Połącz zadania

Ustal zależności pomiędzy zadaniami.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Krok 4: Sprawdź ponownie obliczone daty

Sprawdź, czy daty zostały automatycznie przeliczone.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// W razie potrzeby dodaj więcej weryfikacji
```

## Stosowanie trybu obliczeń ręcznych

### Krok 1: Utwórz nową instancję projektu

 Zainicjuj nowy`Project` obiekt i ustaw go`CalculationMode` własność do`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Krok 2: Ustaw datę rozpoczęcia projektu i dodaj zadania

Określ datę rozpoczęcia projektu i dodaj do niego zadania.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Krok 3: Sprawdź właściwości zadania

Sprawdź, czy właściwości zadania są ustawione poprawnie w trybie ręcznym.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// W razie potrzeby dodaj więcej weryfikacji
```

### Krok 4: Połącz zadania i zweryfikuj daty

Połącz zadania ze sobą i sprawdź, czy ich daty nie zostały przeliczone.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Stosowanie żadnego trybu obliczeń

### Krok 1: Utwórz nową instancję projektu

 Zainicjuj nowy`Project` obiekt i ustaw go`CalculationMode` własność do`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Krok 2: Dodaj nowe zadanie

Dodaj nowe zadanie do projektu.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Krok 3: Sprawdź właściwości zadania

Sprawdź, czy właściwości zadania nie są obliczane automatycznie.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// W razie potrzeby dodaj więcej weryfikacji
```

## Wniosek

W tym samouczku sprawdziliśmy tryby obliczeń dostępne w Aspose.Tasks dla .NET i dowiedzieliśmy się, jak zastosować je w praktycznych scenariuszach. Niezależnie od tego, czy potrzebujesz trybu automatycznego, ręcznego, czy też nie, Aspose.Tasks zapewnia elastyczność dostosowaną do wymagań Twojego projektu.

## Często zadawane pytania

### P1: Czy mogę dynamicznie zmieniać tryb obliczeń w czasie wykonywania?

Odpowiedź 1: Tak, możesz zmienić tryb obliczeń projektu w dowolnym momencie jego działania, modyfikując plik`CalculationMode` nieruchomość.

### P2: Czy Aspose.Tasks obsługuje inne formaty plików do zarządzania projektami oprócz Microsoft Project?

O2: Aspose.Tasks koncentruje się głównie na formatach plików Microsoft Project, ale obsługuje także inne formaty, takie jak Primavera P6 XML, Primavera DB i Asta Powerproject XML.

### P3: Czy Aspose.Tasks nadaje się zarówno do projektów na małą skalę, jak i na poziomie przedsiębiorstwa?

A3: Absolutnie! Aspose.Tasks został zaprojektowany, aby zaspokoić potrzeby zarówno projektów na małą skalę, jak i na poziomie przedsiębiorstwa, dzięki wszechstronnym funkcjom i solidnym interfejsom API.

### P4: Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami i frameworkami .NET?

O4: Tak, możesz bezproblemowo zintegrować Aspose.Tasks z innymi bibliotekami i frameworkami .NET, aby zwiększyć funkcjonalność swoich aplikacji.

### P5: Czy dostępne jest forum społecznościowe lub kanał wsparcia dla użytkowników Aspose.Tasks?

 A5: Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.