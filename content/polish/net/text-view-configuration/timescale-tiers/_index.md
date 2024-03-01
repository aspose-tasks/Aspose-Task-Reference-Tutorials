---
title: Konfigurowanie warstw skali czasowej wykresu Gantta w Aspose.Tasks
linktitle: Konfigurowanie warstw skali czasu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Przeglądaj Aspose.Tasks dla .NET, aby skonfigurować poziomy skali czasu w widoku Wykresu Gantta w celu precyzyjnej wizualizacji osi czasu projektu. #Aspose.Tasks #MS Project
type: docs
weight: 16
url: /pl/net/text-view-configuration/timescale-tiers/
---
## Wstęp
W dynamicznym krajobrazie zarządzania projektami skuteczna wizualizacja ma kluczowe znaczenie dla zrozumienia harmonogramów i terminów. Aspose.Tasks dla .NET zapewnia potężny zestaw narzędzi, a w tym samouczku przyjrzymy się, jak skonfigurować warstwy skali czasu w celu uzyskania optymalnej reprezentacji w widoku Wykres Gantta. Postępuj zgodnie z poniższymi instrukcjami krok po kroku, aby ulepszyć wizualizację projektu.
## Warunki wstępne
Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość C# i .NET.
-  Zainstalowana biblioteka Aspose.Tasks dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
- Środowisko programistyczne skonfigurowane do tworzenia aplikacji .NET.
## Importuj przestrzenie nazw
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Teraz przeanalizujmy każdy krok podanego przykładu.
## Krok 1: Zainicjuj projekt i dodaj łącza do zadań
```csharp
// Ścieżka do katalogu dokumentów.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
Tutaj tworzymy projekt i ustalamy powiązania zadań pomiędzy „Zadaniem 1” i „Zadaniem 2”.
## Krok 2: Skonfiguruj widok wykresu Gantta
```csharp
var view = (GanttChartView)project.DefaultView;
```
Uzyskaj dostęp do widoku Wykres Gantta w celu dostosowania.
## Krok 3: Dostosuj środkowy poziom skali czasu
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
Dostosuj środkowy poziom skali czasu, aby wyświetlać tygodnie z określonymi etykietami i wyrównaniem.
## Krok 4: Dodaj najwyższy poziom skali czasu
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
Dodaj górną warstwę skali czasu reprezentującą miesiące.
## Krok 5: Dostosuj daty środkowego poziomu
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
Spersonalizuj etykiety miesięcy, aby uzyskać lepszą wizualizację.
## Krok 6: Ustaw harmonogram projektu
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
Zdefiniuj skalę czasową projektu, aby kontrolować ogólną oś czasu.
## Krok 7: Zapisz projekt z niestandardową skalą czasu
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
Zapisz projekt ze zdefiniowanymi ustawieniami skali czasu.
## Wniosek
Podsumowując, skonfigurowanie poziomów skali czasu w Aspose.Tasks dla .NET pozwala na bardziej dostosowaną i atrakcyjną wizualnie reprezentację osi czasu projektu. Poniższe kroki umożliwiają utworzenie widoku wykresu Gantta, który dokładnie odpowiada Twoim potrzebom w zakresie zarządzania projektami.
## Często zadawane pytania
### Czy mogę używać Aspose.Tasks z innymi bibliotekami .NET?
Tak, Aspose.Tasks bezproblemowo integruje się z innymi bibliotekami .NET, oferując elastyczność w stosie programistycznym.
### Czy dostępna jest licencja tymczasowa do celów testowych?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) dla ewolucji.
### Czy istnieją dodatkowe opcje dostosowywania widoku Wykres Gantta?
Absolutnie Aspose.Tasks zapewnia szerokie opcje dostosowywania widoku Wykres Gantta, aby dopasować go do różnorodnych wymagań projektu.
### Czy mogę renderować skale czasu w różnych formatach?
Z pewnością możesz eksplorować różne formaty i style reprezentacji skali czasu, aby najlepiej dopasować je do kontekstu projektu.
### Czy istnieje forum społecznościowe dla wsparcia Aspose.Tasks?
 Tak, odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.