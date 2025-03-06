---
title: Opanowywanie danych projektu za pomocą Aspose.Tasks
linktitle: Praca z danymi projektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak manipulować danymi programu Microsoft Project za pomocą Aspose.Tasks w .NET. Z łatwością twórz zadania, dodawaj zasoby i zapisuj projekty.
type: docs
weight: 16
url: /pl/net/project-management-integration/project-data/
---
## Wstęp
tym samouczku omówimy, jak pracować z danymi Microsoft Project przy użyciu biblioteki Aspose.Tasks dla .NET. Aspose.Tasks zapewnia zaawansowane funkcje do manipulowania plikami projektów, w tym tworzenia zadań, dodawania zasobów, ustawiania właściwości i zapisywania projektów w różnych formatach.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1.  Instalacja biblioteki Aspose.Tasks: Pobierz i zainstaluj bibliotekę Aspose.Tasks z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko programistyczne: Upewnij się, że masz skonfigurowane środowisko programistyczne .NET.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw
Przed rozpoczęciem pracy z Aspose.Tasks zaimportuj niezbędne przestrzenie nazw do swojego projektu:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Zainicjuj obiekt projektu
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project();
```
 Ta linia inicjuje nową instancję klasy`Project` class, która reprezentuje plik Microsoft Project.
## Krok 2: Ustaw właściwości projektu
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
Linie te pokazują, jak ustawić właściwości projektu, takie jak format pracy i tryb tworzenia zadania.
## Krok 3: Dodawanie zadań
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
W tym miejscu do głównego zadania projektu dodawane jest nowe zadanie o nazwie „Zadanie 1”.
## Krok 4: Ustawianie właściwości zadania
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Linie te określają datę rozpoczęcia, czas trwania i datę zakończenia „Zadania 1”.
## Krok 5: Dodawanie zasobów
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
W tej części pokazano, jak dodać zasób pracy do projektu.
## Krok 6: Przydzielanie zasobów do zadań
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
Linie te pokazują, jak przypisać wcześniej dodany zasób pracy do „Zadania 1” z określonymi datami rozpoczęcia, pracy i zakończenia.
## Krok 7: Zapisywanie projektu
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
Na koniec projekt jest zapisywany w formacie pliku XML programu Microsoft Project.

## Wniosek
W tym samouczku nauczyliśmy się, jak pracować z danymi Microsoft Project przy użyciu biblioteki Aspose.Tasks w .NET. Postępując zgodnie z przewodnikiem krok po kroku, możesz manipulować plikami projektu, dodawać zadania, zasoby, przypisywać zasoby do zadań i zapisywać projekty w różnych formatach.
## Często zadawane pytania
### P: Czy Aspose.Tasks obsługuje złożone struktury projektu?
O: Tak, Aspose.Tasks zapewnia kompleksową obsługę złożonych struktur projektów, umożliwiając efektywne zarządzanie zadaniami, zasobami i zadaniami.
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami Microsoft Project?
Odp.: Aspose.Tasks obsługuje szeroką gamę wersji Microsoft Project, zapewniając kompatybilność w różnych środowiskach.
### P: Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami .NET?
O: Oczywiście, Aspose.Tasks bezproblemowo integruje się z innymi bibliotekami .NET, zapewniając elastyczność w projektach programistycznych.
### P: Czy Aspose.Tasks oferuje wsparcie dla algorytmów planowania projektów?
O: Tak, Aspose.Tasks zawiera zaawansowane algorytmy planowania, które pomogą Ci zoptymalizować harmonogram projektów i wykorzystanie zasobów.
### P: Czy istnieje forum społecznościowe dla użytkowników Aspose.Tasks?
 O: Tak, możesz znaleźć pomocne zasoby i nawiązać kontakt z innymi użytkownikami Aspose.Tasks na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).