---
date: 2026-09-25
description: Dowiedz się, jak utworzyć harmonogram projektu w Javie przy użyciu Aspose.Tasks.
  Ten przewodnik pokazuje, jak dodać zadania podsumowujące, zarządzać hierarchią projektu
  oraz efektywnie ustawić katalog dokumentów.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Tworzenie zadań w Aspose.Tasks
og_description: Dowiedz się, jak utworzyć harmonogram projektu w Javie przy użyciu
  Aspose.Tasks. Postępuj zgodnie z instrukcjami krok po kroku, aby dodać zadania podsumowujące,
  zarządzać hierarchią oraz ustawić katalog dokumentów.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Jak utworzyć harmonogram projektu przy użyciu Aspose.Tasks dla Javy
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Jak utworzyć harmonogram projektu przy użyciu Aspose.Tasks dla Javy
url: /pl/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć harmonogram projektu przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku dowiesz się, jak **utworzyć harmonogram projektu** w aplikacji Java przy użyciu Aspose.Tasks. Niezależnie od tego, czy tworzysz prostą listę zadań, czy złożony planer na poziomie przedsiębiorstwa, poniższe kroki przeprowadzą Cię przez dodawanie zadań podsumowujących, zarządzanie hierarchią projektu oraz ustawianie katalogu dokumentu — wszystko z jasnymi, gotowymi do uruchomienia fragmentami kodu. Po zakończeniu będziesz mieć w pełni ustrukturyzowany harmonogram gotowy do dalszej manipulacji lub eksportu.

## Szybkie odpowiedzi
- **Co zarządza Aspose.Tasks?** Obsługuje hierarchie zadań, zasoby, kalendarze i formaty plików projektów (MS‑Project, Primavera itp.).  
- **Czy potrzebuję licencji do rozwoju?** Darmowa licencja tymczasowa działa w trybie ewaluacji; pełna licencja jest wymagana w produkcji.  
- **Która wersja Javy jest obsługiwana?** Java 8 i nowsze są w pełni obsługiwane.  
- **Czy mogę dodać własne pola do zadań?** Tak, możesz rozszerzyć zadania o pola definiowane przez użytkownika za pomocą API.  
- **Czy istnieje wbudowane wsparcie dla wykresów Gantta?** Aspose.Tasks może eksportować do PDF/HTML, które zawierają wizualizacje Gantta.

## Czym jest harmonogram projektu w Aspose.Tasks?
Harmonogram projektu to pełny zestaw zadań, zależności i terminów, które definiują, jak praca będzie wykonywana. Aspose.Tasks przechowuje te informacje w obiekcie `Project`, który możesz odczytać, modyfikować i zapisać w różnych formatach. Zawiera daty rozpoczęcia i zakończenia, ograniczenia oraz przydziały zasobów, umożliwiając kompleksowe planowanie i raportowanie.

