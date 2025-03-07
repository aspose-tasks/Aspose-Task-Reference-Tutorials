---
title: Zmniejszanie odstępu między listą zadań a stopką w Aspose.Tasks
linktitle: Zmniejszanie odstępu między listą zadań a stopką w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zmniejszyć lukę między listami zadań MS Project a stopkami za pomocą Aspose.Tasks dla Java. Z łatwością optymalizuj układ dokumentu projektu.
weight: 10
url: /pl/java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmniejszanie odstępu między listą zadań a stopką w Aspose.Tasks

## Wstęp
W tym samouczku zajmiemy się zmniejszeniem luki między listą zadań a stopką w plikach Microsoft Project za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, będziesz w stanie bez wysiłku zoptymalizować układ dokumentów projektu.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Biblioteka Aspose.Tasks for Java: Pobierz i dołącz bibliotekę Aspose.Tasks for Java do swojego projektu. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Zanim zagłębimy się w kodowanie, zaimportujmy niezbędne pakiety:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Krok 1: Podaj ścieżkę do swojego katalogu danych
```java
String dataDir = "Your Data Directory";
```
 Pamiętaj o wymianie`"Your Data Directory"` ze ścieżką do aktualnego katalogu danych, w którym znajduje się plik Microsoft Project (`HomeMovePlan.mpp` w tym przykładzie) znajduje się.
## Krok 2: Przeczytaj plik MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Ten wiersz kodu odczytuje plik Microsoft Project o nazwie`HomeMovePlan.mpp`.
## Krok 3: Ustaw opcje ImageSave
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Skonfiguruj opcje zapisywania obrazu, ustawienia`ReduceFooterGap` Do`true` aby zmniejszyć odstęp pomiędzy listą zadań a stopką.
## Krok 4: Zapisz jako obraz
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Zapisz projekt jako obraz ze skonfigurowanymi opcjami.
## Krok 5: Ustaw opcje PdfSave
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Zdefiniuj opcje zapisywania plików PDF, upewniając się, że są ustawione`ReduceFooterGap` Do`true`.
## Krok 6: Zapisz jako plik PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Zapisz projekt jako plik PDF ze skonfigurowanymi opcjami.
## Krok 7: Ustaw opcje HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // ustawić na true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Określ opcje zapisywania HTML, ustawienie`ReduceFooterGap` Do`true`.
## Krok 8: Zapisz jako HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Zapisz projekt jako plik HTML ze skonfigurowanymi opcjami.

## Wniosek
Podsumowując, zmniejszenie luki między listą zadań a stopką w plikach Microsoft Project jest prostym procesem dzięki Aspose.Tasks dla Java. Wykonując kroki opisane w tym samouczku, możesz skutecznie zoptymalizować układ dokumentów projektu.

## Często zadawane pytania

### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?

Odp.: Aspose.Tasks obsługuje formaty Microsoft Project 2003-2019, zapewniając kompatybilność w różnych wersjach.

### P: Czy mogę dostosować wygląd stopki w dokumentach projektu?

O: Tak, Aspose.Tasks zapewnia szerokie możliwości dostosowywania wyglądu stopek, w tym zmniejszania przerw i dostosowywania rozmieszczenia treści.

### P: Czy Aspose.Tasks obsługuje zapisywanie projektów w formatach innych niż PNG, PDF i HTML?

Odp.: Tak, Aspose.Tasks obsługuje szeroką gamę formatów, w tym między innymi XLSX, XML i MPP.

### P: Czy dostępna jest wersja próbna Aspose.Tasks?

 Odp.: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony[Tutaj](https://releases.aspose.com/).

### P: Gdzie mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy podczas korzystania z Aspose.Tasks?

 Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
