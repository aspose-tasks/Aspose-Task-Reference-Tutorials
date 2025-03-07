---
title: Skonfiguruj opcje MS Project XLSX w Aspose.Tasks dla .NET
linktitle: Konfigurowanie opcji XLSX w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak skonfigurować opcje MS Project XLSX w Aspose.Tasks dla .NET. Dostosuj kolumny, kodowanie i wiele więcej bez wysiłku.
weight: 11
url: /pl/net/file-format-options/configuring-xlsx-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skonfiguruj opcje MS Project XLSX w Aspose.Tasks dla .NET

## Wstęp
Microsoft Project (MS Project) to potężne narzędzie do zarządzania projektami, a Aspose.Tasks dla .NET zapewnia bezproblemową integrację do programowej pracy z plikami MS Project. W tym samouczku omówimy proces konfigurowania opcji MS Project XLSX przy użyciu Aspose.Tasks dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
### 1. Zainstalowano Aspose.Tasks dla .NET
 Upewnij się, że w środowisku programistycznym zainstalowano Aspose.Tasks for .NET. Jeśli nie, możesz pobrać go ze strony[Strona pobierania Aspose.Tasks dla platformy .NET](https://releases.aspose.com/tasks/net/).
### 2. Podstawowa znajomość C# i .NET Framework
Aby skorzystać z tego samouczka, wymagana jest znajomość języka programowania C# i platformy .NET.
### 3. Plik projektu Microsoft
Przygotuj plik Microsoft Project (MPP), który chcesz skonfigurować i zapisać jako plik XLSX.

## Importowanie przestrzeni nazw
Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw:
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## Krok 1: Załaduj projekt
```csharp
var project = new Project("YourProjectFile.mpp");
```
Załaduj plik Microsoft Project, który chcesz skonfigurować.
## Krok 2: Zdefiniuj XlsxOptions
```csharp
var options = new XlsxOptions();
```
 Utwórz instancję`XlsxOptions` aby skonfigurować ustawienia zapisywania w formacie XLSX.
## Krok 3: Dodaj kolumny wykresu Gantta
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
Dodaj żądane kolumny Wykresu Gantta do opcji.
## Krok 4: Dodaj kolumny widoku zasobów
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
Uwzględnij żądane kolumny widoku zasobów w opcjach.
## Krok 5: Dodaj kolumny widoku zadania
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
Dodaj żądane kolumny do widoku przypisania w opcjach.
## Krok 6: Ustaw kodowanie
```csharp
options.Encoding = Encoding.Unicode;
```
Ustaw kodowanie pliku wyjściowego.
## Krok 7: Zapisz projekt jako XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
Zapisz projekt ze skonfigurowanymi opcjami jako plik XLSX.

## Wniosek
tym samouczku nauczyliśmy się konfigurować opcje MS Project XLSX przy użyciu Aspose.Tasks dla .NET. Wykonując poniższe kroki, możesz dostosować format wyjściowy do swoich wymagań, zwiększając elastyczność i użyteczność przepływu pracy związanego z zarządzaniem projektami.
## Często zadawane pytania

### P: Czy mogę oddzielnie skonfigurować różne kolumny dla Wykresu Gantta, Widoku Zasobów i Widoku Przydziału?

O: Tak, możesz dostosować kolumny niezależnie dla każdego widoku za pomocą Aspose.Tasks dla .NET.

### P: Czy przed zakupem Aspose.Tasks dla .NET dostępna jest wersja próbna?

 O: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Strona z wydaniami Aspose.Tasks dla platformy .NET](https://releases.aspose.com/).

### P: Jak mogę uzyskać pomoc, jeśli podczas wdrażania napotkam jakiekolwiek problemy lub będę mieć pytania?

 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) o pomoc od społeczności i zespołu wsparcia Aspose.

### P: Czy mogę generować pliki XLSX za pomocą Aspose.Tasks dla .NET na platformach innych niż Windows?

Odp.: Aspose.Tasks dla .NET jest przeznaczony głównie dla platform Windows, ale możesz zbadać opcje zgodności z innymi platformami.

### P: Czy są dostępne opcje licencji tymczasowych do celów testowych?

 Odpowiedź: Tak, możesz uzyskać tymczasową licencję od[Strona licencji tymczasowej Aspose.Tasks](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
