---
title: Obsługa linii postępu projektu MS za pomocą Aspose.Tasks
linktitle: Obsługa linii postępu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak manipulować liniami postępu w plikach MS Project przy użyciu Aspose.Tasks dla .NET, usprawniając wizualizację projektu i zarządzanie nim.
type: docs
weight: 15
url: /pl/net/project-management-integration/progress-lines/
---
## Wstęp
Microsoft Project (MS Project) to potężne narzędzie do zarządzania projektami, umożliwiające użytkownikom śledzenie różnych aspektów ich projektów. Jedną z kluczowych cech MS Project jest możliwość wizualizacji linii postępu, co pomaga interesariuszom zrozumieć status i trajektorię projektu. W tym samouczku omówimy, jak obsługiwać linie postępu w programie MS Project przy użyciu biblioteki Aspose.Tasks dla platformy .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Visual Studio: Zainstaluj Visual Studio lub inne preferowane środowisko programistyczne .NET.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importowanie przestrzeni nazw
Na początek zaimportujmy niezbędne przestrzenie nazw:
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
Teraz rozłóżmy każdy krok w obsłudze linii postępu:
## Krok 1: Załaduj plik projektu
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
 Tutaj ładujemy plik MS Project`Project2.mpp` i ustaw datę statusu.
## Krok 2: Zdefiniuj widok wykresu Gantta
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Rzuciliśmy widok projektu na widok wykresu Gantta w celu dalszej manipulacji.
## Krok 3: Zdefiniuj linie postępu
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
Inicjujemy linie postępu dla widoku wykresu Gantta.
## Krok 4: Skonfiguruj ustawienia linii postępu
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
Tutaj ustawiamy różne właściwości linii postępu, takie jak kolor linii, wzór, czcionka itp.
## Krok 5: Sprawdź konfigurację linii postępu
```csharp
// Wyjściowe ustawienia linii postępu
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
// Wyprowadź inne ustawienia...
```
Wysyłamy skonfigurowane ustawienia linii postępu w celu weryfikacji.
## Krok 6: Zapisz plik projektu
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
Na koniec zapisujemy zmodyfikowany plik projektu z liniami postępu.

## Wniosek
W tym samouczku nauczyliśmy się obsługiwać wiersze postępu MS Project za pomocą Aspose.Tasks dla .NET. Wykonując te kroki, możesz skutecznie programowo dostosowywać i wizualizować linie postępu w plikach MS Project.
## Często zadawane pytania
### P: Czy mogę bardziej dostosować wygląd linii postępu?
Odp.: Tak, możesz dostosować różne właściwości, takie jak kolor linii, wzór i czcionka, do własnych wymagań.
### P: Czy Aspose.Tasks obsługuje inne funkcje zarządzania projektami?
Odp.: Tak, Aspose.Tasks zapewnia szerokie wsparcie w manipulowaniu różnymi aspektami plików MS Project, w tym zadaniami, zasobami i kalendarzami.
### P: Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami .NET?
O: Oczywiście, Aspose.Tasks zaprojektowano tak, aby bezproblemowo integrował się z innymi bibliotekami .NET, co pozwala na dalsze ulepszanie aplikacji do zarządzania projektami.
### P: Czy istnieje forum społecznościowe dla wsparcia Aspose.Tasks?
 Odp.: Tak, możesz znaleźć pomocne zasoby i poprosić o pomoc na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy Aspose.Tasks oferuje licencje tymczasowe do celów ewaluacyjnych?
 Odpowiedź: Tak, możesz uzyskać tymczasową licencję do oceny od[Tutaj](https://purchase.aspose.com/temporary-license/).