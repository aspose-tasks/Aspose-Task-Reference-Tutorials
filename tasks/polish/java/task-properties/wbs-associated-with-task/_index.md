---
title: WBS powiązany z zadaniem w Aspose.Tasks
linktitle: WBS powiązany z zadaniem w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Opanuj WBS z Aspose.Tasks dla Java - Naucz się czytać i przenumerowywać kody WBS zadań. Zwiększ efektywność zarządzania projektami!
weight: 36
url: /pl/java/task-properties/wbs-associated-with-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# WBS powiązany z zadaniem w Aspose.Tasks

## Wstęp
Witamy w świecie zarządzania projektami z Aspose.Tasks dla Java! W tym samouczku zagłębimy się w zawiłości struktury podziału pracy (WBS) związanej z zadaniami przy użyciu Aspose.Tasks dla Java. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik pomoże Ci poruszać się po podstawach efektywnego zarządzania kodami WBS.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Biblioteka Aspose.Tasks dla Java pobrana i dodana do Twojego projektu. Możesz to dostać od[Tutaj](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Upewnij się, że zaimportowałeś niezbędne pakiety, aby rozpocząć projekt:
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## Przeczytaj kody WBS
Zacznijmy od odczytania kodów WBS powiązanych z zadaniami. Wykonaj następujące kroki:
## Krok 1: Załaduj projekt
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## Krok 2: Zbierz zadania
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## Krok 3: Przeanalizuj i dostosuj
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
Ten fragment kodu odczytuje i dostosowuje kody WBS powiązane z zadaniami w Twoim projekcie.
## Zmień numerację kodów SPP zadań
Przyjrzyjmy się teraz zmianie numeracji kodów WBS dla zadań:
## Krok 1: Załaduj projekt
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## Krok 2: Wybierz Wszystkie zadania
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## Krok 3: Wyprowadź początkowe kody WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## Krok 4: Zmień numerację kodów WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## Krok 5: Wyprowadź zaktualizowane kody WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
Wykonując poniższe kroki, skutecznie przenumerujesz kody SPP dla zadań w swoim projekcie.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się pracować z kodami WBS przy użyciu Aspose.Tasks dla Java. Ta wiedza umożliwi Ci efektywne zarządzanie i dostosowywanie hierarchii zadań w projekcie.
## Często zadawane pytania
### P: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla Java?
 Odp.: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/tasks/java/).
### P: Jak mogę pobrać Aspose.Tasks dla Java?
 O: Możesz to pobrać[Tutaj](https://releases.aspose.com/tasks/java/).
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) dla wsparcia.
### P: Czy mogę uzyskać tymczasową licencję na Aspose.Tasks dla Java?
 Odp.: Tak, zdobądź licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
