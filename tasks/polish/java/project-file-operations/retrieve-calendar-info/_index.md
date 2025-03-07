---
title: Pobierz informacje z kalendarza projektu MS w Aspose.Tasks
linktitle: Pobierz informacje o kalendarzu w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak odzyskać informacje z kalendarza MS Project przy użyciu Aspose.Tasks dla Java. Przewodnik krok po kroku dotyczący programowego dostępu do szczegółów kalendarza.
weight: 14
url: /pl/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz informacje z kalendarza projektu MS w Aspose.Tasks

## Wstęp
W tym samouczku dowiemy się, jak pobrać informacje z kalendarza z plików Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Java. Aspose.Tasks zapewnia zaawansowane funkcje do manipulowania danymi projektu, w tym dostępu do szczegółów kalendarza, takich jak dni i godziny pracy.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawowa znajomość programowania w języku Java.
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Aspose.Tasks dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego kodu Java, aby móc korzystać z funkcjonalności Aspose.Tasks.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Dla lepszego zrozumienia podzielmy teraz podany przykład na wiele kroków.
## Krok 1: Ustaw katalog danych
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` ze ścieżką do katalogu plików projektu.
## Krok 2: Zdefiniuj jednostki czasu
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
Stałe te reprezentują jednostki czasu w mikrosekundach.
## Krok 3: Utwórz instancję projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
 Ta linia tworzy instancję`Project` klasę, inicjując ją ścieżką do pliku projektu (`project.mpp`).
## Krok 4: Pobierz informacje z kalendarzy
```java
CalendarCollection alCals = project.getCalendars();
```
Tutaj pobieramy kolekcję kalendarzy obecnych w pliku projektu.
## Krok 5: Iteruj po kalendarzach
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Informacje o kalendarzu
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iteruj po dniach tygodnia
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Czas w milisekundach
            double time = ts / (OneHour); // Zamień na godziny
            if (wd.getDayWorking()) {
                // Wyświetl dni i godziny pracy
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
Ta pętla przegląda każdy kalendarz i drukuje jego UID, nazwę i dni robocze z odpowiednimi godzinami pracy.
## Krok 6: Wyświetl komunikat o zakończeniu
```java
System.out.println("Process completed Successfully");
```
Na koniec zostanie wyświetlony komunikat informujący o zakończeniu procesu.
## Wniosek
W tym samouczku nauczyliśmy się, jak pobierać informacje z kalendarza z plików MS Project za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie uzyskiwać dostęp do danych projektu i manipulować nimi w aplikacjach Java.

## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi językami programowania?
Odp.: Tak, Aspose.Tasks obsługuje wiele platform i języków programowania, w tym .NET, C++, Pythona i Javy.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?
Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks?
 Odpowiedź: Tak, można kupić licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę znaleźć szczegółową dokumentację dla Aspose.Tasks?
 Odpowiedź: Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
