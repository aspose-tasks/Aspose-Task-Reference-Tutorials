---
date: 2026-06-25
description: Dowiedz się, jak dodać zadanie i zaktualizować pliki MPP przy użyciu
  Aspose.Tasks for Java, biblioteki zarządzania projektami w Javie, która umożliwia
  tworzenie plików Microsoft Project oraz zapisywanie projektu jako MPP.
keywords:
- how to add task
- create task microsoft project
- java project management library
- save project as mpp
linktitle: Jak dodać zadanie i zaktualizować plik MPP w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  headline: How to Add Task and Update MPP File in Aspose.Tasks
  type: TechArticle
- description: Learn how to add task and update MPP files using Aspose.Tasks for Java,
    a java project management library that lets you create task Microsoft Project
    files and save project as MPP.
  name: How to Add Task and Update MPP File in Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – Download from the [download page](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
    text: '**Basic Java knowledge** – Familiarity with classes, objects, and date
      handling.'
  type: HowTo
- questions:
  - answer: Loop over a collection of task names and repeat the “create task” block
      inside the loop.
    question: How do I add multiple tasks at once?
  - answer: Yes—use `task.set(Tsk.CUSTOM_FIELD_x, value)` where *x* is the field index.
    question: Can I set custom fields for the new task?
  - answer: Clone the source task (`Task cloned = sourceTask.clone();`) and then add
      it to the desired parent.
    question: Is it possible to copy an existing task as a template?
  - answer: Retrieve the task by ID (`Task existing = project.getRootTask().getChildren().getById(id);`)
      and modify its properties.
    question: What if I need to update an existing task instead of adding a new one?
  - answer: Yes—use `project.save("output.pdf", SaveFileFormat.Pdf);` or `SaveFileFormat.Png`
      for visual representations.
    question: Does Aspose.Tasks support saving to other formats like PDF or PNG?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak dodać zadanie i zaktualizować plik MPP w Aspose.Tasks
url: /pl/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać zadanie i zaktualizować plik MPP w Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się **jak dodać zadanie** do istniejącego pliku Microsoft Project (MPP) i następnie zapisać zaktualizowany harmonogram przy użyciu Aspose.Tasks for Java, wiodącej **biblioteki zarządzania projektami w języku Java**. Niezależnie od tego, czy tworzysz własny harmonogram, automatyzujesz masowe aktualizacje, czy integrujesz dane projektowe z większym systemem, poniższy przewodnik krok po kroku pokazuje dokładnie, jak wczytać projekt, wstawić nowe zadanie, ustawić jego daty i zachować wynik jako nowy dokument MPP.

## Szybkie odpowiedzi
- **Co oznacza „how to add task” w tym kontekście?** Oznacza to programowe tworzenie nowego elementu pracy w istniejącym pliku MPP.  
- **Która biblioteka obsługuje tę operację?** Aspose.Tasks for Java, solidna biblioteka zarządzania projektami w języku Java.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zapisać wynik jako MPP?** Tak — użyj `project.save(..., SaveFileFormat.Mpp)`, aby **zapisać projekt jako mpp**.  
- **Jaka wersja Java jest wymagana?** Java 8 lub nowsza.

## Co oznacza „how to add task” w pliku MPP?
Dodanie zadania oznacza wstawienie nowego elementu pracy do hierarchii projektu, określenie jego dat rozpoczęcia i zakończenia oraz zapisanie zmiany z powrotem do pliku MPP. Aspose.Tasks abstrahuje szczegóły niskopoziomowego formatu pliku, pozwalając skupić się na logice biznesowej, jednocześnie automatycznie obsługując przydziały zasobów, kalendarze i obliczenia zależności. Aktualizuje także powiązane przydziały i przelicza harmonogram projektu, aby utrzymać spójność między zależnymi zadaniami.

## Dlaczego używać Aspose.Tasks for Java?
- **Pełna kompatybilność**: Obsługuje 100 % funkcji w Microsoft Project 2007‑2021 (ponad 150 typów zadań i 200 pól zasobów).  
- **Zero zależności**: Nie wymaga COM, Office ani natywnych bibliotek — czyste API Java działa wszędzie tam, gdzie działa JRE.  
- **Bogaty zestaw funkcji**: Zawiera łączenie zadań, przydzielanie zasobów, pola niestandardowe i wbudowane raportowanie.  
- **Wysoka wydajność**: Przetwarza projekty z do 10 000 zadań, używając mniej niż 200 MB RAM, co czyni go idealnym do automatyzacji po stronie serwera.

## Wymagania wstępne
1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8+.  
2. **Aspose.Tasks for Java** – Pobierz ze [strony pobierania](https://releases.aspose.com/tasks/java/).  
3. **Podstawowa znajomość Java** – Znajomość klas, obiektów i obsługi dat.  

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy. Dzięki temu uzyskasz dostęp do manipulacji projektem, właściwości zadań i obsługi dat.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```  
`Project` reprezentuje plik Microsoft Project załadowany w pamięci. `SaveFileFormat` wymienia formaty, do których możesz zapisać, takie jak MPP lub PDF. `Task` modeluje pojedynczy element pracy w hierarchii projektu. `Tsk` udostępnia stałe dla pól zadania używanych przy ustawianiu lub pobieraniu wartości. `Calendar` oferuje narzędzia dat‑czasowych do definiowania harmonogramów.

## Krok 1: Zdefiniuj katalog danych
```java
String dataDir = "Your Data Directory";
```  
Zastąp `"Your Data Directory"` absolutną ścieżką, w której znajduje się Twój źródłowy plik MPP.

## Krok 2: Odczytaj istniejący projekt
Klasa `Project` jest podstawowym obiektem Aspose.Tasks, który reprezentuje plik Microsoft Project w pamięci.  
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```  
Konstruktor wczytuje **SampleMSP2010.mpp**, dając Ci w pełni manipulowalny model obiektowy.

## Krok 3: Utwórz nowe zadanie (how to add task)
Klasa `Task` reprezentuje pojedynczy element pracy w hierarchii projektu.  
```java
Task task = project.getRootTask().getChildren().add("Task1");
```  
Ten wiersz **creates task in mpp** poprzez dodanie dziecka o nazwie *Task1* do zadania głównego.

## Krok 4: Ustaw daty rozpoczęcia i zakończenia
Klasa `Calendar` zapewnia narzędzia dat‑czasowe; miesiące są indeksowane od zera (np. `Calendar.JULY`).  
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```  
Tutaj definiujemy harmonogram nowo dodanego zadania. Dostosuj daty, aby pasowały do Twojego harmonogramu projektu.

## Krok 5: Zapisz projekt (save project as mpp)
`SaveFileFormat.Mpp` instruuje Aspose.Tasks, aby zapisał plik w natywnym formacie Microsoft Project.  
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```  
Zaktualizowany projekt, zawierający teraz nowe zadanie, zostaje zapisany jako **AfterLinking.mpp**.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Plik nie znaleziony** | Sprawdź, czy `dataDir` kończy się separatorem ścieżki (`/` lub `\\`) i czy nazwa pliku jest poprawna. |
| **Nieprawidłowe daty** | Pamiętaj, że miesiące w `Calendar` są zerowane; `Calendar.JULY` jest poprawny dla lipca. |
| **Wyjątek licencyjny** | Zainstaluj ważną licencję Aspose.Tasks przed wywołaniem jakiegokolwiek API, aby uniknąć znaków wodnych wersji ewaluacyjnej. |

## Najczęściej zadawane pytania
**Q: Jak dodać wiele zadań jednocześnie?**  
A: Przejdź pętlą po kolekcji nazw zadań i powtórz blok „create task” wewnątrz pętli.

**Q: Czy mogę ustawić pola niestandardowe dla nowego zadania?**  
A: Tak — użyj `task.set(Tsk.CUSTOM_FIELD_x, value)`, gdzie *x* jest indeksem pola.

**Q: Czy można skopiować istniejące zadanie jako szablon?**  
A: Sklonuj zadanie źródłowe (`Task cloned = sourceTask.clone();`), a następnie dodaj je do wybranego rodzica.

**Q: Co zrobić, jeśli muszę zaktualizować istniejące zadanie zamiast dodawać nowe?**  
A: Pobierz zadanie po ID (`Task existing = project.getRootTask().getChildren().getById(id);`) i zmodyfikuj jego właściwości.

**Q: Czy Aspose.Tasks obsługuje zapisywanie do innych formatów, takich jak PDF lub PNG?**  
A: Tak — użyj `project.save("output.pdf", SaveFileFormat.Pdf);` lub `SaveFileFormat.Png` dla reprezentacji wizualnych.

---

**Ostatnia aktualizacja:** 2026-06-25  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć plik MPP – Utwórz i zapisz pusty projekt w formacie MPP przy użyciu Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Jak utworzyć projekt – Ustaw nowe atrybuty zadania przy użyciu Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Utwórz listę zadań w Java – Podstawę projektu MS przy użyciu Aspose.Tasks](/tasks/java/task-baselines/create-task-baseline/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}