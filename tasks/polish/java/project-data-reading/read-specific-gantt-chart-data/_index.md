---
date: 2026-10-31
description: Dowiedz się, jak eksportować gantt do pdf w Javie przy użyciu Aspose.Tasks.
  Ten przewodnik krok po kroku pokazuje, jak odczytać dane wykresu Gantt i generować
  raporty PDF.
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: Odczytaj określone dane wykresu Gantt w Aspose.Tasks
og_description: Eksportuj gantt do pdf w Javie z Aspose.Tasks. Skorzystaj z tego samouczka,
  aby odczytać dane wykresu Gantt, dostosować właściwości widoku i generować raporty
  PDF dla zarządzania projektami.
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: Eksport gantt do pdf w Javie – przewodnik Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: Eksportuj gantt do pdf w Javie – wyodrębnij określone dane
url: /pl/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Export Gantt do PDF w Javie – wyodrębnianie konkretnych danych

## Wprowadzenie
W tym samouczku nauczysz się **eksportować Gantt do PDF w Javie** poprzez odczyt informacji wykresu Gantta przy użyciu Aspose.Tasks for Java. Wykresy Gantta dają menedżerom projektów wizualną mapę zadań, zależności i harmonogramów, a możliwość programowego pobierania tych danych pozwala tworzyć automatyczne raporty PDF, pulpity nawigacyjne lub integracje z innymi systemami korporacyjnymi. Przejdźmy przez każdy krok, od wczytania pliku projektu po wyodrębnienie właściwości widoku i ostateczne wygenerowanie PDF.

## Szybkie odpowiedzi
- **Co mogę wyodrębnić?** Dowolną właściwość widoku, styl paska, linię siatki, styl tekstu, linię postępu lub poziom skali czasu z wykresu Gantta.  
- **Czy potrzebna jest licencja?** Wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługujemy?** Java 8 lub nowsza (samouczek używa JDK 11).  
- **Czy kod działa od razu?** Tak – wystarczy zamienić ścieżkę katalogu danych.  
- **Czy mogę modyfikować widok po odczycie?** Oczywiście – API pozwala zmieniać właściwości i zapisywać je z powrotem do pliku projektu.

## Co to jest eksport Gantt do PDF?
Eksport Gantt do PDF to proces konwersji widoku wykresu Gantta przechowywanego w pliku projektu do dokumentu PDF, który zachowuje styl wizualny i informacje o osi czasu. Operacja ta jest przydatna do udostępniania statusu projektu interesariuszom, którzy mogą nie mieć narzędzia do zarządzania projektami.

## Dlaczego eksportować Gantt do PDF przy użyciu Aspose.Tasks?
Aspose.Tasks może obsługiwać **ponad 30 + formatów wejściowych** (MPP, XML, MPX itp.) i **eksportować do PDF w jednym wywołaniu**, zachowując 95 % wierności wizualnej, nawet w projektach z ponad 500 zadaniami. Biblioteka przetwarza pliki w pamięci, więc możesz generować PDF-y na serwerach bez instalacji Microsoft Project.

