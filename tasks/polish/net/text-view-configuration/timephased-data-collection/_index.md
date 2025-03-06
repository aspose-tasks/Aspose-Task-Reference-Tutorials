---
title: Opanowanie okresowego gromadzenia danych w Aspose.Tasks
linktitle: Zbieranie danych okresowych w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Przeglądaj okresowe gromadzenie danych w Aspose.Tasks dla .NET. Przewodnik krok po kroku, często zadawane pytania i nie tylko. Zwiększ swoje możliwości zarządzania projektami już dziś!
type: docs
weight: 15
url: /pl/net/text-view-configuration/timephased-data-collection/
---
## Wstęp
Czy chcesz wykorzystać moc danych okresowych w aplikacjach .NET przy użyciu Aspose.Tasks? Nie szukaj dalej! Ten kompleksowy przewodnik przeprowadzi Cię przez proces gromadzenia danych okresowych za pomocą Aspose.Tasks dla .NET, zapewniając maksymalne wykorzystanie tej potężnej biblioteki.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Aspose.Tasks dla biblioteki .NET: Pobierz i zainstaluj bibliotekę z[Dokumentacja Aspose.Tasks .NET](https://reference.aspose.com/tasks/net/).
2. Środowisko programistyczne .NET: Upewnij się, że masz skonfigurowane działające środowisko programistyczne .NET.
3. Twój katalog dokumentów: Zastąp symbol zastępczy „Twój katalog dokumentów” we fragmentach kodu ścieżką do katalogu dokumentów.
## Importuj przestrzenie nazw
W projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby wykorzystać funkcjonalności Aspose.Tasks:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Utwórz projekt i zasoby
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Dodaj zadania do projektu
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Ustaw właściwości zadania...
var task2 = project.RootTask.Children.Add("Task 2");
// Ustaw właściwości zadania 2...
```
## 3. Przypisz zasoby do zadań
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Ustaw właściwości przypisania...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//Ustaw właściwości przypisania 2...
```
## 4. Pracuj z danymi okresowymi
```csharp
// Ustaw konturowy kontur pracy
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Sprawdź, czy gromadzenie danych okresowych jest tylko do odczytu
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Wyczyść wygenerowane dane okresowe
assignment.TimephasedData.Clear();
// Twórz i dodawaj dane okresowe
var td = new TimephasedData
{
    // Ustaw właściwości danych okresowych...
};
assignment.TimephasedData.Add(td);
// Dodaj listę danych okresowych
var list = new List<TimephasedData>();
// Dodaj do listy więcej elementów danych okresowych...
assignment.TimephasedData.AddRange(list);
// Filtruj dane okresowe według typu i zakresu dat
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Drukuj filtrowane dane okresowe...
```
## 5. Manipuluj danymi okresowymi
```csharp
// Dodaj nieprawidłowy element danych okresowych, a następnie go usuń
var td4 = new TimephasedData
{
    // Ustaw nieprawidłowe właściwości danych okresowych...
};
assignment.TimephasedData.Add(td4);
// Usuń nieprawidłowy element danych okresowych
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iteruj po wszystkich elementach okresowych
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Drukuj szczegóły elementu okresowego...
}
```
## 6. Skopiuj dane okresowe do innego zadania
```csharp
// Skopiuj dane okresowe do innego zadania
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Przekonwertuj kolekcję na zwykłą listę
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Usuń elementy danych okresowych jeden po drugim
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Wniosek
Podsumowując, ten samouczek zawiera szczegółowy opis gromadzenia danych okresowych przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz bezproblemowo zintegrować tę funkcjonalność ze swoimi projektami, umożliwiając efektywne śledzenie czasu i zarządzanie zasobami.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Tasks dla .NET z innymi narzędziami do zarządzania projektami?
Tak, Aspose.Tasks dla .NET jest zaprojektowany do współpracy z popularnymi narzędziami do zarządzania projektami i obsługuje różne formaty plików.
### Czy istnieje ograniczenie liczby zasobów i zadań, którymi mogę zarządzać za pomocą Aspose.Tasks?
Aspose.Tasks obsługuje projekty o różnej wielkości i nie ma ścisłego ograniczenia liczby zasobów i zadań.
### Jak mogę uzyskać pomoc w przypadku jakichkolwiek problemów lub zapytań związanych z Aspose.Tasks dla .NET?
 Aby uzyskać pomoc, odwiedź stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) aby nawiązać kontakt ze społecznością i uzyskać pomoc.
### Czy mogę wypróbować Aspose.Tasks dla .NET przed zakupem?
 Tak, możesz poznać funkcje Aspose.Tasks dla .NET, uzyskując dostęp do[bezpłatna wersja próbna](https://releases.aspose.com/).
### Gdzie mogę kupić licencję na Aspose.Tasks dla .NET?
Możesz kupić licencję na Aspose.Tasks dla .NET[Tutaj](https://purchase.aspose.com/buy).