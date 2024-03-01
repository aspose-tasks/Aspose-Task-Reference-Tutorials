---
title: Efektywnie zarządzaj filtrami projektów MS za pomocą Aspose.Tasks
linktitle: Zarządzanie kolekcją filtrów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać filtrowanymi kolekcjami MS Project za pomocą Aspose.Tasks dla .NET.
type: docs
weight: 17
url: /pl/net/tasks-project-management/filter-collection/
---
## Wstęp
W tym samouczku przyjrzymy się, jak efektywnie zarządzać kolekcjami filtrów MS Project za pomocą Aspose.Tasks dla .NET. Zarządzanie filtrami ma kluczowe znaczenie dla efektywnego organizowania i analizowania danych projektu. Aspose.Tasks zapewnia solidną funkcjonalność do płynnej obsługi filtrów zadań i zasobów.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Instalacja Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
2. Dostęp do środowiska programistycznego .NET: Upewnij się, że środowisko programistyczne .NET jest skonfigurowane do pracy z Aspose.Tasks.

## Importuj przestrzenie nazw
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Krok 1: Załaduj plik projektu
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## Krok 2: Iteruj po filtrach zadań
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## Krok 3: Iteruj po filtrach zasobów
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## Krok 4: Wyczyść i skopiuj filtry
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Wyczyść filtry innych projektów
otherProject.TaskFilters.Clear();
// Skopiuj filtry do innego projektu
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## Krok 5: Dodaj niestandardowy filtr zadań
```csharp
// Dodaj niestandardowy filtr zadań
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## Krok 6: Usuń wszystkie filtry
```csharp
// Usuń wszystkie filtry
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
Wykonując poniższe kroki, możesz efektywnie zarządzać filtrowanymi kolekcjami MS Project za pomocą Aspose.Tasks dla .NET.

## Wniosek
Efektywne zarządzanie filtrami w zbiorach MS Project ma kluczowe znaczenie dla organizowania i analizowania danych projektowych. Aspose.Tasks dla .NET zapewnia wszechstronną funkcjonalność do płynnej obsługi filtrów zadań i zasobów, umożliwiając programistom efektywne usprawnianie zadań związanych z zarządzaniem projektami.
## Często zadawane pytania
### P: Czy Aspose.Tasks obsługuje złożone struktury projektu?
Odp.: Aspose.Tasks oferuje solidne funkcje do obsługi różnych struktur projektów, w tym złożonych, zapewniając kompleksowe możliwości zarządzania projektami.
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?
O: Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików MS Project, zapewniając kompatybilność w różnych wersjach.
### P: Czy mogę dostosować filtry do konkretnych wymagań projektu?
Odp.: Absolutnie! Aspose.Tasks umożliwia programistom tworzenie niestandardowych filtrów dostosowanych do unikalnych potrzeb projektu, zwiększając elastyczność i wydajność.
### P: Czy Aspose.Tasks zapewnia dokumentację i zasoby wsparcia?
O: Tak, Aspose.Tasks oferuje obszerną dokumentację, samouczki i dedykowane forum wsparcia, które pomaga programistom na każdym etapie wdrażania projektu.
### P: Czy dostępna jest wersja próbna Aspose.Tasks?
Odp.: Tak, programiści mogą uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks, aby zapoznać się z jej funkcjami przed podjęciem decyzji o zakupie.