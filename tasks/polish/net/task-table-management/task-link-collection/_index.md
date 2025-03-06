---
title: Obsługa łączy zadań w Aspose.Tasks
linktitle: Obsługa łączy zadań w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Poznaj moc Aspose.Tasks dla .NET w efektywnym zarządzaniu łączami zadań projektowych. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby ulepszyć zarządzanie projektami.
type: docs
weight: 19
url: /pl/net/task-table-management/task-link-collection/
---
## Wstęp
Witamy w przewodniku krok po kroku dotyczącym obsługi łączy zadań w Aspose.Tasks dla .NET! Powiązania zadań odgrywają kluczową rolę w zarządzaniu projektami, pozwalając na ustanawianie relacji pomiędzy zadaniami i tworzenie zależności. W tym samouczku przeprowadzimy Cię przez proces pracy z kolekcjami łączy do zadań przy użyciu Aspose.Tasks.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Aspose.Tasks dla biblioteki .NET: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/tasks/net/).
2. Przykładowy plik projektu: Przygotuj przykładowy plik projektu (np. „SampleProject.mpp”), który będzie wyświetlany wraz z przykładami.
Teraz zaczynajmy!
## Importuj przestrzenie nazw
W projekcie .NET pamiętaj o zaimportowaniu przestrzeni nazw niezbędnych do pracy z Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Załaduj projekt i zadania dostępu
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
// Załaduj projekt
var project = new Project(DataDir + "SampleProject.mpp");
// Dostęp do zadań według identyfikatora
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Krok 2: Utwórz łącza do zadań
Połącz zadania, aby ustalić zależności:
```csharp
// Połącz zadania za pomocą zależności FinishToStart
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Krok 3: Wydrukuj łącza do zadań
Wydrukuj linki do zadań dla projektu:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Iteruj po łączach zadań
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Krok 4: Edytuj łącze zadania
Edytuj łącze zadania według dostępu do indeksu:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Krok 5: Usuń linki do zadań
Usuń wszystkie linki do zadań z projektu:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się obsługiwać łącza do zadań w Aspose.Tasks dla .NET. Ten obszerny przewodnik omawiał ładowanie projektu, tworzenie łączy do zadań, drukowanie łączy, edycję łączy i usuwanie łączy do zadań.
Zachęcamy do zapoznania się z większą liczbą funkcji i funkcjonalności oferowanych przez Aspose.Tasks, aby ulepszyć swoje doświadczenie w zarządzaniu projektami.
## Często zadawane pytania
### Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami .NET?
Tak, Aspose.Tasks został zaprojektowany tak, aby bezproblemowo współpracować ze wszystkimi wersjami .NET.
### Czy mogę tworzyć niestandardowe typy łączy zadań za pomocą Aspose.Tasks?
Obecnie Aspose.Tasks obsługuje standardowe typy łączy zadań, a niestandardowe typy łączy nie są dostępne.
### Jak mogę zastosować ograniczenia do zadań w Aspose.Tasks?
 Można zastosować wiązania za pomocą opcji`ConstraintType` własność`Task` klasa w Aspose.Tasks.
### Czy są jakieś ograniczenia dotyczące rozmiaru plików projektu, które Aspose.Tasks może obsłużyć?
Aspose.Tasks może efektywnie obsługiwać duże pliki projektu przy minimalnym wpływie na wydajność.
### Czy istnieje forum społecznościowe dla wsparcia Aspose.Tasks?
 Tak, możesz znaleźć wsparcie i nawiązać kontakt ze społecznością na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).