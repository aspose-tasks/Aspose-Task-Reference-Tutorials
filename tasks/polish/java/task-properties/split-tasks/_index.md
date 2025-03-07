---
title: Podziel zadania w Aspose.Tasks
linktitle: Podziel zadania w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Opanuj zarządzanie zadaniami w Javie dzięki Aspose.Tasks! Dowiedz się, jak efektywnie dzielić zadania, aby uzyskać zoptymalizowane ramy czasowe projektu. Pobierz teraz!
weight: 29
url: /pl/java/task-properties/split-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Podziel zadania w Aspose.Tasks

## Wstęp
Czy masz problemy z zarządzaniem zadaniami w swoim projekcie Java? Aspose.Tasks dla Java zapewnia potężne rozwiązanie do efektywnego dzielenia zadań, zwiększając możliwości zarządzania projektami. W tym samouczku przeprowadzimy Cię przez proces dzielenia zadań za pomocą Aspose.Tasks dla Java, pomagając zoptymalizować ramy czasowe projektu i alokację zasobów.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Biblioteka Aspose.Tasks dla Java pobrana i dodana do Twojego projektu. Można go pobrać z[Aspose.Tasks dla dokumentacji Java](https://reference.aspose.com/tasks/java/).
## Importuj pakiety
Rozpocznij od zaimportowania niezbędnych pakietów do projektu Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```
## Krok 1: Utwórz nowy projekt
Zacznij od utworzenia nowego projektu przy użyciu biblioteki Aspose.Tasks:
```java
// Utwórz nowy projekt
Project splitTaskProject = new Project();
```
## Krok 2: Ustaw kalendarz projektu
Skonfiguruj ustawienia kalendarza projektu, aby ustalić oś czasu:
```java
// Zdobądź standardowy kalendarz
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Skonfiguruj ustawienia kalendarza projektu
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (kontynuuj przykład)
```
## Krok 3: Dodaj zadanie root
Dodaj zadanie główne do swojego projektu:
```java
// Zadanie roota
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```
## Krok 4: Dodaj nowe zadanie do podziału
Dodaj nowe zadanie do swojego projektu, które chcesz podzielić:
```java
// Dodaj nowe zadanie
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```
## Krok 5: Utwórz przydział zasobów
Utwórz nowe przypisanie zasobu dla zadania:
```java
// Utwórz nowe przypisanie zasobu
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```
## Krok 6: Wygeneruj dane okresowe
Generuj dane okresowe przydziału zasobów:
```java
// Generuj dane okresowe przydziału zasobów
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```
## Krok 7: Podziel zadanie
Podziel zadanie na kilka części:
```java
// Podziel zadanie na 3 części
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (kontynuuj przykład)
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dzielić zadania za pomocą Aspose.Tasks dla Java. Ta potężna biblioteka upraszcza zarządzanie zadaniami w projektach Java, zapewniając wydajne rozwiązania do optymalizacji harmonogramu projektów i alokacji zasobów.
## Często Zadawane Pytania
### Czy mogę dzielić zadania o różnym czasie trwania?
Tak, możesz dostosować czas trwania zadań do wymagań swojego projektu.
### Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami Java?
Aspose.Tasks dla Java został zaprojektowany tak, aby bezproblemowo współpracować z różnymi wersjami Java, zapewniając kompatybilność.
### Czy mogę używać Aspose.Tasks dla Java za darmo?
Aspose.Tasks dla Java oferuje bezpłatną wersję próbną, umożliwiającą zapoznanie się z jego funkcjami przed dokonaniem zakupu.
### Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Java?
 Odwiedzić[Aspose.Tasks dla forum pomocy technicznej Java](https://forum.aspose.com/c/tasks/15) aby uzyskać pomoc i nawiązać kontakt ze społecznością.
### Czy potrzebuję tymczasowej licencji na Aspose.Tasks dla Java?
 Licencję tymczasową można uzyskać od[ten link](https://purchase.aspose.com/temporary-license/) do celów testowania i oceny.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
