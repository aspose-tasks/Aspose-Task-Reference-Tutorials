---
date: 2026-08-29
description: Dowiedz się, jak ustawić link types i zarządzać task dependencies w Aspose.Tasks
  for Java w samouczku krok po kroku.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Jak ustawić link types w Aspose.Tasks for Java
og_description: Dowiedz się, jak ustawić link types i zarządzać task dependencies
  w Aspose.Tasks for Java. Przewodnik krok po kroku dla programistów.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Jak ustawić link types w Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Jak ustawić link types w Aspose.Tasks for Java
url: /pl/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić typy połączeń w Aspose.Tasks dla Javy

## Wprowadzenie
Jeśli zastanawiasz się **jak ustawić połączenie** między zadaniami, podczas *zarządzania zależnościami zadań* w projekcie, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez tworzenie nowego projektu, dodawanie zadań i definiowanie typu połączenia (Start‑to‑Start, Finish‑to‑Start, itp.) przy użyciu Aspose.Tasks dla Javy. Po zakończeniu będziesz pewny, jak dostosować relacje zadań do rzeczywistych potrzeb harmonogramowania i zobaczysz, jak API obsługuje plany na dużą skalę z aż do 10 000 zadań.

## Szybkie odpowiedzi
- **Jaka klasa reprezentuje zależność?** `TaskLink` jest podstawowym obiektem modelującym połączenie między dwoma zadaniami.  
- **Które wyliczenie definiuje typ relacji?** `TaskLinkType` (np. `StartToStart`, `FinishToStart`).  
- **Czy mogę odczytać istniejące typy połączeń?** Tak – iteruj `Project.getTaskLinks()` i wywołaj `getLinkType()`.  
- **Czy potrzebuję licencji na ten kod?** Tymczasowa licencja działa w testach; pełna licencja jest wymagana w produkcji.  
- **Czy jest to kompatybilne z Java 8+?** Absolutnie – Aspose.Tasks obsługuje Java 8 aż do Java 21, obejmując 13 głównych wydań.

## Co to jest połączenie zadania?
**task link** modeluje zależność między dwoma zadaniami w harmonogramie projektu.  
Możesz tworzyć, modyfikować lub usuwać `TaskLink`, aby odzwierciedlić relacje poprzednik‑następca, umożliwiając harmonogramowi automatyczne obliczanie dat rozpoczęcia i zakończenia.

## Dlaczego używać typów połączeń w Aspose.Tasks?
Aspose.Tasks obsługuje **ponad 30 formatów wejścia i wyjścia** i może przetwarzać projekty zawierające **do 10 000 zadań** bez ładowania całego pliku do pamięci. Ta zmierzona zdolność zapewnia wysoką wydajność nawet w planach o skali przedsiębiorstwa, a biblioteka zachowuje wszystkie funkcje Microsoft Project, takie jak pola niestandardowe i przydziały zasobów.

## Wymagania wstępne
- **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8 lub nowszy.  
- **Biblioteka Aspose.Tasks** – Pobierz najnowszy plik JAR z [download link](https://releases.aspose.com/tasks/java/).  
- **Katalog dokumentów** – Utwórz folder na swoim komputerze, w którym będziesz przechowywać pliki przykładowego projektu.

## Importowanie pakietów
Zaczynamy od importowania niezbędnych klas Aspose.Tasks. To przygotowuje IDE do rozpoznawania wywołań API, które będziemy używać później.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Jak ustawić typy połączeń w Aspose.Tasks dla Javy?
Załaduj nową instancję `Project`, dodaj dwa zadania, a następnie utwórz `TaskLink` z żądanym `TaskLinkType`. Ten dwustopniowy wzorzec pozwala zdefiniować dowolny z czterech standardowych typów zależności w jednym wywołaniu. `Project` reprezentuje cały plik projektu i jego harmonogram. `Task` jest pojedynczym elementem pracy w projekcie. `TaskLink` łączy zadanie poprzednika z zadaniem następnika. `TaskLinkType` to wyliczenie określające relację (Start‑to‑Start, Finish‑to‑Start itp.).

### Krok 1: ustawianie typu połączenia
`TaskLink` reprezentuje zależność między dwoma zadaniami, podczas gdy `TaskLinkType` wylicza możliwe typy relacji, takie jak `StartToStart`. W tym kroku tworzymy nowy projekt, dodajemy dwa zadania i łączymy je przy użyciu relacji **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Porada:** Możesz zamienić `StartToStart` na `FinishToStart`, `StartToFinish` lub `FinishToFinish` w zależności od zależności, którą musisz **zarządzać zależnościami zadań**.

### Krok 2: odczytywanie typu połączenia
`Project.getTaskLinks()` zwraca kolekcję wszystkich obiektów `TaskLink` w harmonogramie. Iterując tę kolekcję, możesz odczytać `TaskLinkType` każdego połączenia i zweryfikować, że prawidłowa relacja została zachowana.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Konsola wyświetli wartości takie jak `StartToStart`, `FinishToStart` itp., potwierdzając typ połączenia, który wcześniej ustawiłeś.

## Typowe problemy i rozwiązania
- **NullPointerException przy dodawaniu połączeń** – Upewnij się, że zarówno zadanie poprzednika, jak i następnika zostały dodane do projektu przed utworzeniem `TaskLink`.  
- **Nieprawidłowy typ połączenia po zapisaniu** – Zawsze wywołuj `project.save("output.mpp")` (lub inny obsługiwany format) po ustawieniu typu połączenia, aby zachować zmiany.  
- **Nie znaleziono licencji** – Umieść plik licencji Aspose.Tasks w classpath projektu i załaduj go za pomocą `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks jest kompatybilny z różnymi środowiskami Java?**  
O: Tak, Aspose.Tasks integruje się ze standardowymi Java SE, Java EE oraz zestawami SDK Android bez dodatkowych zależności.

**P: Czy mogę dostosować typy połączeń do wymagań mojego projektu?**  
O: Absolutnie. Wyliczenie `TaskLinkType` oferuje cztery standardowe typy, a możesz je łączyć z wartościami opóźnień, aby modelować złożone harmonogramy.

**P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks dla Javy?**  
O: Odwołaj się do [dokumentacji Aspose.Tasks dla Java](https://reference.aspose.com/tasks/java/) po szczegółowe wskazówki, referencję API i przykłady kodu.

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?**  
O: Odwiedź [stronę tymczasowej licencji](https://purchase.aspose.com/temporary-license/), aby uzyskać tymczasową licencję do testów.

**P: Gdzie mogę uzyskać wsparcie w kwestiach związanych z Aspose.Tasks?**  
O: Dołącz do społeczności Aspose.Tasks na [forum wsparcia](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc i dyskusje.

**P: Czy mogę zmienić typ połączenia po zapisaniu projektu?**  
O: Tak. Załaduj projekt, pobierz `TaskLink`, wywołaj `setLinkType()` z nową wartością wyliczenia i ponownie zapisz projekt.

**P: Czy Aspose.Tasks obsługuje odczyt plików Microsoft Project (MPP)?**  
O: Tak. Użyj `new Project("file.mpp")`, aby wczytać pliki MPP i pracować z ich połączeniami zadań tak jak w powyższym przykładzie XML.

---

**Ostatnia aktualizacja:** 2026-08-29  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz połączenie zadania między projektami w Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Ustaw datę rozpoczęcia projektu i zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Wczytaj plik MPP w Javie – zarządzaj właściwościami projektu przy użyciu Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}