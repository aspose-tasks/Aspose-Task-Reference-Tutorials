---
title: Opanowanie widoków użycia zadań w Aspose.Tasks dla .NET
linktitle: Konfigurowanie widoków wykorzystania zadań w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Poznaj Aspose.Tasks dla .NET i dowiedz się, jak skonfigurować widoki wykorzystania zadań. Dostosuj ustawienia skali czasu i ulepsz wizualizacje zarządzania projektami.
weight: 24
url: /pl/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie widoków użycia zadań w Aspose.Tasks dla .NET

## Wstęp
dziedzinie zarządzania projektami wizualizacja wykorzystania zadań ma kluczowe znaczenie dla skutecznego planowania i realizacji. Aspose.Tasks dla .NET zapewnia solidne rozwiązanie do renderowania widoków wykorzystania zadań, umożliwiając dostosowanie ustawień skali czasu i formatów prezentacji. W tym samouczku omówimy kroki konfigurowania widoków użycia zadań przy użyciu Aspose.Tasks.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Aspose.Tasks dla .NET: Upewnij się, że biblioteka Aspose.Tasks jest zintegrowana z projektem .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/net/).
2. Środowisko .NET: Skonfiguruj działające środowisko .NET na swoim komputerze.
## Importuj przestrzenie nazw
W projekcie .NET zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Tasks. Dodaj następujące linie do swojego kodu:
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Ustaw ścieżkę katalogu dokumentów
 Przed rozpoczęciem pracy z funkcjonalnościami Aspose.Tasks ustaw ścieżkę do katalogu dokumentów. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką.
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Załaduj projekt
 Zainicjuj Aspose.Tasks`Project` obiekt, ładując plik projektu (np. TaskUsageView.mpp).
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## Krok 3: Zdefiniuj Opcje zapisu
 Stwórz`SaveOptions`obiekt, aby określić opcje renderowania. Ustaw skalę czasu na „Dni”, a format prezentacji na „TaskUsage”.
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## Krok 4: Zapisz w skali czasu w dniach
Zapisz projekt ze wstępnie zdefiniowanymi ustawieniami skali czasu „Dni”.
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Krok 5: Oszczędzaj dzięki skali czasowej ThirdsOfMonths
Zmień ustawienia skali czasu na „ThirdsOfMonths” i zapisz projekt.
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Krok 6: Oszczędzaj w skali czasu w miesiącach
Ustaw skalę czasu na „Miesiące” i zapisz projekt ze zaktualizowanymi ustawieniami.
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## Wniosek
Konfigurowanie widoków użycia zadań za pomocą Aspose.Tasks dla .NET jest prostym procesem. Dostosowując ustawienia skali czasu, możesz dostosować wizualizację zadań projektowych do swoich konkretnych potrzeb.
 Zachęcamy do zapoznania się z większą liczbą funkcji i funkcjonalności w[dokumentacja](https://reference.aspose.com/tasks/net/).
## Często Zadawane Pytania
### Czy mogę dostosować zakres czasu poza wcześniej zdefiniowanymi ustawieniami?
Tak, możesz ustawić niestandardową skalę czasu, określając interwały i jednostki.
### Czy są dostępne inne formaty prezentacji?
Aspose.Tasks obsługuje różne formaty prezentacji, w tym wykres Gantta, ResourceUsage i inne.
### Czy Aspose.Tasks jest kompatybilny z różnymi formatami plików projektów?
Tak, Aspose.Tasks obsługuje popularne formaty plików projektów, takie jak MPP, XML i CSV.
### Czy mogę zastosować różne ustawienia skali czasu do określonych zadań?
Oczywiście możesz dostosować ustawienia skali czasu dla poszczególnych zadań w ramach swojego projektu.
### Jak mogę uzyskać wsparcie lub szukać pomocy dla Aspose.Tasks?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) o wsparcie i wskazówki społeczności.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
