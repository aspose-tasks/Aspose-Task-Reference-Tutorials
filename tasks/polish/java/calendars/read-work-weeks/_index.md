---
title: Przeczytaj tygodnie pracy z kalendarza MS Project za pomocą Aspose.Tasks
linktitle: Czytaj tygodnie pracy z kalendarza za pomocą Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak czytać tygodnie pracy z kalendarza MS Project za pomocą Aspose.Tasks dla Java. Uzyskaj instrukcje krok po kroku w tym obszernym samouczku.
type: docs
weight: 15
url: /pl/java/calendars/read-work-weeks/
---
## Wstęp
tym samouczku omówimy, jak używać Aspose.Tasks dla języka Java do odczytywania informacji o tygodniach pracy z kalendarza programu Microsoft Project. Aspose.Tasks to potężna biblioteka Java, która umożliwia programowe manipulowanie dokumentami Microsoft Project i zarządzanie nimi.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Pobrano i zainstalowano bibliotekę Aspose.Tasks dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety, aby rozpocząć pracę z naszym kodem:
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```
## Krok 1: Skonfiguruj swój katalog danych
Skonfiguruj ścieżkę katalogu, w którym znajduje się plik MS Project:
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Utwórz instancję projektu i uzyskaj dostęp do kalendarza
Utwórz nową instancję klasy Projekt i uzyskaj dostęp do kolekcji kalendarza i tygodni roboczych:
```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```
## Krok 3: Powtarzaj tygodnie pracy
Przeglądaj kolekcję tygodni roboczych i wyświetl informacje o nich:
```java
for (WorkWeek workWeek : collection) {
    // Wyświetl nazwę tygodnia roboczego, daty od i do
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Dostęp do dni tygodnia i godzin pracy
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // W razie potrzeby dalsze czasy pracy procesu
    }
}
```
## Wniosek
tym samouczku nauczyliśmy się czytać informacje o tygodniach pracy z kalendarza Microsoft Project za pomocą Aspose.Tasks dla Java. Ta potężna biblioteka umożliwia płynną manipulację plikami projektu, umożliwiając programistom efektywną automatyzację różnych zadań.
## Często zadawane pytania
### Czy mogę modyfikować informacje o tygodniach pracy za pomocą Aspose.Tasks dla Java?
Tak, Aspose.Tasks udostępnia interfejsy API umożliwiające modyfikowanie, dodawanie lub usuwanie tygodni pracy i powiązanych z nimi informacji.
### Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, w tym formaty MPP i XML.
### Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?
Absolutnie Aspose.Tasks można bezproblemowo zintegrować z innymi frameworkami i bibliotekami Java w celu zwiększenia funkcjonalności.
### Czy dostępna jest wersja próbna Aspose.Tasks?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks z[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?
Możesz znaleźć wsparcie i pomoc na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).