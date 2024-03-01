---
title: Zapisz pliki MS Project jako szablony za pomocą Aspose.Tasks
linktitle: Zapisz opcje szablonu dla Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak zapisywać pliki Microsoft Project jako szablony przy użyciu Aspose.Tasks dla .NET. Dostosuj ustawienia szablonu, aby usprawnić zarządzanie projektami.
type: docs
weight: 18
url: /pl/net/saving-options/save-template-options/
---
## Wstęp
tym samouczku omówimy proces zapisywania szablonu przy użyciu Aspose.Tasks dla .NET. Szablony są przydatne do standaryzacji struktur projektu i ustawień do wykorzystania w przyszłości. Pokażemy, jak zapisać projekt jako szablon, dostosowując po drodze jego właściwości.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Biblioteka Aspose.Tasks dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Tasks dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Znajomość programowania w języku C#: Do zrozumienia i wdrożenia dostarczonych fragmentów kodu wymagana jest podstawowa znajomość programowania w języku C#.
3. Plik programu Microsoft Project: Przygotuj plik programu Microsoft Project (w formacie MPP), który chcesz zapisać jako szablon.

## Importuj przestrzenie nazw
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Krok 1: Załaduj projekt
Najpierw musimy załadować plik Microsoft Project (.mpp), który chcemy zapisać jako szablon.
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Krok 2: Uzyskaj informacje o pliku projektu
Pobierz informacje o załadowanym pliku projektu, takie jak jego format.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Krok 3: Skonfiguruj opcje szablonu zapisu
Utwórz opcje zapisu szablonu i skonfiguruj jego właściwości zgodnie ze swoimi wymaganiami. Opcje te pozwalają dostosować, jakie dane mają zostać usunięte z szablonu.
```csharp
var options = new SaveTemplateOptions
{
	// Usuń wszystkie koszty stałe z szablonu projektu
	RemoveFixedCosts = true,
	// Usuń wszystkie rzeczywiste wartości z szablonu projektu
	RemoveActualValues = true,
	// Usuń stawki za zasoby z szablonu projektu
	RemoveResourceRates = true,
	// Usuń wszystkie wartości bazowe z szablonu projektu
	RemoveBaselineValues = true
};
```
## Krok 4: Zapisz projekt jako szablon
Zapisz projekt jako szablon z określonymi opcjami.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Krok 5: Uzyskaj informacje o pliku szablonu
Pobierz informacje o zapisanym pliku szablonu, takie jak jego format.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Gratulacje! Pomyślnie zapisałeś szablon przy użyciu Aspose.Tasks dla .NET, dostosowując jego właściwości w razie potrzeby.

## Wniosek
W tym samouczku omówiliśmy, jak zapisać plik Microsoft Project jako szablon przy użyciu Aspose.Tasks dla .NET. Szablony są cenne przy standaryzacji struktur i ustawień projektu, usprawniając przyszłe tworzenie projektów.
## Często zadawane pytania
### P: Czy mogę dostosować, które dane mają zostać usunięte z szablonu?
O: Tak, możesz skonfigurować Opcje zapisu szablonu, aby usunąć określone dane, takie jak koszty stałe, wartości rzeczywiste, stawki za zasoby i wartości bazowe.
### P: Czy Aspose.Tasks for .NET jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks dla .NET zapewnia szeroką kompatybilność z różnymi wersjami Microsoft Project, zapewniając bezproblemową integrację i funkcjonalność.
### P: Czy mogę zastosować szablony do istniejących projektów?
O: Tak, możesz zastosować szablony do istniejących projektów, ładując plik szablonu i łącząc go z bieżącym projektem, jeśli zajdzie taka potrzeba.
### P: Czy Aspose.Tasks dla .NET obsługuje programowanie międzyplatformowe?
Odp.: Aspose.Tasks dla .NET jest przeznaczony przede wszystkim dla aplikacji .NET Framework działających na platformach Windows.
### P: Czy dostępna jest pomoc techniczna dla Aspose.Tasks dla .NET?
 Odp.: Tak, możesz zwrócić się o pomoc techniczną i wskazówki do społeczności Aspose.Tasks[fora](https://forum.aspose.com/c/tasks/15)lub skontaktuj się bezpośrednio z ich zespołem wsparcia.