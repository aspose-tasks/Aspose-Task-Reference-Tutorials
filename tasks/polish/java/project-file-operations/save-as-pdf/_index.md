---
title: Zapisz jako plik PDF w Aspose.Tasks
linktitle: Zapisz jako plik PDF w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak konwertować pliki projektu do formatu PDF za pomocą Aspose.Tasks dla Java. Proste kroki do skutecznej konwersji.
weight: 17
url: /pl/java/project-file-operations/save-as-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz jako plik PDF w Aspose.Tasks

## Wstęp
tym samouczku przeprowadzimy Cię przez proces zapisywania projektu w formacie PDF przy użyciu Aspose.Tasks dla Java. Dzięki Aspose.Tasks możesz efektywnie konwertować pliki projektu do formatu PDF, zapewniając kompatybilność i łatwość udostępniania. Przejdźmy do kroków:
## Warunki wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Tasks dla biblioteki Java: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/tasks/java/).
3. Plik projektu: przygotuj plik projektu (np. HomeMovePlan.mpp), który chcesz przekonwertować do formatu PDF.

## Importuj pakiety
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Krok 1: Przeczytaj wejściowy plik projektu
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Upewnij się, że wymieniłeś`"Your Data Directory"` ze ścieżką do katalogu danych zawierającego plik projektu.
## Krok 2: Zapisz projekt jako plik PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Ten fragment kodu zapisuje projekt jako plik PDF o nazwie „Project5.pdf”.
## Krok 3: Dopasowywanie zawartości do rozmiaru komórki
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Tutaj ustawiamy opcje zapisywania pliku PDF, w tym dopasowanie treści, harmonogram i format prezentacji.
## Krok 4: Ukryj legendy
```java
o.setLegendOnEachPage(false);
```
Ten krok powoduje ukrycie legend na każdej stronie pliku PDF.
## Krok 5: Zapisz projekt z zastosowanymi opcjami
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Na koniec ten kod zapisuje projekt z zastosowanymi opcjami do pliku PDF.

## Wniosek
W tym samouczku nauczyliśmy się używać Aspose.Tasks dla Java do zapisywania projektu w formacie PDF. Wykonując te proste kroki, możesz efektywnie konwertować pliki projektu w celu łatwego udostępniania i dystrybucji.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Java?
O: Tak, Aspose.Tasks obsługuje wersje Java począwszy od JDK 6 i nowszych.
### P: Czy mogę dostosować wygląd pliku PDF?
Odp.: Absolutnie! Aspose.Tasks zapewnia różne opcje dostosowywania wyjściowego pliku PDF zgodnie z własnymi wymaganiami.
### P: Czy Aspose.Tasks obsługuje inne formaty plików do konwersji?
Odp.: Tak, Aspose.Tasks obsługuje szeroką gamę formatów plików, w tym MPP, XML, XLSX i inne.
### P: Czy dostępna jest wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks od[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
 O: Aby uzyskać wsparcie i pomoc, możesz odwiedzić stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
