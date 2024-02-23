---
title: Zbiór przypisań zasobów w Aspose.Tasks
linktitle: Zbiór przypisań zasobów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zarządzać przypisaniami zasobów w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. Samouczek krok po kroku z przykładami kodu.
type: docs
weight: 12
url: /pl/net/resource-risk-analysis/resource-assignment-collection/
---
## Wstęp
Witamy w tym kompleksowym samouczku na temat zarządzania przypisaniami zasobów w programie Microsoft Project przy użyciu Aspose.Tasks dla .NET. W tym samouczku omówimy ten proces krok po kroku, upewniając się, że dobrze rozumiesz, jak efektywnie manipulować przydziałami zasobów. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik przeprowadzi Cię przez wszystko, co musisz wiedzieć.
## Warunki wstępne
Zanim zagłębimy się w kod, upewnij się, że masz następującą konfigurację:
1. Zainstalowany Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowany Aspose.Tasks dla .NET w swoim środowisku programistycznym. Jeśli nie, możesz go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Podstawowa znajomość języka C#: W tym samouczku założono, że masz podstawową wiedzę na temat języka programowania C#.
3. Plik programu Microsoft Project: przygotuj plik programu Microsoft Project do celów testowych. Jeśli go nie masz, możesz utworzyć przykładowy plik.

## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Krok 1: Załaduj plik projektu
Rozpocznij od załadowania pliku Microsoft Project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Krok 2: Dodaj zadanie i zasób
Teraz dodajmy zadanie i zasób do projektu:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Krok 3: Przypisz zasób do zadania
Następnie przypiszemy zasób do zadania:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Krok 4: Praca z różnymi typami przydziałów
Można także pracować z przypisaniami obejmującymi jednostki lub koszty:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Ustaw właściwości przydziałów z jednostkami i kosztami w podobny sposób, jak pokazano w kroku 3
```
## Krok 5: Wydrukuj zadania
Wydrukuj zadania do projektu:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Wydrukuj szczegóły zadania
}
```
## Krok 6: Pobierz przypisanie według UID
Możesz pobrać przypisania według UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Krok 7: Sprawdź status tylko do odczytu
Sprawdź, czy kolekcja przypisań zasobów jest tylko do odczytu:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Krok 8: Konwertuj kolekcję na listę i iteruj
Przekonwertuj kolekcję na listę i wykonaj iterację po niej:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Wniosek
Gratulacje! Nauczyłeś się, jak zarządzać przypisaniami zasobów w Microsoft Project przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz efektywnie manipulować zadaniami i zasobami, dzięki czemu zarządzanie projektami jest proste.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla .NET z różnymi wersjami plików Microsoft Project?
O: Tak, Aspose.Tasks dla .NET obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### P: Czy przed zakupem Aspose.Tasks dla .NET dostępna jest wersja próbna?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla .NET od[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy podczas korzystania z Aspose.Tasks dla .NET?
 Odp.: Możesz szukać pomocy na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy mogę używać licencji tymczasowych dla Aspose.Tasks dla .NET?
 Odpowiedź: Tak, licencje tymczasowe są dostępne do celów próbnych. Możesz dostać jeden z[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę kupić pełną licencję na Aspose.Tasks dla .NET?
 Odp.: Możesz kupić pełną licencję w sklepie internetowym Aspose[Tutaj](https://purchase.aspose.com/buy).