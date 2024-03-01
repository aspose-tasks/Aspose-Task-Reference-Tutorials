---
title: Opanowanie widoków wykresu Gantta w Aspose.Tasks
linktitle: Widoki wykresu Gantta w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak dostosować widoki wykresów Gantta w plikach Microsoft Project przy użyciu Aspose.Tasks dla .NET. Przewodnik krok po kroku dotyczący skutecznego zarządzania projektami.
type: docs
weight: 22
url: /pl/net/tasks-project-management/gantt-chart-views/
---
## Wstęp
Wykresy Gantta to potężne narzędzia wykorzystywane w zarządzaniu projektami do wizualizacji zadań, osi czasu i zależności. Aspose.Tasks dla .NET zapewnia solidne możliwości pracy z widokami wykresów Gantta w plikach Microsoft Project. W tym samouczku odkryjemy, jak wykorzystać Aspose.Tasks do manipulowania widokami wykresów Gantta, dostosowywania ich wyglądu i zapisywania ich jako plików PDF.
## Warunki wstępne
Przed kontynuowaniem upewnij się, że spełnione są następujące wymagania wstępne:
### 1. Instalacja Aspose.Tasks dla .NET
 Upewnij się, że zainstalowałeś Aspose.Tasks dla .NET. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/tasks/net/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji[Tutaj](https://reference.aspose.com/tasks/net/).
### 2. Plik projektu Microsoft
Przygotuj plik Microsoft Project (`Project2.mpp`), którego będziesz używać do pracy z widokami wykresów Gantta.
### 3. Podstawowa znajomość C# i .NET Framework
tym samouczku założono, że masz podstawową wiedzę na temat języka programowania C# i platformy .NET.
## Importuj przestrzenie nazw
Zanim zaczniesz pracować z widokami wykresów Gantta w Aspose.Tasks, musisz zaimportować niezbędne przestrzenie nazw do swojego kodu C#. Oto jak możesz to zrobić:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

Podzielmy podany przykładowy kod na wiele kroków i szczegółowo wyjaśnijmy każdy krok:
## Krok 1: Załaduj plik projektu
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
Ten krok polega na załadowaniu pliku Microsoft Project (`Project2.mpp` ) do instancji`Project` klasa.
## Krok 2: Ustaw datę statusu
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Tutaj ustawiamy datę statusu projektu na datę jego rozpoczęcia.
## Krok 3: Uzyskaj dostęp do widoku wykresu Gantta
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
Dostęp do widoku wykresu Gantta uzyskujemy z projektu. Aspose.Tasks umożliwia dostęp do widoków takich jak wykres Gantta, diagram sieciowy i wykorzystanie zadań.
## Krok 4: Dostosuj widok wykresu Gantta
Teraz dostosujmy różne aspekty widoku wykresu Gantta:
### Ustaw zaokrąglenie paska
```csharp
view.BarRounding = false;
```
Określa, czy słupki na wykresie Gantta będą zaokrąglane do najbliższego dnia.
### Ustaw rozmiar paska
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
Określa to wysokość słupków Gantta na wykresie.
### Ukryj paski rozwijane
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
Określa, czy paski zestawień będą ukryte podczas rozwijania zadań sumarycznych.
### Ustaw kolor czasu wolnego od pracy
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
Określa kolor czasu wolnego na wykresie Gantta.
### Zwijane batoniki Gantta
```csharp
view.RollUpGanttBars = true;
```
Określa, czy słupki na wykresie Gantta muszą być zwinięte.
### Pokaż podziały słupków
```csharp
view.ShowBarSplits = true;
```
Określa, czy na wykresie Gantta muszą być pokazywane podziały zadań.
### Pokaż rysunki
```csharp
view.ShowDrawings = true;
```
Określa, czy muszą być wyświetlane rysunki na wykresie Gantta.
### Procent rozmiaru skali czasu
```csharp
view.TimescaleSizePercentage = 10;
```
Ustawia wartość procentową w celu dostosowania odstępów między jednostkami na warstwie skali czasu.
## Krok 5: Zapisz widok wykresu Gantta jako plik PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
Na koniec zapisujemy dostosowany widok wykresu Gantta jako plik PDF.
## Wniosek
W tym samouczku nauczyliśmy się, jak pracować z widokami wykresów Gantta w Aspose.Tasks dla .NET. Postępując zgodnie z podanymi krokami, możesz efektywnie manipulować wykresami Gantta i dostosowywać je zgodnie z wymaganiami projektu.
## Często zadawane pytania
### P: Czy mogę bardziej dostosować wygląd pasków wykresu Gantta?
O: Tak, Aspose.Tasks zapewnia rozbudowane opcje dostosowywania wyglądu słupków wykresu Gantta, w tym kolorów, kształtów i rozmiarów.
### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
Odp.: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### P: Czy mogę eksportować widoki wykresów Gantta do formatów innych niż PDF?
O: Oczywiście, Aspose.Tasks obsługuje eksportowanie widoków wykresów Gantta do wielu formatów, w tym PNG, JPEG i XPS.
### P: Czy Aspose.Tasks oferuje obsługę złożonych algorytmów planowania projektów?
Odp.: Tak, Aspose.Tasks zapewnia zaawansowane algorytmy planowania do skutecznej obsługi złożonych harmonogramów projektów.
### P: Czy istnieje forum społeczności, na którym mogę szukać pomocy lub podzielić się swoimi doświadczeniami z Aspose.Tasks?
 Odpowiedź: Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) aby nawiązać kontakt z innymi użytkownikami, zadawać pytania i znajdować rozwiązania na swoje pytania.