## Dlaczego warto używać Aspose.Tasks do zarządzania projektami w Javie?
Aspose.Tasks obsługuje **ponad 30 formatów wejściowych i wyjściowych** i może przetwarzać projekty z **do 10 000 zadaniami** bez ładowania całego pliku do pamięci, zapewniając wysoką wydajność w scenariuszach zarządzania dużymi projektami w Javie.

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania:
- **Java Development Kit (JDK)** – JDK 8 lub nowszy zainstalowany na Twoim komputerze.  
- **Aspose.Tasks for Java library** – Pobierz i zainstaluj bibliotekę z [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrated Development Environment (IDE)** – Użyj Eclipse, IntelliJ IDEA lub dowolnego przyjaznego Javy IDE, które preferujesz.

## Importowanie pakietów
`Project`, `Task` i powiązane klasy znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku swojego pliku Java:

Klasa `Project` reprezentuje kompletny harmonogram projektu i udostępnia metody do manipulacji zadaniami i zasobami.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Klasa `Project` jest punktem wejścia dla wszystkich operacji na pliku projektu.

## Jak utworzyć harmonogram projektu przy użyciu Aspose.Tasks?

Załaduj nową instancję `Project`, ustaw katalog dokumentu i rozpocznij dodawanie zadań. Ten bezpośredni akapit wyjaśnia podstawowy przepływ: tworzysz `Project`, konfigurujesz jego `RootFolder` (katalog dokumentu), a następnie dodajesz zadanie podsumowujące, po którym następują podzadania. Wszystkie zmiany są przechowywane w pamięci, aż wywołasz `save`, aby zapisać harmonogram do pliku.

### Krok 1: ustaw katalog dokumentu
Określ, gdzie zostanie zapisany wynikowy plik projektu. Ustawienie katalogu na początku zapewnia, że wszystkie późniejsze operacje zapisu używają spójnej ścieżki.

Właściwość `RootFolder` określa podstawowy folder, z którego odczytywane są pliki projektu lub do którego zapisywane.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Krok 2: utwórz nowy projekt
Utwórz nowy obiekt `Project`, który będzie przechowywał Twój harmonogram. Opcjonalnie możesz podać istniejącą ścieżkę pliku, aby wczytać istniejący harmonogram do modyfikacji.

Konstruktor `Project` tworzy pusty harmonogram gotowy do dodawania zadań.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 3: dodaj zadanie podsumowujące
Zadanie podsumowujące grupuje powiązane podzadania i pojawia się jako zwijalny węzeł na wykresie Gantta. Użyj klasy `Task` i ustaw `IsSummary` na `true`.

Metoda `addTask` tworzy nowe zadanie pod określonym rodzicem i zwraca jego identyfikator.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Krok 4: dodaj podzadanie
Podzadania dziedziczą daty rozpoczęcia/zakonczenia od swojego zadania podsumowującego, chyba że je nadpiszesz. Dodanie podzadania jest tak proste, jak ponowne wywołanie `addTask` i podanie identyfikatora rodzica.

Wywołanie `addTask` z identyfikatorem rodzica dodaje podzadanie pod tym zadaniem podsumowującym.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Kontynuuj dodawanie dowolnej liczby zadań i podzadań potrzebnych w Twoim projekcie. Każdy krok przyczynia się do budowy ustrukturyzowanej hierarchii projektu, którą można wyeksportować do MS‑Project, PDF lub innych obsługiwanych formatów.

## Typowe problemy i rozwiązania
- **Problem:** „Katalog dokumentu nie został znaleziony.”  
  **Rozwiązanie:** Sprawdź, czy ścieżka przypisana do `RootFolder` istnieje w systemie plików i czy proces Java ma uprawnienia do zapisu.
- **Problem:** Podzadania nie pojawiają się pod zadaniem podsumowującym.  
  **Rozwiązanie:** Upewnij się, że przekazujesz prawidłowy identyfikator zadania rodzica przy wywoływaniu `addTask`. API wymaga identyfikatora rodzica jako drugiego argumentu.
- **Problem:** Duże projekty powodują OutOfMemoryError.  
  **Rozwiązanie:** Aspose.Tasks przetwarza zadania w trybie strumieniowym; zwiększ rozmiar sterty JVM (`-Xmx2g`) lub podziel harmonogram na wiele plików.

## Najczęściej zadawane pytania
**Q: Czy Aspose.Tasks jest odpowiedni dla małych projektów?**  
A: Zdecydowanie tak. Biblioteka skaluje się od listy pojedynczych zadań do harmonogramów na poziomie przedsiębiorstwa z tysiącami zadań.

**Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks dla Javy?**  
A: Odwołaj się do dokumentacji [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q: Jak uzyskać tymczasową licencję dla Aspose.Tasks?**  
A: Odwiedź [temporary license request page](https://purchase.aspose.com/temporary-license/) aby uzyskać licencję czasowo ograniczoną, działającą w środowisku deweloperskim i testowym.

**Q: Czy mogę dostosować atrybuty zadań przy użyciu Aspose.Tasks?**  
A: Tak, możesz rozszerzyć zadania o własne pola, przydzielać zasoby i modyfikować kalendarze programowo.

**Q: Czy istnieje społeczność wsparcia dla użytkowników Aspose.Tasks?**  
A: Zdecydowanie! Dołącz do społeczności Aspose.Tasks na [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2026-09-25  
**Testowano z:** Aspose.Tasks 24.12 for Java  
**Autor:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Powiązane samouczki

- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Javy](/tasks/java/project-properties/write-project-info/)
- [Utwórz zależności zadań zarządzania projektem w Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Jak dodać zasób do projektu i utworzyć przydziały zasobów w Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}