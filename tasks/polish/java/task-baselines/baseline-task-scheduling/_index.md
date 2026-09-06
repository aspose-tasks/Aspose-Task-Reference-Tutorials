---
date: 2026-08-29
description: Dowiedz się, jak odczytywać dane bazowe i planować zadania przy użyciu
  Aspose.Tasks dla Java, aby skutecznie porównywać planowany i rzeczywisty postęp.
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Planowanie zadań bazowych w Aspose.Tasks
og_description: Dowiedz się, jak odczytywać dane bazowe i planować zadania przy użyciu
  Aspose.Tasks dla Java, umożliwiając precyzyjne porównanie planowanego i rzeczywistego
  postępu.
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: Jak odczytać bazę odniesienia i planować zadania przy użyciu Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: Jak odczytać bazę odniesienia i planować zadania przy użyciu Aspose.Tasks
url: /pl/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać baseline i planować zadania przy użyciu Aspose.Tasks

W tym przewodniku odkryjesz **jak odczytać informacje o baseline** i planować zadania programowo przy użyciu Aspose.Tasks dla Javy. Po zakończeniu samouczka będziesz w stanie przechwycić pierwotny plan projektu, porównać go z rzeczywistym postępem i wygenerować raporty odchyleń — wszystko bez konieczności instalacji Microsoft Project.

## Wprowadzenie do baseline zarządzania projektem

Zarządzanie **baseline zarządzania projektem** jest kamieniem węgielnym skutecznego zarządzania projektami. Pozwala na przechwycenie pierwotnego planu i późniejsze porównanie **planowanego vs rzeczywistego postępu**, aby móc wcześnie wykrywać odchylenia. W tym samouczku przeprowadzimy Cię przez proces planowania baseline zadań przy użyciu Aspose.Tasks dla Javy, dając Ci narzędzia do **zarządzania baseline projektów** z pewnością i utrzymania projektów na właściwej drodze.

## Szybkie odpowiedzi
- **Co reprezentuje baseline zarządzania projektem?**  
  Rejestruje zatwierdzony harmonogram, koszt i zakres na początku projektu, zapewniając punkt odniesienia do analizy odchyleń.  
- **Która biblioteka obsługuje planowanie baseline w Javie?**  
  Aspose.Tasks dla Javy oferuje czysto‑Java API, które obsługuje ponad 45 formatów wejścia i wyjścia oraz projekty do 100 000 zadań.  
- **Czy potrzebna jest licencja do uruchomienia kodu?**  
  Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Jakie są główne wymagania wstępne?**  
  Java Development Kit (JDK) 11+ oraz biblioteka Aspose.Tasks dla Javy.  
- **Czy mogę wyświetlić daty baseline po ich ustawieniu?**  
  Tak — użyj obiektu `TaskBaseline`, aby odczytać wartości start, finish i duration.

## Czym jest baseline zarządzania projektem?
Baseline zarządzania projektem rejestruje zatwierdzony harmonogram, budżet i zakres na początku realizacji. Służy jako punkt odniesienia do pomiaru wydajności i identyfikacji odchyleń w całym cyklu życia projektu. Zawiera planowane daty rozpoczęcia i zakończenia, całkowity koszt oraz szczegóły zakresu, zapewniając kompleksowy obraz do przyszłych porównań.

## Dlaczego warto używać Aspose.Tasks do planowania baseline?
Aspose.Tasks udostępnia czysto‑Java API, które działa bez zainstalowanego Microsoft Project. Obsługuje **ponad 45 formatów wejścia i wyjścia**, może przetwarzać projekty z **do 100 000 zadaniami** w trybie oszczędzającym pamięć oraz oferuje wbudowane metody do odczytu i zapisu danych baseline — co ułatwia automatyczne raportowanie i integrację.

