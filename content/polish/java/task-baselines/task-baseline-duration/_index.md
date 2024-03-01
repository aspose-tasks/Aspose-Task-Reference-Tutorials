---
title: Zarządzanie czasem trwania zadania w Aspose.Tasks
linktitle: Zarządzanie czasem trwania zadania w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak efektywnie zarządzać bazami zadań w MS Project przy użyciu Aspose.Tasks dla Java. Ten samouczek przeprowadzi Cię krok po kroku przez cały proces.
type: docs
weight: 12
url: /pl/java/task-baselines/task-baseline-duration/
---
## Wstęp
Zarządzanie bazami zadań w MS Project ma kluczowe znaczenie dla planowania i śledzenia projektów. W tym samouczku dowiemy się, jak efektywnie zarządzać czasem trwania zadań przy użyciu Aspose.Tasks dla języka Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK).
2.  Biblioteka Aspose.Tasks: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla Java z[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety dla swojego projektu Java:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## Krok 1: Utwórz instancję projektu
Zainicjuj nową instancję projektu, używając następującego kodu:
```java
Project project = new Project();
```
## Krok 2: Utwórz plan bazowy zadania
Utwórz nowe zadanie i ustaw jego linię bazową za pomocą następującego kodu:
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## Krok 3: Wyświetl informacje o planie podstawowym zadania
Pobieraj i wyświetlaj informacje o planie podstawowym zadania, takie jak czas trwania, data rozpoczęcia, data zakończenia i inne:
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## Krok 4: Sprawdź tymczasową linię bazową i koszt stały
Sprawdź, czy poziom bazowy jest przejściowym poziomem bazowym i pobierz wszelkie powiązane z nim koszty stałe:
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## Krok 5: Wydrukuj dane okresowe
Drukuj dane okresowe powiązane z planem bazowym zadania:
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
Wykonując te kroki, możesz efektywnie zarządzać czasem trwania zadań w programie MS Project przy użyciu Aspose.Tasks for Java.

## Wniosek
Zarządzanie bazami zadań jest niezbędne w zarządzaniu projektami, pozwala na śledzenie odchyleń od zaplanowanego harmonogramu. Dzięki Aspose.Tasks dla Java proces ten staje się usprawniony i wydajny, umożliwiając lepszą kontrolę i realizację projektu.
## Często zadawane pytania
### Co to jest baza zadań w MS Project?
Plan bazowy zadania w MS Project to migawka początkowo zaplanowanego harmonogramu zadania, w tym jego data rozpoczęcia, data zakończenia i czas trwania.
### Dlaczego zarządzanie bazami zadań jest ważne?
Zarządzanie bazami zadań pomaga w porównaniu zaplanowanego harmonogramu z rzeczywistym postępem projektu, ułatwiając lepsze śledzenie i podejmowanie decyzji.
### Czy mogę zmodyfikować plan bazowy zadania po jego ustawieniu?
Tak, możesz modyfikować plany bazowe zadań w MS Project, aby odzwierciedlić zmiany w planie projektu. Jednakże istotne jest udokumentowanie wszelkich odchyleń od pierwotnej wartości bazowej.
### Czy Aspose.Tasks obsługuje inne funkcje zarządzania projektami?
Tak, Aspose.Tasks oferuje szeroką gamę funkcji do zarządzania projektami, w tym planowanie zadań, alokację zasobów i generowanie wykresów Gantta.
### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?
 Wsparcie dla Aspose.Tasks znajdziesz na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i kontaktować się z innymi użytkownikami.