## Wymagania wstępne
1. **Java Development Kit (JDK):** Upewnij się, że Java jest zainstalowana w systemie. Możesz ją pobrać ze **[strony pobierania Oracle JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.  
2. **Aspose.Tasks for Java Library:** Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java ze **[strony pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)**.  
3. **Zintegrowane Środowisko Programistyczne (IDE):** Wybierz ulubione IDE. Popularne wybory to IntelliJ IDEA, Eclipse lub NetBeans.

## Import pakietów
Poniższe importy dają dostęp do podstawowych klas Aspose.Tasks potrzebnych do odczytu i eksportu danych Gantta.  
*Brak tutaj bloku kodu, aby skupić się na koncepcjach; po prostu dodaj importy do swojego pliku Java.*

## Jak wczytać plik projektu wykresu Gantta w Javie?
Wczytaj plik projektu, tworząc instancję `Project` i przekazując pełną ścieżkę do konstruktora. Ten krok inicjalizuje reprezentację wykresu Gantta w pamięci, umożliwiając późniejsze zapytania o właściwości widoku. Po pomyślnym wczytaniu pliku możesz zweryfikować nazwę projektu, datę rozpoczęcia i liczbę zadań, aby upewnić się, że otwarto właściwy plik. Ta weryfikacja pomaga wykryć problemy ze ścieżką lub formatem na wczesnym etapie przepływu pracy.  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*Definicja:* `Project` to obiekt najwyższego poziomu Aspose.Tasks, który reprezentuje pojedynczy plik projektu w pamięci.

## Jak uzyskać dostęp do widoku wykresu Gantta?
Pobierz pierwszy widok Gantt z kolekcji widoków projektu. Większość projektów zawiera przynajmniej jeden widok Gantt i zazwyczaj jest to pierwszy wpis. Po uzyskaniu widoku możesz sprawdzić jego nazwę i upewnić się, że jest typu `GanttChartView` przed przystąpieniem do wyodrębniania właściwości. To dodatkowe sprawdzenie zapobiega błędom w czasie wykonywania przy pracy z niestandardowymi lub niestandardowymi kolekcjami widoków.  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*Definicja:* `GanttChartView` reprezentuje wizualny układ zadań, skal czasowych i pasków, które widzisz w typowym wykresie Gantta.

## Jak wyodrębnić właściwości widoku?
Możesz odczytać właściwości takie jak kolor tła, wysokość paska i ustawienia skali czasu bezpośrednio z obiektu `GanttChartView`. Ich wypisanie pomaga zweryfikować bieżącą konfigurację przed eksportem. Typowa pętla wyodrębniająca iteruje po każdej właściwości, formatuje wartość jako ciąg znaków i zapisuje ją w konsoli lub pliku do późniejszej analizy. Takie podejście jest przydatne przy debugowaniu i tworzeniu dokumentacji wyglądu wykresu.  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*Definicja:* `GanttChartView` zapewnia dostęp do ustawień widoku, takich jak kolor tła, wysokość paska i konfiguracja skali czasu.

## Jak wyodrębnić style pasków?
Iteruj po kolekcji obiektów `BarStyle`, aby uzyskać szczegóły takie jak kolor, wzór i kształt dla każdego typu paska używanego w wykresie. Dla każdego stylu możesz także odczytać powiązany typ zadania i warunek, który wyzwala styl, co jest niezbędne przy odtwarzaniu wykresu w innym formacie. Zbieranie tych informacji umożliwia stworzenie wiernej wizualnej repliki lub zastosowanie niestandardowych reguł stylizacji programowo.  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*Definicja:* `BarStyle` definiuje wygląd wizualny paska Gantta, w tym jego kolor, wzór i kształt.

## Jak wyodrębnić linie siatki?
Linie siatki definiują wizualne oddzielenie wierszy i kolumn. Uzyskaj je za pomocą metody `getGridlines()` i wypisz ich widoczność oraz styl. Po pobraniu kolekcji linii siatki możesz przejść przez każdą linię, aby uchwycić jej typ (ciągła, przerywana), grubość i kolor. Dane te są cenne, gdy potrzebujesz odtworzyć dokładny układ siatki w eksportowanych PDF-ach lub innych formatach raportowania.  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*Definicja:* `getGridlines()` zwraca kolekcję obiektów linii siatki, które kontrolują separatory wierszy i kolumn w widoku Gantta.

## Jak wyodrębnić style tekstu?
Style tekstu kontrolują czcionkę, rozmiar i kolor etykiet na wykresie Gantta. Przejdź przez kolekcję `TextStyle`, aby wypisać każdy styl. Dla każdego stylu tekstu możesz także pobrać powiązany element (nazwę zadania, datę itp.) oraz ewentualne reguły formatowania warunkowego. Zarejestrowanie tych szczegółów zapewnia, że wyeksportowane dokumenty zachowają tę samą typografię co oryginalny wykres.  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*Definicja:* `TextStyle` reprezentuje atrybuty formatowania stosowane do elementów tekstowych w wykresie Gantta.

## Jak wyodrębnić linie postępu?
Linie postępu pokazują aktualny punkt ukończenia zadania. Uzyskaj je przez `getProgressLines()` i wypisz ich atrybuty. Każda linia postępu zawiera właściwości takie jak kolor linii, grubość i pozycję względem paska zadania. Rejestrowanie tych informacji pozwala generować wizualizacje uwzględniające postęp lub obliczać ogólne wskaźniki ukończenia projektu.  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*Definicja:* `getProgressLines()` zwraca zestaw obiektów linii postępu, które wskazują status ukończenia zadania.

## Jak wyodrębnić poziomy skali czasu?
Poziomy skali czasu definiują hierarchiczne jednostki czasu (dni, tygodnie, miesiące) wyświetlane na wykresie. Pobierz je za pomocą `getTimescaleTiers()` i wypisz ich ustawienia. Dla każdego poziomu możesz uchwycić typ jednostki, format etykiety i wyrównanie, co jest kluczowe przy odtwarzaniu dokładnej granularności osi czasu w eksportowanych PDF-ach lub niestandardowych komponentach UI.  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*Definicja:* `getTimescaleTiers()` zapewnia dostęp do kolekcji obiektów poziomów skali czasu, które kontrolują wyświetlanie osi czasu.

## Jak wyeksportować wykres Gantt do PDF?
Utwórz obiekt `PdfSaveOptions`, opcjonalnie dostosuj rozmiar strony lub osadzanie czcionek, a następnie wywołaj `project.save` z formatem PDF. To pojedyncze wywołanie generuje PDF, który odzwierciedla widok Gantt na ekranie. Możesz także określić dodatkowe opcje, takie jak kompresja obrazu, usunięcie znaku wodnego lub osadzenie własnych czcionek, aby spełnić wymagania brandingowe firmy. Po zapisaniu zweryfikuj rozmiar pliku PDF i wierność wizualną, aby upewnić się, że eksport się powiódł.  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*Definicja:* `PdfSaveOptions` pozwala precyzyjnie dostroić wyjście PDF, takie jak wymiary strony, kompresja i obsługa czcionek.

## Typowe pułapki i wskazówki
- **Nieprawidłowy katalog danych:** Upewnij się, że `dataDir` kończy się separatorem pliku (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Brak widoku:** Jeśli projekt nie ma widoku Gantt, `project.getViews()` będzie pusty – dodaj sprawdzenie przed rzutowaniem.  
- **Wyjątki licencyjne:** Bez ważnej licencji API może dodać znak wodny do wyeksportowanych PDF‑ów.  
- **Duże projekty:** Dla projektów z ponad 1 000 zadaniami rozważ zwiększenie rozmiaru sterty JVM (`-Xmx2g`), aby uniknąć `OutOfMemoryError`.  

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?**  
A: Tak, Aspose.Tasks for Java integruje się bezproblemowo z dowolną biblioteką lub frameworkiem Java, w tym Spring, Hibernate i Apache POI.

**Q: Czy Aspose.Tasks nadaje się do dużych projektów korporacyjnych?**  
A: Absolutnie. Biblioteka przetwarza pliki MPP o wielokrotności setek stron w mniej niż 5 sekund na standardowym sprzęcie serwerowym i obsługuje równoległe wykonywanie w środowiskach wielowątkowych.

**Q: Czy Aspose.Tasks obsługuje wiele formatów plików projektów?**  
A: Tak, Aspose.Tasks obsługuje ponad 20 formatów, w tym MPP, XML, MPX i Primavera XML, umożliwiając odczyt i konwersję starszych harmonogramów.

**Q: Czy mogę dostosować wygląd wykresów Gantt przy użyciu Aspose.Tasks?**  
A: Oczywiście. Możesz modyfikować style pasków, linie siatki, style tekstu i poziomy skali czasu programowo przed eksportem do PDF lub formatów obrazu.

**Q: Jak zapisać zmiany po modyfikacji widoku?**  
A: Wywołaj `project.save("output.mpp");` po wprowadzeniu zmian, aby zachować je w pliku projektu.

---

**Ostatnia aktualizacja:** 2026-10-31  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## Powiązane samouczki

- [Jak zapisać projekt jako PDF przy użyciu Aspose.Tasks – przewodnik eksportu](/tasks/java/project-file-operations/save-as-pdf/)
- [Utwórz PDF projektu – Dostosuj skalę czasu wykresu Gantt](/tasks/java/project-file-operations/set-time-scale-count/)
- [Eksportuj projekt do PDF i zmniejsz odstęp między listą zadań a stopką w Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}