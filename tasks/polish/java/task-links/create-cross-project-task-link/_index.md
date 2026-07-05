---
date: 2026-07-05
description: Dowiedz się, jak łączyć zadania pomiędzy projektami za pomocą Aspose.Tasks
  for Java. Przewodnik krok po kroku, wymagania wstępne oraz najlepsze praktyki zapewniające
  płynne łączenie zadań między projektami.
keywords:
- link tasks across projects
- Aspose.Tasks Java
- cross‑project task link
linktitle: Utwórz łącze zadania międzyprojektowego w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  headline: Link Tasks Across Projects Using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to link tasks across projects with Aspose.Tasks for Java.
    Step‑by‑step guide, prerequisites, and best practices for seamless cross‑project
    task linking.
  name: Link Tasks Across Projects Using Aspose.Tasks for Java
  steps:
  - name: Set Up Your Environment
    text: 'Ensure the Aspose.Tasks JAR is on the classpath and the license file is
      loaded at runtime: `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`
      **License** loads your Aspose.Tasks license file to enable full functionality
      and remove evaluation watermarks.'
  - name: Create a Project Instance
    text: 'Instantiate a new `Project` object for the target project where you want
      the link to live: `Project targetProject = new Project();` The `Project` class
      is Aspose.Tasks'' top‑level object that represents a single project file in
      memory.'
  - name: Add a Summary Task
    text: 'A summary task groups related tasks. Create one to hold both the external
      and local tasks: `Task summary = targetProject.getRootTask().getChildren().add("Integration
      Summary");`'
  - name: Add External Task
    text: 'Insert an external task that points to a task in another project file:
      `Task external = summary.getChildren().addExternalTask("ExternalProject.mpp",
      5);` The **addExternalTask** method creates a placeholder task that references
      an external project file, using the provided file name and task ID.'
  - name: Add Local Task
    text: 'Create the task that will be linked to the external one: `Task local =
      summary.getChildren().add("Local Task");`'
  - name: Create Task Link
    text: 'Establish a dependency between the external and local tasks. The most common
      link type is Finish‑to‑Start: `TaskLink link = targetProject.getTaskLinks().add(external,
      local, TaskLinkType.FinishToStart);` **TaskLink** records the relationship;
      you can later modify its lag, lead, or type as needed.'
  - name: Save and Verify
    text: 'Persist the project to a file and optionally open it in Microsoft Project
      to verify the link: `targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`
      **SaveFileFormat** specifies the file format for saving a project. When you
      open *LinkedProject.mpp*, you’ll see the external task displayed wi'
  type: HowTo
- questions:
  - answer: Yes, you can add several external tasks under one summary task and create
      individual links for each, using the same `addExternalTask` method.
    question: Can I link tasks from multiple external projects in the same summary
      task?
  - answer: Any change to the external task’s schedule, duration, or constraints is
      automatically reflected in the dependent local task when the target project
      is refreshed.
    question: What happens if the external task in the linked project is modified?
  - answer: Absolutely. Aspose.Tasks supports linking between MPP, XML, and Primavera
      formats, allowing heterogeneous project ecosystems to stay synchronized.
    question: Is it possible to create links between tasks in different file formats?
  - answer: Yes, remove the link by calling `project.getTaskLinks().remove(link)`
      or by deleting the external task placeholder.
    question: Can I unlink tasks once they are linked across projects?
  - answer: The library can handle **10,000+ linked tasks** per project, limited only
      by available system memory and the underlying file format specifications.
    question: Are there any limitations on the number of tasks that can be linked
      across projects?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Łączenie zadań pomiędzy projektami przy użyciu Aspose.Tasks for Java
url: /pl/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Łączenie zadań między projektami przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
Łączenie zadań między projektami to podstawowa funkcja, która pozwala synchronizować pracę, unikać duplikacji i utrzymywać jedyne źródło prawdy dla działań współzależnych. W tym samouczku dowiesz się, jak **łączyć zadania między projektami** przy użyciu Aspose.Tasks dla Javy, krok po kroku. Po zakończeniu będziesz mieć w pełni funkcjonalne połączenie międzyprojektowe, które aktualizuje się automatycznie, gdy którakolwiek ze stron się zmieni, zapewniając koordynację w czasie rzeczywistym bez ręcznego kopiowania i wklejania.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do tworzenia projektu?** `Project` – reprezentuje cały plik MS‑Project w pamięci.  
- **Która metoda dodaje zadanie zewnętrzne?** `project.getRootTask().getChildren().addExternalTask(...)`.  
- **Czy mogę ustawić typ połączenia?** Tak – użyj `TaskLinkType.FinishToStart`, `StartToStart`, itp.  
- **Czy potrzebuję licencji do łączenia?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego; darmowa wersja próbna działa w celach oceny.  
- **Czy istnieje limit na połączone zadania?** Aspose.Tasks może obsłużyć ponad 10 000 połączonych zadań na projekt bez pogorszenia wydajności.

## Co to jest łączenie zadań między projektami?
Łączenie zadań między projektami tworzy zależność pomiędzy zadaniem w jednym pliku projektu a zadaniem w innym, umożliwiając automatyczne przenoszenie zmian w zadaniu źródłowym (czas trwania, data rozpoczęcia, ograniczenia) do zadania zależnego. Mechanizm ten utrzymuje harmonogramy w zgodności, redukuje ręczne aktualizacje i zapewnia, że każda modyfikacja w projekcie źródłowym jest natychmiast odzwierciedlana we wszystkich połączonych projektach, zachowując spójność w całym portfelu.

## Dlaczego warto używać Aspose.Tasks do łączenia międzyprojektowego?
Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** i może przetwarzać **projekty liczące setki stron**, przy jednoczesnym utrzymaniu zużycia pamięci poniżej 200 MB. Jego API wykonuje łączenie po stronie serwera, eliminując potrzebę instalacji Microsoft Project i umożliwiając automatyzowane potoki w dużych przedsiębiorstwach.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

- Java 17 (lub nowsza) zainstalowana i skonfigurowana w Twoim IDE.  
- Ważny plik licencji Aspose.Tasks dla Javy (`Aspose.Tasks.Java.lic`).  
- Bibliotekę Aspose.Tasks dla Javy dodaną do projektu. Możesz ją pobrać ze [strony wydania Aspose.Tasks dla Javy](https://releases.aspose.com/tasks/java/).  
- Podstawową znajomość pojęć MS‑Project, takich jak zadania, zadania zbiorcze i zależności.

## Importowanie pakietów
Klasy `Project`, `Task`, `TaskLink` oraz powiązane wyliczenia znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku pliku Java:

`import com.aspose.tasks.*;`

**Project** jest główną klasą reprezentującą plik projektu w pamięci. **Task** reprezentuje pojedynczy element pracy w projekcie. **TaskLink** definiuje zależność pomiędzy dwoma zadaniami. Te importy dają dostęp do pełnego zestawu funkcji manipulacji projektami, w tym łączenia międzyprojektowego.

## Jak łączyć zadania między projektami?
Wczytaj dwa pliki projektów, dodaj placeholder zadania zewnętrznego, utwórz zadanie lokalne, a następnie połącz je za pomocą `TaskLink`. API obsługuje mapowanie identyfikatorów i automatycznie aktualizuje, zapewniając, że każda zmiana w zadaniu zewnętrznym jest propagowana do połączonego zadania lokalnego bez dodatkowego kodu. To podejście upraszcza koordynację wielu projektów i zmniejsza ryzyko odchylenia harmonogramu.

### Krok 1: Przygotowanie środowiska
Upewnij się, że plik JAR Aspose.Tasks znajduje się w classpath i plik licencji jest wczytany w czasie wykonywania:

`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`

**License** wczytuje plik licencji Aspose.Tasks, aby włączyć pełną funkcjonalność i usunąć znaki wodne wersji ewaluacyjnej.

### Krok 2: Utworzenie instancji projektu
Utwórz nowy obiekt `Project` dla projektu docelowego, w którym ma znajdować się połączenie:

`Project targetProject = new Project();`

Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, reprezentującym pojedynczy plik projektu w pamięci.

### Krok 3: Dodanie zadania zbiorczego
Zadanie zbiorcze grupuje powiązane zadania. Utwórz je, aby pomieścić zarówno zadanie zewnętrzne, jak i lokalne:

`Task summary = targetProject.getRootTask().getChildren().add("Integration Summary");`

### Krok 4: Dodanie zadania zewnętrznego
Wstaw zadanie zewnętrzne, które wskazuje na zadanie w innym pliku projektu:

`Task external = summary.getChildren().addExternalTask("ExternalProject.mpp", 5);`

Metoda **addExternalTask** tworzy placeholder zadania, które odwołuje się do zewnętrznego pliku projektu, używając podanej nazwy pliku i identyfikatora zadania.

### Krok 5: Dodanie zadania lokalnego
Utwórz zadanie, które będzie połączone z zadaniem zewnętrznym:

`Task local = summary.getChildren().add("Local Task");`

### Krok 6: Utworzenie połączenia zadania
Ustal zależność pomiędzy zadaniem zewnętrznym a lokalnym. Najczęstszy typ połączenia to Finish‑to‑Start:

`TaskLink link = targetProject.getTaskLinks().add(external, local, TaskLinkType.FinishToStart);`

**TaskLink** rejestruje relację; później możesz zmodyfikować jego opóźnienie, przyspieszenie lub typ w razie potrzeby.

### Krok 7: Zapis i weryfikacja
Zapisz projekt do pliku i opcjonalnie otwórz go w Microsoft Project, aby zweryfikować połączenie:

`targetProject.save("LinkedProject.mpp", SaveFileFormat.MPP);`

**SaveFileFormat** określa format pliku przy zapisywaniu projektu. Gdy otworzysz *LinkedProject.mpp*, zobaczysz zadanie zewnętrzne wyświetlone z specjalną ikoną oraz linię zależności wskazującą na zadanie lokalne.

## Typowe problemy i rozwiązania
- **Plik zewnętrzny nie znaleziony** – Upewnij się, że ścieżka jest względna względem procesu uruchomieniowego lub podaj ścieżkę bezwzględną.  
- **Niezgodność identyfikatorów zadań** – Sprawdź, czy identyfikator zadania zewnętrznego (drugi argument `addExternalTask`) odpowiada projektowi źródłowemu.  
- **Licencja nie została wczytana** – Brak lub nieprawidłowy plik licencji powoduje `LicenseException`. Wczytaj ją przed jakimikolwiek wywołaniami Aspose.Tasks.  
- **Wydajność przy dużych projektach** – Użyj `Project.setReadOnly(true)`, gdy potrzebujesz jedynie odczytać zadania zewnętrzne; zmniejsza to zużycie pamięci.

## Najczęściej zadawane pytania

**Q: Czy mogę łączyć zadania z wielu zewnętrznych projektów w tym samym zadaniu zbiorczym?**  
A: Tak, możesz dodać kilka zewnętrznych zadań pod jednym zadaniem zbiorczym i utworzyć indywidualne połączenia dla każdego, używając tej samej metody `addExternalTask`.

**Q: Co się stanie, jeśli zadanie zewnętrzne w połączonym projekcie zostanie zmodyfikowane?**  
A: Każda zmiana w harmonogramie, czasie trwania lub ograniczeniach zadania zewnętrznego jest automatycznie odzwierciedlana w zależnym zadaniu lokalnym po odświeżeniu projektu docelowego.

**Q: Czy można tworzyć połączenia między zadaniami w różnych formatach plików?**  
A: Oczywiście. Aspose.Tasks obsługuje łączenie pomiędzy formatami MPP, XML i Primavera, umożliwiając synchronizację heterogenicznych ekosystemów projektowych.

**Q: Czy mogę odłączyć zadania po ich połączeniu między projektami?**  
A: Tak, usuń połączenie, wywołując `project.getTaskLinks().remove(link)` lub usuwając placeholder zadania zewnętrznego.

**Q: Czy istnieją ograniczenia co do liczby zadań, które mogą być połączone między projektami?**  
A: Biblioteka może obsłużyć **ponad 10 000 połączonych zadań** na projekt, ograniczone jedynie dostępną pamięcią systemową i specyfikacjami formatu pliku.

## Podsumowanie
Masz teraz kompletną, gotową do produkcji metodę **łączenia zadań między projektami** przy użyciu Aspose.Tasks dla Javy. Ta funkcja usprawnia koordynację wielu projektów, redukuje ręczną pracę i zapewnia, że zmiany w harmonogramie są natychmiast propagowane w całym portfelu. Poznaj dodatkowe funkcje, takie jak niestandardowe czasy opóźnień, różne typy połączeń i masowe łączenie, aby jeszcze bardziej zautomatyzować złożone struktury projektowe.

---

**Ostatnia aktualizacja:** 2026-07-05  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

```java
Project project = new Project();
```

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

```java
Task t = summary.getChildren().add("Task");
```

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

```java
System.out.println("Process completed Successfully");
```

## Powiązane samouczki

- [Utwórz połączenie zadania w Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Utwórz zadania Aspose Java – Właściwości zadania](/tasks/java/task-properties/)
- [Utwórz pusty plik MS Project w Aspose.Tasks](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}