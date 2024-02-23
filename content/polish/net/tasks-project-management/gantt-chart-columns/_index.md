---
title: Dostosuj kolumny wykresu Gantta za pomocą Aspose.Tasks
linktitle: Kolumny wykresu Gantta w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak dostosować kolumny wykresu Gantta w Aspose.Tasks dla .NET, aby efektywnie wyświetlać informacje o konkretnych zadaniach.
type: docs
weight: 21
url: /pl/net/tasks-project-management/gantt-chart-columns/
---
## Wstęp
Wykresy Gantta są podstawowym narzędziem w zarządzaniu projektami, zapewniającym wizualną reprezentację zadań, osi czasu i zasobów. Aspose.Tasks dla .NET oferuje potężne możliwości manipulowania wykresami Gantta, w tym dostosowywanie kolumn w celu wyświetlania określonych informacji o zadaniu. W tym samouczku omówimy, jak pracować z kolumnami wykresu Gantta za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Instalacja: Aspose.Tasks for .NET zainstalowany w twoim systemie. Jeśli nie, pobierz i zainstaluj go z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne .NET: praktyczna znajomość języka C# i frameworku .NET.
3. Przykładowy plik projektu: Przygotuj przykładowy plik programu Microsoft Project (`.mpp`) przydatny do eksperymentowania. Jeśli go nie posiadasz, możesz stworzyć prosty projekt w MS Project i zapisać go.

## Importuj przestrzenie nazw
Najpierw musisz zaimportować niezbędne przestrzenie nazw do pracy z Aspose.Tasks dla .NET:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Załaduj plik projektu
 Załaduj plik projektu za pomocą`Project` klasa dostarczona przez Aspose.Tasks:
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Krok 2: Zdefiniuj kolumny wykresu Gantta
Zdefiniuj kolumny, które chcesz wyświetlić na wykresie Gantta. Możesz określić pola wbudowane lub utworzyć własne:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Krok 3: Iteruj po kolumnach
Iteruj po zdefiniowanych kolumnach, aby uzyskać dostęp do ich właściwości i wyświetlić informacje:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Krok 4: Zapisz wykres Gantta w formacie CSV
Zapisz wykres Gantta ze zdefiniowanymi kolumnami do pliku CSV:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Wykonując te kroki, możesz efektywnie pracować z kolumnami wykresu Gantta w Aspose.Tasks for .NET, umożliwiając dostosowywanie i wyświetlanie informacji o zadaniach zgodnie z potrzebami.

## Wniosek
Opanowanie manipulacji kolumnami wykresu Gantta w Aspose.Tasks dla .NET otwiera nieograniczone możliwości dostosowywania wizualizacji zarządzania projektami do konkretnych potrzeb. Wykonując kroki opisane w tym samouczku, możesz efektywnie zarządzać informacjami o zadaniach oraz poprawić przejrzystość i organizację projektu.
## Często zadawane pytania
### P: Czy mogę tworzyć niestandardowe kolumny w Aspose.Tasks dla .NET?
Odp.: Tak, możesz zdefiniować niestandardowe kolumny, aby wyświetlać określone atrybuty zadań zgodnie z wymaganiami projektu.
### P: Czy Aspose.Tasks dla .NET jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?
Odp.: Aspose.Tasks dla .NET obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność w różnych środowiskach projektowych.
### P: Jak mogę obsługiwać złożone struktury projektu za pomocą Aspose.Tasks dla .NET?
Odp.: Aspose.Tasks dla .NET zapewnia kompleksowe interfejsy API i funkcje do zarządzania złożonymi strukturami projektów, oferując elastyczność i skalowalność.
### P: Czy istnieją jakieś ograniczenia dotyczące liczby kolumn, które mogę dodać do wykresu Gantta?
Odp.: Aspose.Tasks dla .NET oferuje szerokie opcje dostosowywania, umożliwiając dodawanie znacznej liczby kolumn do wykresów Gantta bez ograniczeń.
### P: Gdzie mogę znaleźć dodatkowe wsparcie i zasoby dla Aspose.Tasks dla .NET?
Odp.: Możesz przeglądać dokumentację, fora społeczności i kanały wsparcia udostępniane przez Aspose.Tasks dla .NET, aby uzyskać dostęp do kompleksowych zasobów i pomocy.