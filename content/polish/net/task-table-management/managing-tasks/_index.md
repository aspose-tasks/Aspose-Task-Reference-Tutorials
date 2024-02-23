---
title: Zarządzanie zadaniami w Aspose.Tasks
linktitle: Zarządzanie zadaniami w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zapoznaj się z kompleksowym przewodnikiem na temat zarządzania zadaniami za pomocą Aspose.Tasks dla .NET. Dowiedz się, jak dodawać, wyświetlać podzielone części, przenosić, pobierać/ustawiać właściwości i nie tylko.
type: docs
weight: 15
url: /pl/net/task-table-management/managing-tasks/
---
## Wstęp
Jeśli jesteś programistą .NET i chcesz efektywnie zarządzać zadaniami w swoich projektach, Aspose.Tasks dla .NET zapewnia solidne rozwiązanie. Ten samouczek poprowadzi Cię przez różne aspekty zarządzania zadaniami przy użyciu Aspose.Tasks, oferując instrukcje krok po kroku i przykłady kodu. Niezależnie od tego, czy dodajesz zadania, wyświetlasz podzielone części, przenosisz zadania pod tym samym elementem nadrzędnym, pobierasz/ustawiasz właściwości zadania, przeglądasz przypisania zadań, czytasz plany bazowe zadań czy usuwasz zadania, ten przewodnik pomoże Ci.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Biblioteka Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Tasks dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
2. Katalog dokumentów: skonfiguruj katalog, w którym będą przechowywane dokumenty projektu.
## Importuj przestrzenie nazw
W swoim projekcie .NET uwzględnij niezbędne przestrzenie nazw do pracy z Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Dodawanie zadania do projektu
```csharp
// Utwórz nowy projekt
var project = new Project();
// Dodaj zadanie
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Zapisz projekt
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Wyświetlanie podzielonych części zadania
```csharp
// Załaduj projekt z podzielonymi zadaniami
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Uzyskaj dostęp do zadania
var task = project.RootTask.Children.GetById(4);
// Wyświetl podzielone części
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Przenoszenie zadania pod tym samym elementem nadrzędnym
```csharp
try
{
    // Załaduj projekt
    var project = new Project(DataDir + "MoveTask.mpp");
    // Przenieś zadania o identyfikatorze 5 przed zadaniem o identyfikatorze 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Zapisz zmodyfikowany projekt
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Pobieranie/ustawianie właściwości zadania
```csharp
// Utwórz nowy projekt
var project = new Project();
// Dodaj zadanie i ustaw właściwości
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Zbieraj i wyświetlaj właściwości zadania
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterowanie po zadaniach
```csharp
// Załaduj projekt z zadaniami
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Zbieraj i wyświetlaj przypisania zadań
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Odczytywanie linii bazowych zadania
```csharp
// Utwórz nowy projekt
var project = new Project();
// Dodaj zadanie i ustal poziom bazowy
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Wyświetl czas bazowy zadania
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Usuwanie zadania
```csharp
// Utwórz nowy projekt
var project = new Project();
// Dodaj zadanie
var task = project.RootTask.Children.Add("Task");
// Wyświetl liczbę zadań przed i po usunięciu
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Usuń zadanie
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Wniosek
Zarządzanie zadaniami w Aspose.Tasks dla .NET to bezproblemowy proces z użyciem dostarczonych przykładów. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, zastosowanie tych technik zwiększy Twoje możliwości zarządzania projektami.
## Często Zadawane Pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi frameworkami .NET?
O: Tak, Aspose.Tasks obsługuje różne platformy .NET, zapewniając kompatybilność z Twoim środowiskiem programistycznym.
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?
 Odp.: Możesz uzyskać 30-dniową tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Czy są jakieś ograniczenia podczas pracy z podzielonymi zadaniami w Aspose.Tasks?
 O: Dzielenie zadań to zaawansowana funkcja, można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/tasks/net/).
### P: Czy mogę dostosować właściwości zadania poza tym, co pokazano w przykładach?
Odp.: Absolutnie! Aspose.Tasks zapewnia rozbudowane opcje dostosowywania właściwości zadań. Sprawdź dokumentację, aby uzyskać więcej szczegółów.
### P: Jak uzyskać wsparcie dla Aspose.Tasks?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.