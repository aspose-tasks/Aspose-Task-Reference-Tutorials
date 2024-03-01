---
title: Zaktualizuj dane zadania do formatu MPP w Aspose.Tasks
linktitle: Zaktualizuj dane zadania do formatu MPP w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zaktualizować dane zadania do formatu MPP przy użyciu Aspose.Tasks dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie zarządzać projektami.
type: docs
weight: 35
url: /pl/java/task-properties/update-task-data/
---
## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym aktualizacji danych zadań do formatu MPP przy użyciu Aspose.Tasks dla Java. W tym samouczku przeprowadzimy Cię przez proces, upewniając się, że rozumiesz każdy krok w sposób jasny. Aspose.Tasks dla Java zapewnia solidne rozwiązanie do pracy z plikami Microsoft Project, a pod koniec tego przewodnika będziesz mógł efektywnie aktualizować dane zadań w formacie MPP.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Tasks dla Java: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Tasks. Można go pobrać z[strona wydania](https://releases.aspose.com/tasks/java/).
- Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java.
- Zintegrowane środowisko programistyczne (IDE): Użyj wybranego IDE do programowania w języku Java.
## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów do projektu Java. Poniższy fragment demonstruje, jak importować pakiety:
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. Utwórz i skonfiguruj zadanie początkowe
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//... (Kontynuuj resztę kodu)
```
## 2. Ustaw datę rozpoczęcia i czas trwania
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//... (Kontynuuj resztę kodu)
```
## 3. Utwórz zadanie podsumowujące
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//... (Kontynuuj resztę kodu)
```
## 4. Ustaw termin ostateczny i uwagi do zadania
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//... (Kontynuuj resztę kodu)
```
## 5. Skonfiguruj ograniczenia zadań
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//... (Kontynuuj resztę kodu)
```
## 6. Utwórz dodatkowe zadania
```java
//Utwórz 10 nowych zadań
for (int i = 0; i < 10; i++) {
    //... (Kontynuuj resztę kodu)
}
//... (Kontynuuj resztę kodu)
```
## 7. Zapisz projekt
```java
// Zapisz projekt
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
Wykonując poniższe kroki, pomyślnie zaktualizowałeś dane zadania do formatu MPP przy użyciu Aspose.Tasks dla Java.
## Wniosek
Gratulacje! Ukończyłeś obszerny przewodnik na temat aktualizacji danych zadań w formacie MPP przy użyciu Aspose.Tasks dla Java. Ta potężna biblioteka upraszcza zadania związane z zarządzaniem projektami, dzięki czemu jest cennym narzędziem dla programistów Java.
## Często zadawane pytania
### P: Gdzie mogę znaleźć dokumentację Aspose.Tasks dla Java?
 Odp.: Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/tasks/java/).
### P: Jak mogę pobrać Aspose.Tasks dla Java?
 O: Możesz pobrać go z[strona wydania](https://releases.aspose.com/tasks/java/).
### P: Czy dostępny jest bezpłatny okres próbny?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
 O: Odwiedź forum wsparcia[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy oferujecie licencje tymczasowe do celów testowych?
 Odpowiedź: Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).