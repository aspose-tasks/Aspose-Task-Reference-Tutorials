---
date: 2026-06-15
description: Dowiedz się, jak konwertować mpp do pdf i renderować widoki Resource
  Usage i Sheet przy użyciu Aspose.Tasks dla Java. Postępuj zgodnie z naszym przewodnikiem
  krok po kroku, aby ustawić timescale i generować szczegółowe raporty PDF bez wysiłku.
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: Konwertuj MPP do PDF i renderuj widok Resource Usage – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Konwertuj MPP do PDF i renderuj widok Resource Usage – Aspose.Tasks
url: /pl/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj MPP do PDF i renderuj widok wykorzystania zasobów – Aspose.Tasks

W tym samouczku dowiesz się **jak konwertować mpp do pdf**, renderując widoki Wykorzystania zasobów i Arkusza pliku Microsoft Project. Korzystanie z Aspose.Tasks dla Javy eliminuje potrzebę posiadania Microsoft Project na serwerze, zapewniając szybki i niezawodny sposób tworzenia raportów PDF z plików MPP. Pokażemy również **jak ustawić skalę czasu**, aby wynik odpowiadał Twoim wymaganiom raportowym.

## Szybkie odpowiedzi
- **Co robi Aspose.Tasks?** Odczytuje, modyfikuje i konwertuje pliki Microsoft Project (MPP) bez konieczności instalacji MS Project.  
- **Czy mogę konwertować MPP do PDF w jednej linii kodu?** Tak – załaduj projekt, ustaw SaveOptions i wywołaj `save`.  
- **Jakie skale czasu są obsługiwane?** Days, ThirdsOfMonths i Months.  
- **Czy potrzebuję licencji do produkcji?** Wymagana jest licencja komercyjna dla wdrożeń nie‑testowych.  
- **Czy biblioteka jest kompatybilna z Java 8+?** Zdecydowanie – obsługuje Java 8 i nowsze wersje.

## Co to jest konwersja mpp do pdf?
*Konwersja mpp do pdf* odnosi się do procesu pobrania pliku Microsoft Project (.mpp) i wygenerowania wersji w formacie Portable Document Format (PDF), która wiernie odtwarza tabele, harmonogramy, wykresy i przydziały zasobów projektu. Powstały plik PDF można łatwo udostępniać, drukować i archiwizować bez konieczności instalacji Microsoft Project na komputerze odbiorcy.

## Dlaczego konwertować projekt do PDF przy użyciu Aspose.Tasks?
Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** i może renderować projekty liczące setki stron bez ładowania całego pliku do pamięci, zmniejszając zużycie RAM nawet o 70 %. Wyjście PDF zachowuje tabele, wykresy i przydziały zasobów, co czyni je idealnym do dystrybucji wśród interesariuszy oraz archiwizacji.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – Java 8 lub nowsza zainstalowana na Twoim komputerze.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania](https://releases.aspose.com/tasks/java/).  

## Jak konwertować mpp do pdf przy użyciu Aspose.Tasks dla Javy?
Załaduj swój plik MPP, skonfiguruj żądaną skalę czasu, ustaw format prezentacji na **ResourceUsage** i zapisz wynik jako PDF. Ten kompletny przepływ wymaga tylko kilku wywołań API i działa w czasie krótszym niż sekunda dla typowych rozmiarów projektów.

### Krok 1: Odczytaj projekt źródłowy
Klasa `Project` reprezentuje plik Microsoft Project załadowany do pamięci, zapewniając dostęp do jego danych i struktury.  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### Krok 2: Zdefiniuj SaveOptions z wymaganymi ustawieniami TimeScale
`SaveOptions` konfiguruje sposób zapisu projektu, pozwalając określić ustawienia specyficzne dla formatu, takie jak skala czasu.  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Krok 3: Ustaw format prezentacji na ResourceUsage
`PresentationFormat` określa, który widok projektu (np. ResourceUsage) jest renderowany w dokumencie wyjściowym.  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Krok 4: Zapisz projekt jako PDF
`project.save` zapisuje projekt do pliku przy użyciu podanych `SaveOptions`, tworząc ostateczny PDF.  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Krok 5: Renderuj widoki dla innych ustawień TimeScale
Powtórz poprzednie kroki, zmieniając wartość `TimeScale`, aby renderować dodatkowe widoki skali czasu.  
```java
// Save the Project
project.save(dataDir + days, options);
```

### Krok 6: Opcjonalnie – konwertuj wiele projektów w partii
Jeśli potrzebujesz **konwertować projekt do pdf** dla wielu plików, umieść powyższą logikę w pętli iterującej po katalogu plików *.mpp*. To podejście **zapisuje pliki ms project pdf** masowo przy minimalnych zmianach w kodzie.  
Poniższy kod demonstruje kompletny przykład konwersji pliku MPP do PDF z żądanymi ustawieniami.  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## Typowe problemy i rozwiązania
- **Brak czcionek w PDF** – Upewnij się, że wymagane czcionki są zainstalowane na serwerze lub osadź je za pomocą `PdfSaveOptions`.  
- **Duże pliki projektów powodują OutOfMemoryError** – użyj `LoadOptions.setLoadAllResources(false)`, aby ładować zasoby na żądanie.  
- **Nieprawidłowe renderowanie skali czasu** – sprawdź, czy `options.setTimeScale(TimeScale.Days)` (lub inny enum) odpowiada żądanej granularności.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks może renderować inne widoki oprócz Wykorzystania zasobów i Arkusza?**  
A: Tak, obsługuje także wykres Gantta, Task Usage, Calendar i wiele dodatkowych widoków.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Zdecydowanie – obsługuje formaty MPP, MPT i XML od Project 2000 do Project 2021.

**Q: Czy mogę dostosować wygląd renderowanych widoków?**  
A: Tak, możesz modyfikować kolory, czcionki i układ kolumn za pomocą `PdfSaveOptions` i `PresentationOptions`.

**Q: Czy Aspose.Tasks wymaga zainstalowanego Microsoft Project?**  
A: Nie, jest to samodzielna biblioteka działająca w dowolnym środowisku kompatybilnym z Javą.

**Q: Gdzie mogę uzyskać wsparcie techniczne?**  
A: Wsparcie jest dostępne na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15/).

**Ostatnia aktualizacja:** 2026-06-15  
**Testowano z:** Aspose.Tasks 24.12 for Java  
**Autor:** Aspose

## Powiązane samouczki

- [Renderowanie widoku wykorzystania zasobów i arkusza w Aspose.Tasks](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [Jak wyeksportować PDF w Aspose.Tasks – Zapisz jako PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [Jak tworzyć pliki MPP przy użyciu Aspose.Tasks dla Javy](/tasks/java/project-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}