---
title: Obsługa podzielonych części projektu MS w Aspose.Tasks
linktitle: Obsługa podzielonych części w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie obsługiwać podzielone części MS Project za pomocą Aspose.Tasks dla .NET. Usprawnij przepływ pracy w zarządzaniu projektami.
weight: 18
url: /pl/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa podzielonych części projektu MS w Aspose.Tasks


## Wstęp
Zarządzanie podzielonymi częściami MS Project może być kluczowym aspektem zarządzania projektami podczas korzystania z Aspose.Tasks dla .NET. W tym samouczku odkryjemy, jak skutecznie obsługiwać podzielone części, korzystając ze wskazówek krok po kroku.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1.  Instalacja Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[strona internetowa](https://releases.aspose.com/tasks/net/).
   
2. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw
W kodzie C# pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Krok 1: Tworzenie instancji projektu
```csharp
var project = new Project();
```
 Utwórz nową instancję`Project` klasa.
## Krok 2: Ustalanie dat rozpoczęcia i zakończenia projektu
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Ustaw daty rozpoczęcia i zakończenia projektu.
## Krok 3: Dodawanie zadania
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Dodaj nowe zadanie do projektu.
## Krok 4: Ustawianie właściwości zadania
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Ustaw właściwości, takie jak stan ręczny, data rozpoczęcia i czas trwania zadania.
## Krok 5: Dodawanie przypisań zasobów
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Dodaj przypisania zasobów do zadania.
## Krok 6: Ustawianie właściwości przypisania
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Ustaw właściwości, takie jak data rozpoczęcia, praca i data zakończenia przydziału.
## Krok 7: Generowanie danych okresowych
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Generuj dane okresowe dla zadania w oparciu o kalendarz projektu.
## Krok 8: Podział zadania
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Podziel zadanie na wiele części w określonym przedziale czasowym.
## Krok 9: Iteracja po podzielonych częściach
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Wykonaj iterację po podzielonych częściach zadania i wydrukuj daty ich rozpoczęcia i zakończenia.

## Wniosek
Efektywna obsługa podzielonych części MS Project w Aspose.Tasks dla .NET ma kluczowe znaczenie dla efektywności zarządzania projektami. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zarządzać podzielonymi zadaniami i usprawnić przepływ pracy w zarządzaniu projektami.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z innymi frameworkami .NET?
Odp.: Tak, Aspose.Tasks dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Standard.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 Odpowiedź: Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### P: Czy Aspose.Tasks dla .NET obsługuje zarządzanie zasobami?
O: Tak, Aspose.Tasks for .NET pozwala efektywnie zarządzać zasobami projektu.
### P: Czy mogę dostosować kalendarze projektów za pomocą Aspose.Tasks dla .NET?
Odp.: Oczywiście, możesz dostosować kalendarze projektów zgodnie z wymaganiami projektu.
### P: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla .NET?
 Odp.: Wsparcie i pomoc można znaleźć na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
