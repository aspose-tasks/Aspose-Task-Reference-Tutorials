---
title: Obsługuj właściwości opóźnienia poziomowania w Aspose.Tasks
linktitle: Obsługuj właściwości opóźnienia poziomowania dla przypisań zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak obsługiwać właściwości opóźnienia poziomowania dla przydziałów zasobów w Aspose.Tasks dla Java, korzystając z tego wszechstronnego samouczka.
type: docs
weight: 17
url: /pl/java/resource-assignments/leveling-delay-properties/
---
## Wstęp
W tym samouczku omówimy proces obsługi właściwości opóźnienia poziomowania dla przydziałów zasobów w Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project w systemie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie zainstalowano pakiet Java JDK. Można go pobrać i zainstalować ze strony[strona internetowa](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Biblioteka Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z witryny[strona pobierania](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do swojego projektu Java, aby móc korzystać z funkcjonalności Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Utwórz obiekt projektu
 Utwórz instancję a`Project` obiekt:
```java
Project prj = new Project();
```
## Krok 2: Utwórz zadanie
Dodaj zadanie do projektu:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## Krok 3: Ustaw datę rozpoczęcia i czas trwania zadania
Ustaw datę rozpoczęcia i czas trwania zadania:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## Krok 4: Dodaj zasób
Dodaj zasób do projektu:
```java
Resource resource = prj.getResources().add("Resource 1");
```
## Krok 5: Utwórz przydział zasobów
Utwórz przypisanie zasobu dla zadania i zasobu:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## Krok 6: Ustaw opóźnienie poziomowania
Ustaw opóźnienie poziomowania dla zadania:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## Krok 7: Wyświetl wyniki
Wydrukuj opóźnienie poziomowania i inne istotne informacje:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Wniosek
W tym samouczku nauczyliśmy się obsługiwać właściwości opóźnienia poziomowania dla przydziałów zasobów w Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie zarządzać przypisaniami zasobów w projektach Java.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi bibliotekami Java?

O: Tak, Aspose.Tasks można zintegrować z innymi bibliotekami Java w celu zwiększenia możliwości zarządzania projektami.

### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?

O: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks?

 O: Wsparcie i zasoby znajdziesz na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?

 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks ze strony[strona z wydaniami](https://releases.aspose.com/).

### P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?

 Odpowiedź: Możesz poprosić o licencję tymczasową od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.