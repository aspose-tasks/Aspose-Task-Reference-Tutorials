---
date: 2026-03-24
description: Dowiedz się, jak ustawić tryb obliczeń w Aspose.Tasks dla .NET, obejmujący
  tryb automatyczny, ręczny oraz wyłączony, aby zarządzać zależnościami zadań.
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Jak ustawić tryb obliczeń w Aspose.Tasks dla .NET
url: /pl/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić tryb obliczeń w Aspose.Tasks dla .NET

## Wprowadzenie

Aspose.Tasks for .NET to potężne API, które umożliwia programowe pracowanie z plikami Microsoft Project. Jednym z najważniejszych ustawień, z którymi się spotkasz, jest **tryb obliczeń**, który kontroluje sposób aktualizacji dat zadań i harmonogramów projektu. W tym samouczku dowiesz się **jak ustawić tryb obliczeń**, poznasz **automatyczny tryb obliczeń**, **ręczny tryb obliczeń** oraz **tryb bez obliczeń**, oraz zobaczysz, jak te opcje wpływają na **zarządzanie zależnościami zadań**, **tworzenie daty rozpoczęcia projektu** i **łączenie zależności zakończenie‑rozpoczęcie**.

## Quick Answers
- **Co to jest tryb obliczeń?** Określa, czy daty zadań są przeliczane automatycznie, ręcznie, czy wcale.  
- **Dlaczego używać ręcznego trybu obliczeń?** Aby mieć pełną kontrolę nad momentem odświeżania harmonogramu, przydatne przy masowych aktualizacjach.  
- **Jaki tryb jest domyślny?** Automatyczny tryb obliczeń, który natychmiast aktualizuje daty po wprowadzeniu zmian.  
- **Czy mogę zmienić tryb w czasie działania?** Tak — po prostu ustaw właściwość `CalculationMode` na obiekcie `Project`.  
- **Czy potrzebna jest licencja?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.

## Co to jest „ustawianie trybu obliczeń” w Aspose.Tasks?

Ustawienie trybu obliczeń jest tak proste, jak przypisanie wartości wyliczeniowej do właściwości `Project.CalculationMode`. Wyliczenie oferuje trzy opcje: `Automatic`, `Manual` i `None`. Wybór odpowiedniego trybu zależy od Twojego przepływu pracy — czy potrzebujesz natychmiastowych aktualizacji, przetwarzania wsadowego, czy pełnej kontroli.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

1. **Visual Studio** – dowolną nowszą wersję (2019, 2022 lub późniejszą).  
2. **Aspose.Tasks for .NET** – pobierz i zainstaluj bibliotekę z [tutaj](https://releases.aspose.com/tasks/net/).  
3. **Podstawową znajomość C#** – powinieneś być zaznajomiony z tworzeniem aplikacji konsolowych i używaniem pakietów NuGet.

## Importowanie przestrzeni nazw

Zanim zaczniemy pracę z Aspose.Tasks for .NET, zaimportujmy niezbędne przestrzenie nazw:

```csharp
using Aspose.Tasks;
using System;
```

## Jak ustawić tryb obliczeń

Poniżej znajdziesz przykłady krok po kroku dla każdego trybu obliczeń. Bloki kodu pozostają niezmienione w stosunku do oryginalnego samouczka; otaczające wyjaśnienia zostały rozbudowane dla większej przejrzystości.

### Stosowanie automatycznego trybu obliczeń

Tryb automatyczny przelicza daty natychmiast, gdy tylko modyfikujesz zadania lub połączenia.

#### Krok 1: Utwórz nową instancję klasy Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Krok 2: Ustaw datę rozpoczęcia projektu i dodaj zadania

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Krok 3: Połącz zadania (zakończenie‑rozpoczęcie)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Krok 4: Zweryfikuj przeliczone daty

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Stosowanie ręcznego trybu obliczeń

Ręczny tryb wyłącza automatyczne aktualizacje, dając możliwość przetwarzania zmian wsadowo przed wymuszeniem przeliczenia.

#### Krok 1: Utwórz nową instancję klasy Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Krok 2: Ustaw datę rozpoczęcia projektu i dodaj zadania

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Krok 3: Zweryfikuj właściwości zadania

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Krok 4: Połącz zadania i zweryfikuj daty (brak automatycznego przeliczania)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Stosowanie trybu bez obliczeń

Tryb bez obliczeń wyłącza wszystkie wewnętrzne kalkulacje. Używaj go, gdy potrzebujesz jedynie odczytu lub eksportu danych bez zmian w harmonogramie.

#### Krok 1: Utwórz nową instancję klasy Project

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Krok 2: Dodaj nowe zadanie

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Krok 3: Zweryfikuj właściwości zadania (brak automatycznych identyfikatorów)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Typowe problemy i rozwiązania

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Daty nie aktualizują się po połączeniu zadań | Projekt jest w trybie **Manual** lub **None** | Ustaw `project.CalculationMode = CalculationMode.Automatic` lub wywołaj ręcznie `project.Calculate()` |
| Identyfikatory zadań pozostają 0 | Używanie trybu **None** uniemożliwia generowanie ID | Przełącz na tryb **Automatic** lub **Manual**, a następnie przelicz |
| Łączenie nie powiodło się z `ArgumentException` | Data rozpoczęcia poprzednika jest późniejsza niż następnika przy użyciu trybu **Manual** bez przeliczenia | Upewnij się, że daty rozpoczęcia są prawidłowe lub przelicz po dodaniu połączeń |

## Najczęściej zadawane pytania

**Q1: Czy mogę zmienić tryb obliczeń dynamicznie w czasie działania?**  
A1: Tak, możesz modyfikować właściwość `CalculationMode` w dowolnym miejscu kodu, a następnie wywołać `project.Calculate()`, jeśli potrzebna jest natychmiastowa aktualizacja.

**Q2: Czy Aspose.Tasks obsługuje inne formaty plików zarządzania projektami oprócz Microsoft Project?**  
A2: Aspose.Tasks koncentruje się głównie na formatach Microsoft Project, ale obsługuje także Primavera P6 XML, Primavera DB oraz Asta Powerproject XML.

**Q3: Czy Aspose.Tasks jest odpowiedni zarówno dla małych, jak i dużych projektów korporacyjnych?**  
A3: Zdecydowanie. API skaluje się od prostych list zadań po złożone, wieloetapowe harmonogramy korporacyjne.

**Q4: Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami i frameworkami .NET?**  
A4: Tak, możesz łączyć Aspose.Tasks z ASP.NET, WPF, Xamarin lub dowolną inną technologią .NET, aby tworzyć rozbudowane rozwiązania do zarządzania projektami.

**Q5: Czy istnieje forum społecznościowe lub kanał wsparcia dostępny dla użytkowników Aspose.Tasks?**  
A5: Tak, możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania wsparcia społeczności i dyskusji.

---

**Ostatnia aktualizacja:** 2026-03-24  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}