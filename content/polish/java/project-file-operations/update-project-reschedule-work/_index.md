---
title: Zaktualizuj i przełóż projekt MS w Aspose.Tasks
linktitle: Zaktualizuj projekt i przełóż nieukończoną pracę w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak programowo aktualizować i zmieniać harmonogram plików MS Project za pomocą Aspose.Tasks dla Java.
type: docs
weight: 23
url: /pl/java/project-file-operations/update-project-reschedule-work/
---
## Wstęp
Microsoft Project to powszechnie używane oprogramowanie do zarządzania projektami, które pozwala użytkownikom efektywnie zarządzać zadaniami, zasobami i harmonogramem. Aspose.Tasks dla Java zapewnia potężny zestaw interfejsów API do programowego manipulowania plikami Microsoft Project. W tym samouczku dowiemy się, jak zaktualizować pliki MS Project i przełożyć niezakończone prace za pomocą Aspose.Tasks dla Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Aspose.Tasks dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość języka programowania Java.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do kodu Java:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## Krok 1: Skonfiguruj projekt
Zainicjuj nowy obiekt Project i zdefiniuj w nim zadania wraz z czasem ich trwania i zależnościami.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Zdefiniuj zadania i czas ich trwania
// ...
// Zdefiniuj zależności zadań
// ...
// Zapisz początkowy stan projektu
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## Krok 2: Zaktualizuj pracę nad projektem
Zaktualizuj pracę nad projektem, aby oznaczyć ją jako ukończoną do określonej daty.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Zapisz zaktualizowany projekt
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Krok 3: Przełóż nieukończoną pracę na inny termin
Przełóż niezakończoną pracę na inny termin, aby rozpocząć ją po określonej dacie.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Zapisz przełożony projekt
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Wniosek
W tym samouczku nauczyliśmy się, jak aktualizować pliki MS Project i zmieniać terminy niezakończonych prac za pomocą Aspose.Tasks dla Java. Może to być szczególnie przydatne w scenariuszach, w których harmonogram projektu wymaga dostosowania w oparciu o postęp lub zmieniające się priorytety.

## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje złożone struktury projektów?
O: Tak, Aspose.Tasks dla Java zapewnia solidne interfejsy API do wydajnego zarządzania zadaniami, zależnościami, zasobami i innymi elementami projektu.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Java?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub pytań.
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Java?
 Odpowiedź: Tak, można kupić licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks dla Java?
 Odpowiedź: Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/java/) w celu uzyskania kompleksowych przewodników i referencji API.