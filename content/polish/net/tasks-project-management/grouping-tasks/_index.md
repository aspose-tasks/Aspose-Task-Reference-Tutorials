---
title: Efektywne grupowanie zadań MS Project za pomocą Aspose.Tasks
linktitle: Grupowanie zadań w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie grupować zadania Microsoft Project za pomocą Aspose.Tasks dla .NET.
type: docs
weight: 25
url: /pl/net/tasks-project-management/grouping-tasks/
---
## Wstęp
Zarządzanie zadaniami w programie Microsoft Project może czasami stanowić wyzwanie, zwłaszcza jeśli chodzi o ich efektywną organizację. Aspose.Tasks dla .NET oferuje kompleksowe rozwiązanie tego problemu, zapewniając funkcje efektywnego grupowania zadań. W tym samouczku przyjrzymy się, jak grupować zadania MS Project za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1.  Biblioteka Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla .NET ze strony[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw do swojego projektu C#, aby móc korzystać z funkcjonalności Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Krok 1: Załaduj plik projektu MS
Rozpocznij od załadowania pliku MS Project przy użyciu następującego kodu:
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Krok 2: Uzyskaj dostęp do grup zadań
Następnie przejdźmy do grup zadań w projekcie:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
```
## Krok 3: Pobierz informacje o grupie
Teraz pobierz informacje o grupie zadaniowej:
```csharp
Console.WriteLine("Task Group Uid: " + group.Uid);
Console.WriteLine("Task Group Index: " + group.Index);
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Is Task Group Maintain Hierarchy?: " + group.MaintainHierarchy);
Console.WriteLine("Is Task Group Show In Menu?: " + group.ShowInMenu);
Console.WriteLine("Is Task Group Show Summary?: " + group.ShowSummary);
```
## Krok 4: Kryteria grupy dostępu
Uzyskaj dostęp do kryteriów ustawionych dla grupy zadaniowej:
```csharp
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
## Krok 5: Uzyskaj informacje o kryterium
Uzyskaj szczegółowe informacje o każdym kryterium:
```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Task Criterion Field: " + criterion.Field);
    Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
    Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
    Console.WriteLine("Task Criterion Pattern: " + criterion.Pattern);
    if (group == criterion.ParentGroup)
    {
        Console.WriteLine("Parent Group is equal to task Group.");
    }
    Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
    Console.WriteLine("Font Size: " + criterion.Font.Size);
    Console.WriteLine("Font Style: " + criterion.Font.Style);
    Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
}
```
Wykonując te kroki, możesz efektywnie grupować zadania MS Project przy użyciu Aspose.Tasks dla .NET, usprawniając organizację i zarządzanie danymi projektu.

## Wniosek
Podsumowując, Aspose.Tasks dla .NET zapewnia potężne możliwości grupowania zadań MS Project, pozwalając na lepszą organizację i zarządzanie danymi projektu. Wykonując kroki opisane w tym samouczku, możesz efektywnie wykorzystać te funkcje w aplikacjach .NET.
## Często zadawane pytania
### Czy mogę grupować zadania według niestandardowych kryteriów?
Tak, możesz zdefiniować niestandardowe kryteria grupowania zadań zgodnie ze swoimi specyficznymi wymaganiami, korzystając z Aspose.Tasks dla .NET.
### Czy Aspose.Tasks obsługuje różne wersje plików MS Project?
Tak, Aspose.Tasks obsługuje różne wersje plików MS Project, zapewniając kompatybilność i bezproblemową integrację.
### Czy dostępna jest wersja próbna Aspose.Tasks dla .NET?
 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/).
### Czy mogę dostosować wygląd pogrupowanych zadań?
Absolutnie Aspose.Tasks zapewnia opcje dostosowywania wyglądu pogrupowanych zadań, w tym kolorów komórek, czcionek i stylów.
### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla .NET?
 Możesz znaleźć wsparcie i pomoc dla Aspose.Tasks dla .NET w[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).