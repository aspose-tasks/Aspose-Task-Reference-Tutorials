---
title: Konfigurowanie opcji wyświetlania MS Project w Aspose.Tasks
linktitle: Konfigurowanie opcji wyświetlania projektu w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak programowo skonfigurować opcje wyświetlania MS Project przy użyciu Aspose.Tasks dla .NET. Dostosuj wygląd swojego projektu bez wysiłku.
weight: 17
url: /pl/net/project-management-integration/project-display-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurowanie opcji wyświetlania MS Project w Aspose.Tasks

## Wstęp
Microsoft Project oferuje mnóstwo opcji wyświetlania, które pozwalają dostosować wygląd projektu. Aspose.Tasks dla .NET zapewnia solidną platformę do programowego manipulowania tymi opcjami. W tym samouczku przyjrzymy się, jak skonfigurować opcje wyświetlania MS Project za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim zagłębisz się w samouczek, upewnij się, że posiadasz następujące elementy:
1.  Aspose.Tasks dla .NET: Pobierz i zainstaluj bibliotekę z[Tutaj](https://releases.aspose.com/tasks/net/).
2. Plik Microsoft Project: Przygotuj prawidłowy plik MS Project (.mpp), aby zastosować opcje wyświetlania.
3. Podstawowa znajomość języka C#: Wymagana jest znajomość języka programowania C#.

## Importowanie przestrzeni nazw
Po pierwsze, pamiętaj o zaimportowaniu niezbędnych przestrzeni nazw do kodu C#:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## Krok 1: Załaduj plik projektu
 Załaduj plik MS Project za pomocą`Project` klasa dostarczona przez Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Krok 2: Skonfiguruj opcje wyświetlania
Teraz skonfigurujmy różne opcje wyświetlania dostępne w MS Project:
### Wyłącz ostrzeżenia dotyczące harmonogramu zadań
Aby wyłączyć ostrzeżenia dotyczące konfliktów planowania z ręcznie zaplanowanymi zadaniami (dostępne w programie Project 2010 i nowszych wersjach):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Dodaj spację przed etykietą
Ustaw, aby dodać spację przed wartością liczby i skrótem czasu:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Skonfiguruj wyświetlanie etykiet dla jednostek czasu
Dostosuj sposób wyświetlania różnych jednostek czasu:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Pokaż zadanie podsumowujące projekt
Wyświetl podsumowanie informacji o całym projekcie w jednym wierszu:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Włącz sugestie dotyczące harmonogramu zadań
Zezwalaj na wyświetlanie sugestii dotyczących konfliktów planowania z zadaniami zaplanowanymi ręcznie:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Podkreśl hiperłącza
Ustaw podkreślanie hiperłączy w projekcie:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Krok 3: Zapisz projekt
Na koniec zapisz projekt z zastosowanymi opcjami wyświetlania:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Wniosek
W tym samouczku nauczyliśmy się konfigurować opcje wyświetlania MS Project za pomocą Aspose.Tasks dla .NET. Dzięki tym funkcjom możesz efektywnie programowo dostosowywać wygląd plików projektu.
## Często zadawane pytania
### P: Czy mogę zastosować te opcje wyświetlania tylko do określonych zadań?
Odp.: Tak, możesz selektywnie zastosować opcje wyświetlania do poszczególnych zadań za pomocą interfejsu API Aspose.Tasks.
### P: Czy te opcje wyświetlania wpływają na podstawowe dane projektu?
O: Nie, te opcje modyfikują jedynie wizualną reprezentację projektu i nie zmieniają podstawowych danych.
### P: Czy te opcje wyświetlania są kompatybilne ze wszystkimi wersjami Microsoft Project?
O: Nie, niektóre opcje mogą być specyficzne dla niektórych wersji MS Project. Szczegóły dotyczące kompatybilności można znaleźć w dokumentacji.
### P: Czy mogę przywrócić domyślne ustawienia opcji wyświetlania?
Odp.: Tak, możesz zresetować opcje wyświetlania do wartości domyślnych za pomocą interfejsu API Aspose.Tasks.
### P: Czy istnieją jakieś ograniczenia w programowym dostosowywaniu opcji wyświetlania?
O: Chociaż Aspose.Tasks zapewnia szerokie możliwości dostosowywania, niektóre opcje wyświetlania mogą nie być dostępne programowo ze względu na ograniczenia w formacie pliku MS Project.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
