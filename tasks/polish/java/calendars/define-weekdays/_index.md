---
title: Zdefiniuj dni tygodnia w kalendarzu za pomocą Aspose.Tasks
linktitle: Zdefiniuj dni tygodnia w kalendarzu za pomocą Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak definiować dni tygodnia w kalendarzu MS Project przy użyciu Aspose.Tasks dla Java. Dostosuj dni i godziny pracy bez wysiłku.
weight: 12
url: /pl/java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zdefiniuj dni tygodnia w kalendarzu za pomocą Aspose.Tasks

## Wstęp
tym samouczku omówimy proces definiowania dni tygodnia w kalendarzu MS Project przy użyciu Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom programowe manipulowanie plikami Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) jeśli jeszcze tego nie zrobiłeś.
2.  Aspose.Tasks for Java Library: Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java z pliku[strona pobierania](https://releases.aspose.com/tasks/java/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety wymagane do pracy z Aspose.Tasks w swoim projekcie Java:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Krok 1: Utwórz instancję projektu
Utwórz instancję obiektu Project, który reprezentuje plik MS Project, z którym będziesz pracować:
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Krok 2: Zdefiniuj kalendarz
Utwórz nową instancję kalendarza i dodaj ją do projektu:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Krok 3: Dodaj dni robocze
Zdefiniuj dni robocze, dodając od poniedziałku do czwartku z domyślnymi czasami:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Krok 4: Ustaw niestandardowy dzień roboczy
Zdefiniuj sobotę i niedzielę jako dni robocze:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Krok 5: Ustaw krótki dzień roboczy
Ustaw piątek jako krótki dzień roboczy z niestandardowymi godzinami pracy:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Krok 6: Zapisz projekt
Zapisz zmodyfikowany projekt do pliku XML:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Wniosek
Gratulacje! Pomyślnie zdefiniowałeś dni tygodnia w kalendarzu MS Project przy użyciu Aspose.Tasks dla Java. Możesz teraz zintegrować tę funkcjonalność z aplikacjami Java, aby programowo manipulować plikami MS Project.
## Często zadawane pytania
### P1: Czy mogę zdefiniować niestandardowe dni wolne od pracy za pomocą Aspose.Tasks dla Java?
 Odp.: Tak, możesz zdefiniować niestandardowe dni wolne od pracy, ustawiając`DayWorking` własność do`false` dla danego dnia tygodnia.
### P2: Jak mogę dodać święta do kalendarza?
 O: Możesz dodać święta, tworząc instancje`CalendarExceptions` określeniem dat wolnych od pracy.
### P3: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?
Odp.: Tak, Aspose.Tasks obsługuje różne wersje plików MS Project, w tym formaty MPP, MPT i XML.
### P4: Czy mogę modyfikować istniejące kalendarze w pliku MS Project?
O: Tak, możesz załadować istniejący projekt z kalendarzami, wprowadzić modyfikacje, a następnie zapisać zmiany z powrotem w oryginalnym pliku.
### P5: Czy Aspose.Tasks zapewnia obsługę powtarzających się zadań?
Odp.: Tak, Aspose.Tasks umożliwia pracę z powtarzającymi się zadaniami, w tym definiowanie wzorców ich powtarzania i czasu trwania.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
