---
title: Wyodrębnianie informacji o powtarzających się zadaniach w Aspose.Tasks
linktitle: Wyodrębnianie informacji o powtarzających się zadaniach w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak wyodrębnić informacje o powtarzających się zadaniach z plików MS Project za pomocą Aspose.Tasks dla .NET. Łatwa integracja dla programistów .NET.
type: docs
weight: 13
url: /pl/net/rate-recurring-tasks/recurring-task-information/
---
## Wstęp
Aspose.Tasks dla .NET to potężna biblioteka, która umożliwia programistom pracę z plikami Microsoft Project w ich aplikacjach .NET. W tym samouczku przyjrzymy się, jak wyodrębnić informacje o powtarzających się zadaniach z plików MS Project za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Podstawowa znajomość języka programowania C#.
2. Program Visual Studio zainstalowany w systemie.
3.  Zainstalowana biblioteka Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
## Importuj przestrzenie nazw
Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego kodu C#:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Podzielmy teraz przykład na kilka kroków:
## Krok 1: Skonfiguruj ścieżkę pliku projektu
```csharp
String DataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do pliku MS Project.
## Krok 2: Załaduj plik MS Project
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Ta linia inicjuje nową`Project` obiekt, ładując plik MS Project określony ścieżką.
## Krok 3: Przeczytaj powtarzające się informacje o zadaniach
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Dostęp i wyświetlanie informacji o powtarzających się zadaniach
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // W razie potrzeby kontynuuj wyświetlanie innych informacji o zadaniach cyklicznych
}
```
Ta pętla iteruje po wszystkich zadaniach w projekcie i sprawdza, czy z każdym zadaniem są powiązane powtarzające się informacje. Jeśli tak, pobiera i wyświetla różne właściwości zadania cyklicznego, takie jak data rozpoczęcia, czas trwania, data zakończenia itp.
## Wniosek
tym samouczku nauczyliśmy się, jak wyodrębniać informacje o powtarzających się zadaniach z plików MS Project za pomocą Aspose.Tasks dla .NET. Dzięki tej wiedzy możesz teraz zintegrować tę funkcjonalność z aplikacjami .NET, aby efektywniej pracować z powtarzającymi się zadaniami.
## Często zadawane pytania
### P: Czy mogę modyfikować informacje o zadaniach cyklicznych za pomocą Aspose.Tasks dla .NET?
O: Tak, możesz programowo modyfikować informacje o zadaniach cyklicznych, korzystając z dostarczonych interfejsów API.
### P: Czy Aspose.Tasks obsługuje inne formaty plików projektów oprócz MS Project?
O: Tak, Aspose.Tasks obsługuje różne formaty plików projektów, takie jak MPP, XML i CSV.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?
 Odp.: Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).
### P: Jak mogę uzyskać pomoc techniczną dla Aspose.Tasks dla .NET?
 Odp.: Możesz uzyskać pomoc techniczną na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).