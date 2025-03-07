---
title: Opanowanie opcji zapisu MS Project dla Aspose.Tasks
linktitle: Ogólne opcje zapisywania dla Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zapisywać pliki MS Project przy użyciu Aspose.Tasks dla .NET. Dostosuj opcje wyjściowe bez wysiłku do swoich projektów.
weight: 17
url: /pl/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie opcji zapisu MS Project dla Aspose.Tasks

## Wstęp
Aspose.Tasks dla .NET oferuje zaawansowane funkcje do programowego manipulowania plikami Microsoft Project. W tym samouczku zagłębimy się w zawiłości zapisywania plików MS Project przy użyciu różnych opcji udostępnianych przez Aspose.Tasks. W szczególności skupimy się na ogólnych opcjach zapisywania dostępnych dla Aspose.Tasks, umożliwiając dostosowanie wyników do konkretnych wymagań.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Instalacja Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[link do pobrania](https://releases.aspose.com/tasks/net/).
2. Podstawowa znajomość .NET Framework: Znajomość koncepcji programowania .NET jest korzystna.

## Importowanie przestrzeni nazw
Zanim zagłębisz się w kod, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Krok 1: Załaduj plik projektu
Najpierw musisz załadować plik MS Project za pomocą Aspose.Tasks:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Krok 2: Zdefiniuj opcje zapisywania
 Zdefiniuj opcje zapisu zgodnie ze swoimi wymaganiami. W tym przykładzie używamy`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Krok 3: Dostosuj kolumny widoku
Możesz dostosować kolumny widoku, takie jak wykres Gantta, widok zasobów i widok przypisań. Oto jak dodać kolumny do każdego z nich:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Krok 4: Zapisz projekt z opcjami
Na koniec zapisz projekt z określonymi opcjami:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Wniosek
Opanowanie ogólnych opcji zapisywania MS Project za pomocą Aspose.Tasks dla .NET umożliwia efektywne dostosowanie formatu wyjściowego do potrzeb projektu.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?
O: Tak, Aspose.Tasks obsługuje różne wersje plików MS Project, zapewniając kompatybilność w różnych środowiskach.
### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?
 Odp.: Tak, możesz eksplorować Aspose.Tasks w ramach bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć dokumentację dla Aspose.Tasks?
 Odp.: Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/tasks/net/), zapewniając kompleksowe wskazówki dotyczące korzystania z funkcji Aspose.Tasks.
### P: Jak mogę uzyskać tymczasowe licencje na Aspose.Tasks?
 Odpowiedź: Licencje tymczasowe są dostępne do celów próbnych[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę uzyskać pomoc dotyczącą zapytań związanych z Aspose.Tasks?
 O: Możesz dołączyć do forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15)aby uzyskać pomoc od ekspertów i innych programistów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
