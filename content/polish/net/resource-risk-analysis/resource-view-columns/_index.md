---
title: Dostosuj kolumny widoku zasobów projektu MS w Aspose.Tasks
linktitle: Dostosowywanie kolumn widoku zasobów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie dostosowywać kolumny widoku zasobów MS Project za pomocą Aspose.Tasks dla .NET. Twórz dostosowane widoki, aby lepiej zarządzać projektami.
type: docs
weight: 17
url: /pl/net/resource-risk-analysis/resource-view-columns/
---
## Wstęp
Aspose.Tasks dla .NET to potężny interfejs API, który umożliwia programistom programową pracę z plikami Microsoft Project. Jednym z typowych zadań w zarządzaniu projektami jest dostosowywanie widoków w celu wyświetlania określonych informacji. W tym samouczku przyjrzymy się, jak dostosować kolumny widoku zasobów MS Project za pomocą Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Aspose.Tasks dla biblioteki .NET: Możesz ją pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Plik Microsoft Project: Przygotuj przykładowy plik MS Project do przetestowania.
3. Środowisko programistyczne: Środowisko programistyczne skonfigurowane w oparciu o platformę .NET.
## Importuj przestrzenie nazw
Najpierw zaimportujmy niezbędne przestrzenie nazw do naszego projektu:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## Krok 1: Załaduj plik projektu
Załaduj plik MS Project za pomocą Aspose.Tasks API:
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## Krok 2: Uzyskaj zasoby i zdefiniuj opcje
Następnie pobierz zasób, którego kolumny widoku chcesz dostosować i zdefiniuj opcje zapisywania pliku PDF:
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## Krok 3: Zdefiniuj kolumny niestandardowe
Teraz zdefiniuj niestandardowe kolumny dla widoku zasobów. Możesz określić różne pola, a nawet używać delegatów do niestandardowych obliczeń:
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## Krok 4: Iteruj po kolumnach
Iteruj po zdefiniowanych kolumnach i wyświetl ich właściwości:
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## Krok 5: Zapisz dostosowany widok
Na koniec ustaw widok niestandardowy i zapisz go jako plik PDF:
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
Wykonując poniższe kroki, możesz efektywnie dostosować kolumny widoku zasobów MS Project przy użyciu Aspose.Tasks dla .NET.
## Wniosek
Dostosowanie kolumn widoku zasobów MS Project jest niezbędne do wyświetlania odpowiednich informacji dostosowanych do potrzeb Twojego projektu. Dzięki Aspose.Tasks dla .NET zadanie to staje się proste i wydajne, umożliwiając łatwe tworzenie niestandardowych widoków.
## Często zadawane pytania
### Czy mogę dostosować widoki dla innych elementów oprócz zasobów?
Tak, Aspose.Tasks umożliwia również dostosowywanie zadań, przydziałów i innych elementów projektu.
### Czy Aspose.Tasks obsługuje zapisywanie widoków w formatach innych niż PDF?
Tak, możesz zapisywać widoki w różnych formatach, takich jak XLSX, HTML i obrazy.
### Czy można zastosować formatowanie do widoku niestandardowego?
Oczywiście, Aspose.Tasks zapewnia szerokie opcje formatowania, aby poprawić wygląd niestandardowych widoków.
### Czy mogę dynamicznie aktualizować widok niestandardowy w oparciu o zmieniające się dane projektu?
Tak, możesz aktualizować i ponownie generować widok niestandardowy za każdym razem, gdy zmienią się podstawowe dane projektu.
### Czy Aspose.Tasks obsługuje rozwój międzyplatformowy?
Aspose.Tasks dla .NET jest przeznaczony głównie dla platform .NET, ale dostępne są również wersje dla Java i innych platform.