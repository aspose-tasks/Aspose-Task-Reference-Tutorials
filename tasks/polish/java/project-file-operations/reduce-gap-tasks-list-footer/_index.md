---
date: 2025-12-17
description: Dowiedz się, jak wyeksportować projekt do PDF, zmniejszyć odstęp stopki
  i zapisać projekt jako obraz przy użyciu Aspose.Tasks for Java. Optymalizuj układ
  swojego projektu MS Project bez wysiłku.
linktitle: Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Eksportuj projekt do PDF i zmniejsz odstęp między listą zadań a stopką w Aspose.Tasks
url: /pl/java/project-file-operations/reduce-gap-tasks-list-footer/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eksportowanie projektu do PDF i odstępu między listą zadań a stopką w Aspose.Tasks

## Wstęp
W tym samouczku odkryjesz **jak wyeksportować projekt do PDF**, jednocześnie zmniejszając niepożądany odstęp między listą zadań a stopką w pliku Microsoft Project. Po usunięciu przewodnika w przypadku wygenerowania czystych plików PDF, obrazów PNG oraz stron HTML o zwartej kolejności przy użyciu Aspose.Tasks dla Javy. Przejdźmy krok po kroku przez proces.

## Szybkie odpowiedzi
- **Co oznacza „eksportuj projekt do formatu PDF”?** Konwertuje plik MPP na dokument PDF, zachowując zadania, osie czasu i formatowanie.
- **Po co zmniejszać odstęp w stopce?** Mniejsza przerwa tworzy zwarte, bardziej profesjonalnie wyglądające raporty, zwłaszcza w przypadku dokumentów drukowanych lub przeglądanych w Internecie.
- **Czy mogę zapisać projekt również jako obraz?** Tak – Aspose.Tasks obsługuje PNG, JPEG i inne formaty obrazów.
- **Czy potrzebuję specjalnej licencji?** Dostępna jest bezpłatna wersja próbna; do użytku produkcyjnego wymagana jest licencja komercyjna.
- **Która wersja Javy jest wymagana?** Java 8 lub nowsza działa z obecną biblioteką Aspose.Tasks.

## Czym jest „eksport projektu do PDF”?
Eksport projektu do PDF przekształca wewnętrzną strukturę MPP w przenośny dokument, który można otworzyć na dowolnym urządzeniu bez konieczności korzystania z programu Microsoft Project. Jest to idealne rozwiązanie do udostępniania raportów o stanie, aktualizacji dla interesariuszy lub archiwizowania planów projektów.

## Dlaczego warto zmniejszyć odstęp w stopce?
Domyślny odstęp w stopce może powodować niepotrzebne odstępy, powodując problemy z paginacją i nierówny wygląd. Zmniejszenie odstępu zapewnia efektywne wykorzystanie strony przez treść, dzięki czemu końcowy plik PDF lub obraz jest bardziej czytelny.

## Jak zmniejszyć odstęp między listą zadań a stopką?
Aspose.Tasks udostępnia opcję `setReduceFooterGap(true)` dla operacji zapisywania obrazów, plików PDF i HTML. Włączenie tej flagi powoduje, że silnik kompresuje przestrzeń między ostatnim wierszem zadania a stopką strony.

## Zapisz projekt jako obraz za pomocą Aspose.Tasks
Jeśli potrzebujesz wizualnego podglądu harmonogramu, możesz **zapisać projekt jako obraz** (PNG), stosując te same ustawienia redukcji luk.

## Eksport projektu Java do PDF
Poniższe sekcje opisują pełny proces **eksportu projektu Java**, od załadowania pliku MPP do zapisania go w trzech różnych formatach.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
1. Java Development Kit (JDK) – wersja 8 lub nowsza.
2. Aspose.Tasks for Java Library – pobierz ją [tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Zanim przejdziemy do kodowania, zaimportujmy niezbędne pakiety:
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

## Krok 1: Podaj ścieżkę do katalogu danych
```java
String dataDir = "Your Data Directory";
```
Upewnij się, że fragment „Twój katalog danych” został zastąpiony ścieżką do rzeczywistego katalogu danych, w którym znajduje się plik Microsoft Project (w tym przykładzie „HomeMovePlan.mpp”).

## Krok 2: Odczyt pliku MPP
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ten wiersz kodu odczytuje plik Microsoft Project o nazwie „HomeMovePlan.mpp”.

## Krok 3: Ustaw ImageSaveOptions (Zapisz projekt jako obraz)
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Skonfiguruj opcje zapisywania obrazu, ustawiając parametr „ReduceFooterGap” na „true”, aby zmniejszyć odstęp między listą zadań a stopką.

## Krok 4: Zapisz jako obraz
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Zapisz projekt jako obraz ze skonfigurowanymi opcjami.

## Krok 5: Ustaw PdfSaveOptions (Eksportuj projekt do PDF)
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Zdefiniuj opcje zapisywania pliku PDF, ustawiając parametr „ReduceFooterGap” na „true”.

## Krok 6: Zapisz jako PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Zapisz projekt jako PDF ze skonfigurowanymi opcjami.

## Krok 7: Ustaw HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Określ opcje zapisu HTML, ustawiając `ReduceFooterGap` na `true`.

## Krok 8: Zapisz jako HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Zapisz projekt jako plik HTML ze skonfigurowanymi opcjami.

## Podsumowanie
Podsumowując, zmniejszenie odstępu między listą zadań a stopką w plikach programu Microsoft Project to prosty proces dzięki Aspose.Tasks for Java. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz sprawnie **eksportować projekt do pliku PDF**, zapisać go jako obraz lub wygenerować kod HTML, zachowując jednocześnie zwarty i profesjonalny układ.

## Często zadawane pytania (dodatkowe)

**P: Jak zmniejszenie odstępu między stopkami wpływa na paginację?**
O: Minimalizuje to puste miejsce u dołu każdej strony, umożliwiając umieszczenie większej liczby zadań na jednej stronie i zmniejszając całkowitą liczbę stron.

**P: Czy mogę zastosować to samo ustawienie redukcji odstępu tylko do jednej strony?**
O: Tak, ustawiając `setRenderToSinglePage(true)` w `ImageSaveOptions`, możesz kontrolować paginację, jednocześnie zmniejszając odstęp.

**P: Czy opcja `setReduceFooterGap` jest dostępna dla innych formatów wyjściowych?**
O: Obecnie jest obsługiwana dla eksportów PNG, PDF i HTML. W przypadku innych formatów może być konieczne ręczne dostosowanie układu.

**P: Co zrobić, jeśli mój projekt zawiera pola niestandardowe — czy są one zachowywane?**
O: Wszystkie pola niestandardowe są zachowywane podczas eksportu; zmiany układu wpływają tylko na odstępy, a nie na dane.

**P: Czy biblioteka sprawnie obsługuje duże projekty?**
O: Aspose.Tasks przesyła strumieniowo dane i może przetwarzać duże pliki MPP; należy jednak zapewnić wystarczającą ilość pamięci podczas eksportowania obrazów o wysokiej rozdzielczości.

---

**Ostatnia aktualizacja:** 2025-12-17
**Testowano z:** Aspose.Tasks 24.11 dla Javy
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}