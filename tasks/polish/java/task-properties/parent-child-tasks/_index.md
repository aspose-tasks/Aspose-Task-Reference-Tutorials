---
title: Zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks
linktitle: Zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Zwiększ efektywność zarządzania projektami dzięki Aspose.Tasks dla Java. Dowiedz się, jak krok po kroku zarządzać zadaniami rodziców i dzieci. Zacznij teraz!
weight: 24
url: /pl/java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks

## Wstęp
W zarządzaniu projektami kluczowa jest efektywna organizacja zadań. Aspose.Tasks dla Java zapewnia solidne rozwiązanie do efektywnego zarządzania zadaniami nadrzędnymi i podrzędnymi. W tym samouczku przeprowadzimy Cię przez proces używania Aspose.Tasks dla Java w celu usprawnienia zadań projektowych.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Tasks dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/java/).
- Zintegrowane środowisko programistyczne Java (IDE) skonfigurowane w systemie.
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Pakiety te ułatwiają bezproblemową integrację z funkcjonalnościami Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```
## Krok 1: Ustaw datę rozpoczęcia projektu
Zacznij od ustalenia daty rozpoczęcia projektu i innych istotnych parametrów.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Tutaj można dodać dodatkowy kod dla importu pakietów
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```
## Krok 2: Dodaj zadanie nadrzędne (zadanie 1)
Utwórz zadanie nadrzędne o nazwie „Zadanie 1” i skonfiguruj jego właściwości.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```
## Krok 3: Dodaj zadanie nadrzędne (zadanie 2) do zadań podrzędnych
Teraz dodaj kolejne zadanie nadrzędne o nazwie „Zadanie 2” i uwzględnij zadania podrzędne (Zadanie 3 i Zadanie 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Dodaj zadania podrzędne do Zadania 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Tutaj można dodać dodatkową konfigurację dla Zadania 3 i Zadania 4
```
## Krok 4: Skonfiguruj zadania podrzędne
Określ daty rozpoczęcia, czas trwania i ograniczenia dla Zadania 3 i Zadania 4.
```java
// Skonfiguruj zadanie 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Skonfiguruj zadanie 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```
## Krok 5: Zaktualizuj procent wykonania zadania
Dostosuj procent ukończenia zadania 3 i zadania 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Krok 6: Zapisz projekt
Na koniec zapisz projekt z zastosowanymi zmianami.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
Ten przewodnik krok po kroku pokazuje, jak skutecznie zarządzać zadaniami nadrzędnymi i podrzędnymi za pomocą Aspose.Tasks dla Java. Eksperymentuj z różnymi konfiguracjami, aby dopasować je do wymagań swojego projektu.
## Wniosek
Podsumowując, Aspose.Tasks dla Java umożliwia programistom efektywną realizację zadań projektowych, zapewniając bezproblemową organizację i śledzenie. Wykonaj opisane kroki, aby zwiększyć możliwości zarządzania projektami.
## Często zadawane pytania
### Czy Aspose.Tasks for Java jest kompatybilny z różnymi formatami plików projektów?
Tak, Aspose.Tasks for Java obsługuje różne formaty plików projektów, w tym MPP i XML.
### Czy mogę dostosować właściwości zadania poza tym, co opisano w tym samouczku?
Absolutnie! Aspose.Tasks dla Java zapewnia rozbudowane opcje dostosowywania właściwości zadań.
### Czy istnieje forum społecznościowe dla Aspose.Tasks, na którym mogę szukać pomocy?
 Tak, możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności.
### Jak mogę uzyskać tymczasową licencję na Aspose.Tasks dla Java?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć obszerną dokumentację Aspose.Tasks dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
