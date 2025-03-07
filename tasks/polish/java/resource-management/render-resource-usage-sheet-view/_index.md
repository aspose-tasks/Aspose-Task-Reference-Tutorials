---
title: Renderuj wykorzystanie zasobów i widok arkusza w Aspose.Tasks
linktitle: Renderuj wykorzystanie zasobów i widok arkusza w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak renderować widoki użycia zasobów i arkuszy MS Project w Aspose.Tasks dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby bez wysiłku wygenerować szczegółowe raporty w formacie PDF.
weight: 16
url: /pl/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Renderuj wykorzystanie zasobów i widok arkusza w Aspose.Tasks

## Wstęp
W tym samouczku dowiemy się, jak używać Aspose.Tasks dla Java do renderowania widoków użycia zasobów i arkusza MS Project. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz zainstalowane i skonfigurowane następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit. Możesz pobrać i zainstalować najnowszą wersję JDK ze strony internetowej Oracle.
2.  Aspose.Tasks dla Java: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla Java z pliku[strona pobierania](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Krok 1: Przeczytaj projekt źródłowy
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
// Przeczytaj projekt źródłowy
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
W tym kroku podajemy ścieżkę do źródłowego pliku projektu (`ResourceUsageView.mpp` ) i użyj`Project` klasę, żeby to przeczytać.
## Krok 2: Zdefiniuj SaveOptions z wymaganymi ustawieniami skali czasu
```java
// Zdefiniuj SaveOptions z wymaganymi ustawieniami TimeScale jako dni
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Tutaj definiujemy`SaveOptions` z wymaganymi`TimeScale` ustawienia. W tym przykładzie ustawiliśmy`TimeScale` do Dni.
## Krok 3: Ustaw Format prezentacji na ResourceUsage
```java
// Ustaw format prezentacji na ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Ustawiamy format prezentacji na`ResourceUsage`, wskazując, że chcemy wyrenderować widok użycia zasobu.
## Krok 4: Zapisz projekt
```java
// Zapisz projekt
project.save(dataDir + days, options);
```
Na koniec zapisujemy projekt z określonymi opcjami. W tym przykładzie plik wyjściowy zostanie zapisany jako`result_days.pdf`.
## Krok 5: Renderuj widoki dla innych ustawień skali czasu
Powtórz kroki od 2 do 4, aby renderować widoki z różnymi ustawieniami skali czasu (trzecie miesiące i miesiące).
```java
// Ustaw ustawienia skali czasu na ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Zapisz projekt
project.save(thirds, options);
// Ustaw ustawienia Skali czasu na Miesiące
options.setTimescale(Timescale.Months);
// Zapisz projekt
project.save(dataDir + months, options);
```
 Pamiętaj o zmianie`Timescale` ustawienia odpowiednio dla każdego widoku.

## Wniosek
W tym samouczku omówiliśmy, jak używać Aspose.Tasks dla języka Java do renderowania widoków użycia zasobów i arkusza programu MS Project. Wykonując czynności opisane powyżej, możesz wydajnie generować te widoki w formacie PDF, ułatwiając lepszą wizualizację i analizę danych projektu.
## Często zadawane pytania
### Czy Aspose.Tasks może renderować inne widoki oprócz użycia zasobów i arkusza?
Aspose.Tasks obsługuje między innymi renderowanie różnych widoków, takich jak Wykres Gantta, Obciążenie zadaniami i Widoki kalendarza.
### Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików Microsoft Project, w tym formaty MPP, MPT i XML.
### Czy mogę dostosować wygląd renderowanych widoków za pomocą Aspose.Tasks?
Absolutnie! Aspose.Tasks zapewnia rozbudowane opcje dostosowywania wyglądu i układu renderowanych widoków do własnych wymagań.
### Czy Aspose.Tasks wymaga zainstalowania programu Microsoft Project w systemie?
Nie, Aspose.Tasks jest samodzielną biblioteką i do swojego działania nie wymaga instalacji Microsoft Project.
### Czy dostępna jest pomoc techniczna dla użytkowników Aspose.Tasks?
 Tak, użytkownicy Aspose.Tasks mogą skorzystać ze wsparcia technicznego za pośrednictwem[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
