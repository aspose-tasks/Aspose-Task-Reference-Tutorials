---
title: Uzyskaj godziny pracy z kalendarza za pomocą Aspose.Tasks
linktitle: Uzyskaj godziny pracy z kalendarza za pomocą Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Z łatwością wyodrębnij godziny pracy z kalendarzy MS Project za pomocą Aspose.Tasks dla Java. Uprość zadania związane z zarządzaniem projektami.
type: docs
weight: 13
url: /pl/java/calendars/working-hours/
---
## Wstęp
Zarządzanie kalendarzami projektów i wyodrębnianie godzin pracy jest niezbędne do skutecznego zarządzania projektami. Aspose.Tasks dla Java zapewnia solidną funkcjonalność umożliwiającą łatwe pobieranie godzin pracy z kalendarzy MS Project. W tym samouczku przeprowadzimy Cię przez ten proces krok po kroku.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Biblioteka Aspose.Tasks dla Java pobrana i dodana do Twojego projektu. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość języka programowania Java.
## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do pracy z Aspose.Tasks dla Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Załaduj plik projektu
Zacznij od załadowania pliku MS Project:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Pobierz informacje o zadaniu i kalendarzu
Wyodrębnij szczegóły zadania i kalendarza z projektu:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Krok 3: Zdefiniuj daty rozpoczęcia i zakończenia
Ustaw daty rozpoczęcia i zakończenia zadania:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Krok 4: Iteruj po datach
Iteruj po datach w czasie trwania zadania:
```java
java.util.Calendar tempDate = calStartDate;
```
## Krok 5: Oblicz czas trwania
Oblicz czas trwania w minutach, godzinach i dniach:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Wniosek
tym samouczku omówiliśmy, jak pobrać godziny pracy z kalendarza MS Project za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie zarządzać harmonogramami projektów i z łatwością obliczać czas trwania zadań.
## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje złożone struktury projektów?
O: Tak, Aspose.Tasks for Java zapewnia kompleksowe wsparcie w obsłudze złożonych struktur projektów, w tym zadań, zasobów i kalendarzy.
### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?
O: Oczywiście, Aspose.Tasks for Java obsługuje różne wersje MS Project, zapewniając kompatybilność w różnych środowiskach.
### P: Czy mogę dostosować godziny pracy i święta w kalendarzach projektów?
Odp.: Tak, możesz łatwo dostosować godziny pracy i święta zgodnie z wymaganiami projektu, korzystając z Aspose.Tasks dla API Java.
### P: Czy Aspose.Tasks for Java oferuje wsparcie i dokumentację?
O: Tak, Aspose.Tasks for Java zapewnia obszerną dokumentację i dedykowane fora wsparcia, aby pomóc programistom w efektywnym wykorzystaniu jego funkcji.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Tasks dla Java z[Tutaj](https://releases.aspose.com/).