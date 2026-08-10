---
date: 2026-05-26
description: Dowiedz się, jak eksportować MPP do CSV, zapisać projekt jako Template
  oraz konwertować MPP na tekst przy użyciu Aspose.Tasks dla Java.
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: Eksportuj MPP do CSV, tekstu i Template przy użyciu Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Eksportuj MPP do CSV, tekstu i Template przy użyciu Aspose.Tasks Java
url: /pl/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eksport MPP do CSV, Tekstu i Szablonu przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku dowiesz się **jak eksportować MPP do CSV**, tworzyć wielokrotnego użytku szablony projektów oraz generować wyciągi w formacie zwykłego tekstu przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy budujesz potok raportowania, automatyzujesz tworzenie projektów, czy integrujesz się z innymi systemami, te kroki przeniosą Cię od surowego pliku MPP do dokładnie takiego wyniku, jakiego potrzebujesz — szybko i bez instalacji Microsoft Project.

## Szybkie odpowiedzi
- **Czy mogę eksportować MPP do CSV?** Tak – wywołaj `project.save("output.csv", SaveFileFormat.CSV)`.  
- **Jak wyeksportować do zwykłego tekstu?** Użyj `SaveFileFormat.TEXT` z metodą `save`.  
- **Co robi „zapisz projekt jako szablon”?** Tworzy plik `.mpt`, który usuwa daty i linie bazowe, pozostawiając jedynie szkielet.  
- **Czy potrzebna jest licencja?** Wersja próbna działa w trybie ewaluacji; licencja komercyjna usuwa ograniczenia wersji próbnej.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub nowsza jest w pełni wspierana.

## Co to jest „zapisz projekt jako szablon”?
Zapisanie projektu jako szablonu (`.mpt`) zachowuje strukturę, hierarchię zadań i przydziały zasobów, jednocześnie usuwając rzeczywiste daty rozpoczęcia/zakończenia oraz dane linii bazowych. Dzięki temu szablon jest idealny do ponownego wykorzystania standardowego układu projektu w wielu nowych projektach. Zachowuje wszystkie pola niestandardowe, stawki kosztów i szczegóły przydziałów, zapewniając, że szablon może być zastosowany do dowolnego nowego projektu bez utraty istotnej konfiguracji.

## Dlaczego używać Aspose.Tasks dla Javy?
Eksportuj MPP do CSV, tekstu lub szablonu bezpośrednio z Javy, bez Microsoft Project. Aspose.Tasks obsługuje **ponad 20 wersji Microsoft Project** (2000‑2024) i może przetwarzać pliki do **500 MB** w trybie oszczędzającym pamięć, co czyni go idealnym do automatyzacji po stronie serwera, potoków CI oraz narzędzi wieloplatformowych.

## Wymagania wstępne
- Zainstalowany Java Development Kit 8 lub nowszy.  
- Biblioteka Aspose.Tasks for Java dodana do projektu – pobierz z [tutaj](https://releases.aspose.com/tasks/java/).  
- Inne biblioteki Aspose możesz przeglądać pod [tutaj](https://releases.aspose.com/).  
- Podstawowa znajomość Javy oraz konfiguracji projektu Maven/Gradle.

## Importowanie pakietów
Klasa `Project` jest podstawowym obiektem Aspose.Tasks, który reprezentuje plik Microsoft Project w pamięci. Po dodaniu biblioteki do pliku budowania, zaimportuj wymagane klasy:

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## Zapisz projekt jako CSV (Eksport MPP do CSV)
Eksportowanie pliku MPP do CSV umożliwia wprowadzanie danych zadań do Excela, Power BI lub dowolnej platformy analitycznej.

### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Zapisz jako CSV
`SaveFileFormat.CSV` informuje Aspose.Tasks, aby wyeksportował projekt w formacie CSV.  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## Zapisz projekt jako tekst (Jak wyeksportować tekst)
Plik w formacie zwykłego tekstu zapewnia szybki, czytelny dla człowieka zrzut zadań, zasobów i przydziałów.

### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Zapisz jako tekst
`SaveFileFormat.TEXT` instruuje bibliotekę do wygenerowania reprezentacji projektu w zwykłym tekście.  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## Zapisz projekt jako szablon (Utwórz szablon projektu w Javie)

### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### Krok 2: Ustaw opcje szablonu
Użyj `Project.save` z `SaveFileFormat.MPT` (lub `SaveFileFormat.TEMPLATE`), aby utworzyć plik szablonu, który usuwa daty i linie bazowe.  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### Krok 3: Zapisz jako szablon
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Typowe problemy i wskazówki
- **Plik nie znaleziony:** Sprawdź ścieżkę do `YourProject.mpp` lub użyj ścieżki bezwzględnej.  
- **Wyjątki licencyjne:** Bez ważnej licencji biblioteka działa w trybie ewaluacji i może dodawać znaki wodne. Zastosuj licencję wcześnie (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`).  
- **Duże projekty:** Dla plików większych niż 200 MB zwiększ przydział pamięci JVM (`-Xmx2g`), aby zapobiec `OutOfMemoryError`.  
- **Wydajność:** Przy konwertowaniu wielu projektów, w miarę możliwości ponownie używaj jednej instancji `Project`, aby zmniejszyć narzut tworzenia obiektów.

## Zakończenie
Pokazaliśmy, jak **eksportować MPP do CSV**, **przekształcić MPP w tekst** oraz **zapisać projekt jako szablon** przy użyciu Aspose.Tasks dla Javy. Te możliwości pozwalają automatyzować raportowanie, tworzyć ustandaryzowane szkielety projektów i integrować dane projektowe z dowolnym systemem downstream — bez konieczności instalacji Microsoft Project.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks dla Javy radzi sobie ze złożonymi, wieloetapowymi projektami?**  
A: Tak, w pełni obsługuje zadania, zasoby, przydziały, linie bazowe i pola niestandardowe we wszystkich wersjach Project do 2024 roku.

**Q: Czy dostępna jest wersja próbna?**  
A: Oczywiście – pobierz darmową wersję próbną z [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać pomoc w razie problemów?**  
A: Oficjalne forum wsparcia znajduje się pod adresem [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), gdzie personel i członkowie społeczności odpowiadają na pytania.

**Q: Czy mogę uzyskać tymczasową licencję na krótkoterminową ewaluację?**  
A: Tak, zakup tymczasową licencję pod [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Czy Aspose.Tasks działa na Linux i macOS?**  
A: Jest w pełni wieloplatformowy i działa na Windows, macOS i Linux z dowolnym środowiskiem uruchomieniowym Java 8+.

---

**Ostatnia aktualizacja:** 2026-05-26  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć plik MPP – Tworzenie i zapisywanie pustego projektu w formacie MPP przy użyciu Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Ładowanie pliku MPP w Javie – Zarządzanie właściwościami projektu przy użyciu Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Jak wyeksportować MPP do Excela przy użyciu Aspose.Tasks dla Javy](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}