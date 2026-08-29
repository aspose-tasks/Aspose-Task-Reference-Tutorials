---
date: 2026-08-29
description: Dowiedz się, jak ustawić baseline duration i śledzić postęp projektu
  przy użyciu Aspose.Tasks for Java. Ten przewodnik krok po kroku pomaga efektywnie
  zarządzać task baselines.
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: Jak ustawić baseline duration w Aspose.Tasks for Java
og_description: Dowiedz się, jak ustawić baseline duration i śledzić postęp projektu
  przy użyciu Aspose.Tasks for Java. Zapoznaj się z tym szczegółowym przewodnikiem,
  aby efektywnie zarządzać task baselines.
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: Jak ustawić baseline duration, aby śledzić postęp projektu
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: Jak ustawić baseline duration, aby śledzić postęp projektu
url: /pl/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić czas trwania linii bazowej, aby śledzić postęp projektu

## Wprowadzenie
Śledzenie postępu projektu zaczyna się od solidnej linii bazowej. W tym samouczku dowiesz się **jak ustawić czas trwania linii bazowej** dla zadań w plikach Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy oraz zrozumiesz, dlaczego wczesne ustalenie linii bazowej pomaga monitorować odchylenia harmonogramu, wariancje kosztów i nadmierne przydzielenie zasobów przez cały okres trwania projektu.

## Szybkie odpowiedzi
- **Co oznacza „ustawienie linii bazowej”?** Rejestruje ona pierwotną datę rozpoczęcia, zakończenia i czas trwania zadania, abyś mógł porównywać przyszłe zmiany.  
- **Która klasa Aspose.Tasks tworzy projekt?** Klasa `Project` – dowiesz się również, jak **poprawnie utworzyć instancję projektu**.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Bezpłatna licencja ewaluacyjna działa w testach; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę pobrać tymczasowe linie bazowe?** Tak, Aspose.Tasks umożliwia zapytanie o tymczasowe linie bazowe i ich stałe koszty.  
- **Jaka wersja Javy jest wymagana?** Zalecana jest Java 8 lub nowsza.  
- **Jak to pomaga w śledzeniu postępu projektu?** Po ustawieniu linii bazowej możesz natychmiast porównać rzeczywiste daty z pierwotnym planem, korzystając z wbudowanych funkcji raportowania.

## Czym jest linia bazowa zadania i dlaczego ją ustawiać?
Linia bazowa zadania przechowuje zaplanowany harmonogram (datę rozpoczęcia, zakończenia i czas trwania) w określonym momencie. Ustawiając linię bazową tworzysz punkt odniesienia, który ułatwia wykrywanie odchyleń harmonogramu, przekroczeń kosztów i nadmiernego przydziału zasobów w miarę rozwoju projektu.

## Dlaczego używać Aspose.Tasks do zarządzania liniami bazowymi?
Aspose.Tasks zapewnia **pełną kompatybilność z .mpp** – możesz odczytywać i zapisywać natywne pliki Microsoft Project bez konieczności instalacji Microsoft Office. API daje programowy dostęp do **ponad 50 formatów wejścia i wyjścia**, obsługuje **tymczasowe linie bazowe 1‑10** oraz może obsługiwać **projekty o setkach stron** bez ładowania całego pliku do pamięci, co jest niezbędne przy wysokowydajnym przetwarzaniu wsadowym.

