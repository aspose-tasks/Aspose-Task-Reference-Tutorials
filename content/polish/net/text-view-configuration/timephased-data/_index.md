---
title: Opanuj obsługę danych okresowych za pomocą Aspose.Tasks dla .NET
linktitle: Obsługa danych okresowych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Przeglądaj Aspose.Tasks dla .NET, aby bez wysiłku obsługiwać dane okresowe, usprawniać planowanie projektów i optymalizować zarządzanie zasobami. #Aspose #Zadania #MS Projekt
type: docs
weight: 14
url: /pl/net/text-view-configuration/timephased-data/
---
## Wstęp
W świecie zarządzania projektami efektywne przetwarzanie danych okresowych ma kluczowe znaczenie dla alokacji zasobów, szacowania kosztów i ogólnego planowania projektu. Aspose.Tasks dla .NET zapewnia potężne rozwiązanie do płynnej pracy z niestandardowymi danymi okresowymi. Ten samouczek poprowadzi Cię przez proces obsługi danych okresowych za pomocą Aspose.Tasks, umożliwiając optymalizację zarządzania zasobami w Twoich projektach.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość koncepcji zarządzania projektami.
-  Zainstalowano Aspose.Tasks dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
- Edytor kodu, taki jak Visual Studio, do implementacji dostarczonych przykładów.
## Importuj przestrzenie nazw
projekcie .NET pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw, aby wykorzystać funkcje Aspose.Tasks. Dodaj następujące wiersze na początku pliku kodu:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Podzielmy teraz podany przykład na wiele kroków, które poprowadzą Cię przez obsługę danych okresowych za pomocą Aspose.Tasks:
## Krok 1: Skonfiguruj projekt
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
Tutaj inicjujemy nowy projekt i ustawiamy jego tryb obliczeń.
## Krok 2: Zdefiniuj zasoby i zadania
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
Utwórz zasoby pracy i kosztów, a także zadanie, aby symulować strukturę projektu.
## Krok 3: Przypisz zasoby do zadania
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
Przypisz zasoby pracy i kosztów do zadania.
## Krok 4: Dodaj niestandardowe dane okresowe
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
// Podobne kroki w przypadku costAssignment
costAssignment.TimephasedData.Clear();
```
Dodaj niestandardowe dane okresowe zarówno dla przydziałów pracy, jak i kosztów.
## Krok 5: Wyświetl dane okresowe
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        // Wyświetlaj istotne informacje na temat każdego okresowego wprowadzania danych
    }
}
```
Na koniec wyświetl dane okresowe dla każdego zadania.
#
## Wniosek
Efektywna obsługa danych okresowych w Aspose.Tasks otwiera nowe możliwości szczegółowego planowania projektu i zarządzania zasobami. Postępując zgodnie z tym przewodnikiem krok po kroku, nauczyłeś się manipulować danymi okresowymi, aby spełnić specyficzne potrzeby Twoich projektów.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Tasks dla .NET z innymi narzędziami do zarządzania projektami?
Aspose.Tasks jest przeznaczony przede wszystkim do programowania .NET. Jednak jego funkcjonalności mogą uzupełniać różne narzędzia do zarządzania projektami.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla .NET?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Tasks dla .NET?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności.
### Co to jest licencja tymczasowa i jak mogę ją uzyskać?
 Dowiedz się o licencjach tymczasowych[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć dokumentację Aspose.Tasks dla .NET?
 Zapoznaj się z całością[dokumentacja](https://reference.aspose.com/tasks/net/) aby uzyskać szczegółowe informacje.