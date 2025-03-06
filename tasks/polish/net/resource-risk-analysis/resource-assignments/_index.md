---
title: Obsługa przypisań zasobów projektu MS w Aspose.Tasks
linktitle: Obsługa przypisań zasobów w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie obsługiwać przydziały zasobów MS Project za pomocą Aspose.Tasks dla .NET. Ten kompleksowy podręcznik zawiera szczegółowe wskazówki dla programistów.
weight: 11
url: /pl/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa przypisań zasobów projektu MS w Aspose.Tasks

## Wstęp
W tym samouczku omówimy, jak efektywnie obsługiwać przydziały zasobów programu Microsoft Project za pomocą Aspose.Tasks dla .NET. Aspose.Tasks to potężny interfejs API, który umożliwia programistom programowe manipulowanie plikami Microsoft Project. Wykonując poniższe kroki, dowiesz się, jak efektywnie zarządzać przydziałami zasobów w aplikacjach .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:

## Importuj przestrzenie nazw
Po pierwsze, musisz zaimportować niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Tasks w swoim projekcie .NET. To zawiera:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
Podzielmy teraz podany przykład na wiele kroków, aby uzyskać pełne zrozumienie sposobu obsługi przydziałów zasobów MS Project przy użyciu Aspose.Tasks.
## Krok 1: Skonfiguruj ustawienia projektu i kalendarza
Aby rozpocząć, utwórz nową instancję projektu i skonfiguruj ustawienia kalendarza projektu:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Krok 2: Dodaj zadanie do projektu
Następnie dodaj nowe zadanie do zadania głównego projektu:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Krok 3: Utwórz przypisanie zasobów i wygeneruj dane okresowe
Teraz utwórz nowe przypisanie zasobów dla zadania i wygeneruj dane okresowe:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Krok 4: Podziel zadanie
Podziel zadanie na wiele części, podając daty rozpoczęcia i zakończenia:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Krok 5: Ustaw kontur pracy
Ustaw typ konturu roboczego dla przyporządkowania:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Krok 6: Zapisz projekt
Na koniec zapisz plik projektu z wprowadzonymi zmianami:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Wniosek
Podsumowując, obsługa przypisań zasobów Microsoft Project przy użyciu Aspose.Tasks dla .NET jest prostym procesem. Wykonując kroki opisane w tym samouczku, możesz efektywnie zarządzać przypisaniami zasobów w aplikacjach .NET.
## Często zadawane pytania
### Czy Aspose.Tasks może obsługiwać złożone struktury projektu?
Tak, Aspose.Tasks zapewnia kompleksowe funkcjonalności umożliwiające efektywną obsługę złożonych struktur projektowych.
### Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?
Tak, Aspose.Tasks obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.
### Czy mogę dostosować przydział zasobów w oparciu o określone wymagania?
Absolutnie Aspose.Tasks oferuje szerokie opcje dostosowywania przydziału zasobów w celu spełnienia konkretnych potrzeb projektu.
### Czy Aspose.Tasks obsługuje eksport danych projektu do innych formatów?
Tak, Aspose.Tasks umożliwia eksport danych projektu do różnych formatów, takich jak między innymi XML, PDF i HTML.
### Czy dostępna jest pomoc techniczna dla użytkowników Aspose.Tasks?
Tak, Aspose zapewnia dedykowane wsparcie techniczne za pośrednictwem swojego forum i innych kanałów, aby pomóc użytkownikom w przypadku jakichkolwiek pytań lub problemów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