## Prerequisites
1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8+.  
2. **Aspose.Tasks for Java** – pobierz bibliotekę ze [strony pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **IDE lub narzędzie budujące** – Maven, Gradle lub dowolne IDE, które preferujesz.

## Importowanie pakietów
Poniższe importy wprowadzają podstawowe klasy Aspose.Tasks potrzebne do pracy z projektami, zadaniami, liniami bazowymi i danymi czasowymi.

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Krok 1: utwórz instancję projektu
Klasa `Project` reprezentuje plik Microsoft Project w pamięci i jest punktem wejścia dla wszystkich operacji.

```java
Project project = new Project();
```

## Krok 2: utwórz linię bazową zadania
`TaskBaseline` przechowuje zaplanowane daty rozpoczęcia, zakończenia oraz czas trwania konkretnego zadania.

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 3: wyświetl informacje o linii bazowej zadania
Metoda `getBaselines()` zwraca kolekcję linii bazowych powiązanych z zadaniem.

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Krok 4: sprawdź tymczasową linię bazową i koszt stały
`BaselineType` wylicza podstawowe i tymczasowe linie bazowe (Baseline, Baseline1‑Baseline10).

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Krok 5: wydrukuj dane czasowe
`TimephasedData` reprezentuje fragment informacji o harmonogramie dla określonego przedziału czasu.

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Postępując zgodnie z tymi krokami, możesz **ustawić czas trwania linii bazowej** dla dowolnego zadania i pobrać szczegółowe informacje o linii bazowej przy użyciu Aspose.Tasks for Java, co zapewnia niezawodny sposób na **śledzenie postępu projektu** przez cały cykl życia projektu.

## Typowe problemy i rozwiązania
- **Linia bazowa nie pojawia się w MS Project:** Upewnij się, że wywołałeś `project.setBaseline(BaselineType.Baseline)` **po** dodaniu zadania.  
- **NullPointerException przy `getBaselines()`:** Sprawdź, czy zadanie zostało dodane do projektu przed ustawieniem linii bazowej.  
- **Niezgodność jednostki czasu:** Użyj `TimeUnitType`, aby poprawnie sformatować czas trwania, szczególnie przy pracy z niestandardowymi kalendarzami.

## FAQ
### Czym jest linia bazowa zadania w MS Project?
Linia bazowa zadania w MS Project to migawka początkowego planowanego harmonogramu zadania, obejmująca datę rozpoczęcia, zakończenia oraz czas trwania.

### Dlaczego zarządzanie liniami bazowymi zadania jest ważne?
Zarządzanie liniami bazowymi zadania pomaga porównać planowany harmonogram z rzeczywistym postępem projektu, ułatwiając lepsze śledzenie i podejmowanie decyzji.

### Czy mogę zmodyfikować linię bazową zadania po jej ustawieniu?
Tak, możesz modyfikować linie bazowe zadania w MS Project, aby odzwierciedlić zmiany w planie projektu. Jednak ważne jest dokumentowanie wszelkich odchyleń od pierwotnej linii bazowej.

### Czy Aspose.Tasks obsługuje inne funkcje zarządzania projektami?
Tak, Aspose.Tasks oferuje szeroki zakres funkcji zarządzania projektami, w tym planowanie zadań, przydzielanie zasobów i generowanie wykresów Gantta.

### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?
Wsparcie dla Aspose.Tasks znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i współpracować z innymi użytkownikami.

## Dodatkowe często zadawane pytania
**P: Czy muszę wywoływać `setBaseline` dla każdego zadania osobno?**  
O: Nie. Wywołanie `project.setBaseline(BaselineType.Baseline)` zapisuje linię bazową dla wszystkich zadań w projekcie jednocześnie.

**P: Jak mogę ustawić tymczasową linię bazową dla konkretnego zadania?**  
O: Użyj `project.setBaseline(BaselineType.Baseline1)` (lub Baseline2‑Baseline10) po zaktualizowaniu harmonogramu zadania.

**P: Czy można wyeksportować dane linii bazowej do CSV?**  
O: Tak. Iteruj po `task.getBaselines()` i zapisz wybrane pola do pliku CSV używając standardowego I/O Javy.

**P: Czy mogę odczytać istniejący plik .mpp, który już zawiera linie bazowe?**  
O: Oczywiście. Załaduj plik za pomocą `new Project("myproject.mpp")`, a następnie uzyskaj dostęp do linii bazowych każdego zadania, jak pokazano powyżej.

**P: Czy Aspose.Tasks obsługuje pliki wieloprojektowe?**  
O: Aspose.Tasks działa z pojedynczymi plikami .mpp. W scenariuszach wieloprojektowych należy łączyć projekty programowo.

---

**Ostatnia aktualizacja:** 2026-08-29  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz listę zadań Java – Linia bazowa MS Project przy użyciu Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Utwórz projekt MPP Java – Zmiana postępu zadania przy użyciu Aspose.Tasks](/tasks/java/task-properties/change-progress/)
- [Linia bazowa zarządzania projektem – Planowanie zadań przy użyciu Aspose.Tasks](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}