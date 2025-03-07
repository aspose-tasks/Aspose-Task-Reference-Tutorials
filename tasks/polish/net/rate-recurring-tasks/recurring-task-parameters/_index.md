---
title: Ustawianie powtarzających się parametrów zadań w Aspose.Tasks
linktitle: Ustawianie powtarzających się parametrów zadań w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak ustawić parametry zadań cyklicznych w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. Kompleksowy samouczek z przewodnikiem krok po kroku.
weight: 14
url: /pl/net/rate-recurring-tasks/recurring-task-parameters/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie powtarzających się parametrów zadań w Aspose.Tasks

## Wstęp
tym samouczku przeprowadzimy Cię przez proces ustawiania parametrów zadań cyklicznych programu Microsoft Project za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Podstawowa znajomość języka programowania C#.
2. Zainstalowano Visual Studio lub dowolne inne środowisko C# IDE.
3. Zainstalowana biblioteka Aspose.Tasks dla .NET, do której odwołuje się Twój projekt.

## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#:
```csharp
using Aspose.Tasks;
using System;

```
## Krok 1: Zdefiniuj katalog dokumentów
```csharp
String DataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do katalogu dokumentów.
## Krok 2: Załaduj plik projektu
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Ta linia kodu ładuje plik Microsoft Project do pliku`project` zmienny.
## Krok 3: Zdefiniuj parametry zadania cyklicznego
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Tutaj definiujesz parametry zadania cyklicznego, takie jak nazwa zadania, czas trwania, wzorzec powtarzania, zakres powtarzania i to, czy ignorować kalendarz zasobu.
## Krok 4: Ustaw kalendarz dla zadania cyklicznego
```csharp
parameters.SetCalendar(project, "Standard");
```
Ten krok ustawia kalendarz dla zadania cyklicznego. W tym przykładzie ustawia kalendarz na „Standardowy”.
## Krok 5: Dodaj parametry do projektu
```csharp
project.RootTask.Children.Add(parameters);
```
Na koniec dodaj parametry do zadania głównego projektu.

## Wniosek
tym samouczku pokazaliśmy, jak ustawić parametry zadań cyklicznych programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz efektywnie zarządzać powtarzającymi się zadaniami w swoich projektach.
## Często zadawane pytania
### Czy mogę bardziej dostosować wzór powtarzania?
Tak, Aspose.Tasks zapewnia różne wzorce powtarzania i opcje, które można dostosować do wymagań projektu.
### Czy przed zakupem dostępna jest wersja próbna?
 Tak, możesz pobrać bezpłatną wersję próbną z Aspose.Tasks[strona internetowa](https://purchase.aspose.com/buy) do oceny funkcji biblioteki.
### Czy Aspose.Tasks obsługuje inne formaty plików projektów?
Tak, Aspose.Tasks obsługuje różne formaty plików projektów, w tym MPP, XML, XLSX i inne.
### Czy mogę uzyskać wsparcie, jeśli napotkam jakiekolwiek problemy podczas wdrożenia?
Tak, możesz odwiedzić forum Aspose.Tasks, aby uzyskać pomoc społeczności lub skontaktować się z obsługą techniczną w celu uzyskania bezpośredniej pomocy.
### Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?
 Licencję tymczasową można uzyskać od firmy[strona internetowa](https://purchase.aspose.com/temporary-license/) do celów testowych.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
