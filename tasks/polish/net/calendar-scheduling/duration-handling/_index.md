---
title: Obsługa czasu trwania w Aspose.Tasks
linktitle: Obsługa czasu trwania w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie obsługiwać czasy trwania w Aspose.Tasks dla .NET, korzystając z samouczków krok po kroku.
weight: 30
url: /pl/net/calendar-scheduling/duration-handling/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa czasu trwania w Aspose.Tasks

## Wstęp

Efektywna obsługa czasów trwania ma kluczowe znaczenie w aplikacjach do zarządzania projektami. Aspose.Tasks dla .NET zapewnia solidną funkcjonalność do efektywnego zarządzania czasem trwania. W tym samouczku omówimy różne aspekty obsługi czasu trwania przy użyciu Aspose.Tasks dla .NET.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

1. Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna do zrozumienia i wdrożenia przykładów.
2. Visual Studio: zainstaluj Visual Studio IDE, aby tworzyć i uruchamiać aplikacje .NET.
3.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

Podzielmy każdy przykład na wiele kroków w formie przewodnika krok po kroku:

## Aktualizacja czasu trwania zadań

### Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Uzyskaj zadanie i czas trwania

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Krok 3: Aktualizuj czas trwania

```csharp
duration1 = duration1.Add(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Krok 4: Wyświetl zaktualizowany czas trwania

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Odejmowanie czasu trwania zadań

### Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Uzyskaj zadanie i czas trwania

```csharp
var task1 = project.RootTask.Children.GetById(1);
var duration1 = task1.Get(Tsk.Duration);
```

### Krok 3: Odejmij czas trwania

```csharp
duration1 = duration1.Subtract(project.GetDuration(1, TimeUnitType.Day));
task1.Set(Tsk.Duration, duration1);
```

### Krok 4: Wyświetl zaktualizowany czas trwania

```csharp
Console.WriteLine("The duration of task 1: " + task1.Get(Tsk.Duration));
```

## Konwersja czasu trwania na TimeSpan

### Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Uzyskaj zadanie i czas trwania

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Krok 3: Konwertuj czas trwania na TimeSpan

```csharp
Console.WriteLine("Time span of duration: " + duration.TimeSpan);
```

## Konwersja czasu trwania na ciąg

### Krok 1: Załaduj plik projektu

```csharp
var project = new Project(DataDir + "TaskDurations.mpp");
```

### Krok 2: Uzyskaj zadanie i czas trwania

```csharp
var task = project.RootTask.Children.GetById(1);
var duration = task.Get(Tsk.Duration);
```

### Krok 3: Konwertuj czas trwania na ciąg

```csharp
Console.WriteLine("The duration as a string: " + duration.ToString());
```

## Wniosek

tym samouczku omówiliśmy różne aspekty obsługi czasu trwania w Aspose.Tasks dla .NET. Zrozumienie czasów trwania i skuteczne zarządzanie nimi jest niezbędne do skutecznego zarządzania projektami. Aspose.Tasks zapewnia wszechstronne funkcje upraszczające zadania związane z zarządzaniem czasem trwania w aplikacjach .NET.

## Często zadawane pytania

### P1: Co to jest Aspose.Tasks dla .NET?

O1: Aspose.Tasks dla .NET to potężna biblioteka do pracy z plikami Microsoft Project w aplikacjach .NET.

### P2: Czy Aspose.Tasks obsługuje złożone struktury projektu?

Odpowiedź 2: Tak, Aspose.Tasks może z łatwością obsługiwać złożone struktury projektu, udostępniając rozbudowane interfejsy API do manipulacji.

### P3: Czy Aspose.Tasks dla .NET jest kompatybilny z .NET Core?

O3: Tak, Aspose.Tasks dla .NET jest kompatybilny z .NET Core, co pozwala na używanie go w aplikacjach wieloplatformowych.

### P4: Czy Aspose.Tasks obsługuje odczytywanie i zapisywanie plików Microsoft Project?

O4: Tak, Aspose.Tasks obsługuje odczytywanie i zapisywanie plików Microsoft Project w różnych formatach, w tym MPP, XML i MPX.

### P5: Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?

O5: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