## Wymagania wstępne
- **Java Development Kit (JDK)** – zainstaluj JDK 11 lub nowszy. Możesz go pobrać ze [strony internetowej](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Biblioteka Aspose.Tasks dla Javy** – pobierz najnowsze wydanie ze [strony pobierania](https://releases.aspose.com/tasks/java/) i dodaj plik JAR do classpathu swojego projektu.

## Importowanie pakietów
Klasy `Project`, `Task` i `TaskBaseline` znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku swojego pliku źródłowego:

Klasa `Project` jest obiektem najwyższego poziomu Aspose.Tasks, który reprezentuje pojedynczy plik projektu w pamięci. Zapewnia dostęp do zadań, zasobów i kolekcji baseline.

## Jak odczytać baseline?
Wczytaj projekt, a następnie zapytaj kolekcję `TaskBaseline` dla każdego zadania. Obiekt `TaskBaseline` zwraca start, finish i duration baseline, które zostały zapisane po wywołaniu `setBaseline`. To bezpośrednie podejście pozwala odczytać wartości baseline bez parsowania plików XML lub binarnych.

## Krok 1: utwórz nową instancję projektu
Klasa `Project` reprezentuje cały plik projektu w pamięci.
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## Krok 2: zdefiniuj zadanie i ustaw baseline
`Task` reprezentuje pojedynczy element pracy, a `setBaseline` zapisuje jego bieżący harmonogram jako baseline.
```java
Project project = new Project();
```

## Krok 3: uzyskaj dostęp do informacji o baseline
`TaskBaseline` przechowuje zapisane wartości start, finish i duration dla baseline.
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 4: wyświetl czas trwania baseline
`Duration` reprezentuje długość czasu dla zadania lub baseline.
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## Krok 5: wyświetl datę rozpoczęcia baseline
`Start` jest zaplanowaną datą rozpoczęcia baseline.
```java
System.out.println(baseline.getDuration().toString());
```

## Krok 6: wyświetl datę zakończenia baseline
`Finish` jest zaplanowaną datą zakończenia baseline.
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## Typowe problemy i rozwiązania
- **Baseline nie ustawiony:** Upewnij się, że wywołujesz `project.setBaseline(BaselineType.Baseline)` **po** dodaniu zadań; w przeciwnym razie kolekcja baseline będzie pusta.  
- **Wartości null:** Jeśli `task.getBaselines()` zwraca pustą listę, sprawdź, czy zadanie zostało dodane do hierarchii projektu przed ustawieniem baseline.  
- **Format daty:** Metody `getStart()` i `getFinish()` zwracają obiekty `java.util.Date`. Użyj `SimpleDateFormat`, jeśli potrzebny jest niestandardowy format wyświetlania.

## Najczęściej zadawane pytania

**P: Jak utworzyć nową instancję projektu w Aspose.Tasks?**  
A: Zainstancjuj klasę `Project` (`Project project = new Project();`). Tworzy to nowy plik projektu gotowy do zadań i baseline.

**P: Jaka jest różnica między `BaselineType.Baseline` a innymi typami baseline?**  
A: `BaselineType.Baseline` odnosi się do podstawowego baseline (Baseline 1). Aspose.Tasks obsługuje także Baseline 2‑10 dla dodatkowych migawków.

**P: Czy mogę wyeksportować dane baseline do Excela lub CSV?**  
A: Tak, możesz iterować po obiektach `TaskBaseline` i zapisywać wartości do pliku CSV używając standardowego I/O Javy.

**P: Czy ustawienie baseline wpływa na istniejące daty zadań?**  
A: Ustawienie baseline zapisuje bieżące daty, ale nie modyfikuje aktywnego harmonogramu zadania. Możesz nadal zmieniać daty start/finish po ustawieniu baseline.

**P: Czy można programowo porównać wiele baseline?**  
A: Oczywiście. Pobierz każdy baseline za pomocą `task.getBaselines().get(index)` i porównaj ich właściwości `Start`, `Finish` oraz `Duration`.

---

**Ostatnia aktualizacja:** 2026-08-29  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Powiązane samouczki

- [Utwórz listę zadań Java – Baseline MS Project przy użyciu Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)
- [Jak ustawić czas trwania baseline w Aspose.Tasks dla Javy](/tasks/java/task-baselines/task-baseline-duration/)
- [Utwórz projekt MPP Java – Zmiana postępu zadania przy użyciu Aspose.Tasks](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}