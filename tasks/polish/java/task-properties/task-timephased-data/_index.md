---
title: Dane okresowe zadania w Aspose.Tasks
linktitle: Dane okresowe zadania w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Poznaj Aspose.Tasks dla Java i okresowe zarządzanie danymi w ramach zadań głównych. Pobierz bibliotekę, skorzystaj z bezpłatnego okresu próbnego i usprawnij śledzenie projektów.
weight: 34
url: /pl/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dane okresowe zadania w Aspose.Tasks

## Wstęp
dziedzinie zarządzania projektami precyzyjne śledzenie danych okresowych zadań ma kluczowe znaczenie dla wydajnej realizacji projektu. Aspose.Tasks dla Java jawi się jako potężne narzędzie usprawniające ten proces, oferujące solidne funkcje i elastyczność. Ten samouczek poprowadzi Cię przez wykorzystanie Aspose.Tasks dla Java do efektywnego zarządzania danymi okresowymi zadań.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Środowisko programistyczne Java: Upewnij się, że masz zainstalowaną Javę w swoim systemie.
-  Aspose.Tasks dla biblioteki Java: Pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/tasks/java/).
- Katalog dokumentów: skonfiguruj katalog dla dokumentów projektu.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety dla Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## Krok 1: Ustaw datę rozpoczęcia projektu
```java
Project project = new Project(dataDir + "project.xml");
// Dodatkowy kod dla importu pakietów
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
Objaśnienie: Zainicjuj obiekt kalendarza, ustaw datę początkową i zastosuj ją w projekcie.
## Krok 2: Zdefiniuj zadanie i zasób
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Wyjaśnienie: Utwórz zadanie i zasób, ustalając stawki za pracę standardową i nadgodziny.
## Krok 3: Ustaw czas trwania zadania
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Wyjaśnienie: Określ czas trwania zadania (np. 6 dni).
## Krok 4: Przypisz zasób do zadania
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Objaśnienie: Przypisz zasób do zadania.
## Krok 5: Skonfiguruj przypisanie zasobów
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Objaśnienie: Ustaw parametry takie jak zatrzymanie, wznowienie i kontur pracy dla przydziału zasobu.
## Krok 6: Ustaw linię bazową
```java
project.setBaseline(BaselineType.Baseline);
```
Wyjaśnienie: Ustal punkt odniesienia dla projektu.
## Krok 7: Zaktualizuj wykonanie zadania
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Objaśnienie: Wskaż procent wykonania zadania.
## Krok 8: Pobierz dane okresowe
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Objaśnienie: Pobierz dane okresowe dotyczące pozostałej pracy przydziału.
## Krok 9: Wyświetl dane okresowe
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Dodatkowy kod do wyświetlania innych wartości
```
Objaśnienie: Wyprowadź i wyświetl dane okresowe.
## Wniosek
Efektywne zarządzanie danymi okresowymi zadań jest niezbędne dla powodzenia projektu. Aspose.Tasks dla Java upraszcza ten proces, zapewniając kompleksowy zestaw funkcjonalności. Postępując zgodnie z tym samouczkiem, możesz bezproblemowo zintegrować Aspose.Tasks z projektem Java, zapewniając precyzyjną kontrolę nad harmonogramem projektu i alokacją zasobów.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.Tasks dla Java w dowolnym projekcie Java?
O: Tak, Aspose.Tasks for Java jest kompatybilny z każdym projektem opartym na Javie.
### P: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks dla Java?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie i dyskusje.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks dla Java?
 Odpowiedź: Możesz nabyć licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę kupić Aspose.Tasks dla Java?
 O: Możesz kupić Aspose.Tasks dla Java[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
