---
date: 2026-08-08
description: Dowiedz się, jak ustawić kalendarz ms project, ustawić dzienne godziny
  pracy oraz dodać dni robocze w weekendy przy użyciu Aspose.Tasks dla Java. Zapisz
  projekt jako XML w kilku linijkach kodu.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Jak ustawić kalendarz ms project i zdefiniować dni robocze
og_description: Ustaw kalendarz ms project, zdefiniuj dni robocze i dodaj dni robocze
  w weekendy przy użyciu Aspose.Tasks dla Java. Postępuj zgodnie z tym samouczkiem
  krok po kroku i zapisz jako XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Ustaw kalendarz ms project za pomocą Aspose.Tasks – przewodnik Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Jak ustawić kalendarz ms project i zdefiniować dni robocze
url: /pl/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kalendarz ms project i zdefiniować dni robocze

W tym samouczku dowiesz się, **jak ustawić kalendarz ms project** programowo, zdefiniować dni robocze i skonfigurować niestandardowe dni pracy przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz silnik harmonogramowania, integrujesz się z systemami ERP, czy po prostu potrzebujesz wygenerować plan projektu bez otwierania Microsoft Project, poniższe kroki pokażą, jak utworzyć kalendarz, ustawić dzienne godziny pracy i dodać dni pracy w weekendy w kilku linijkach kodu.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java.  
- **Czy mogę dodać dni pracy w weekendy?** Tak – wystarczy oznaczyć sobotę i niedzielę jako dni robocze.  
- **Jak zapisać projekt?** Wywołaj `prj.save(..., SaveFileFormat.Xml)`.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w ocenie; licencja jest wymagana w środowisku produkcyjnym.  
- **Jaką wersję Javy obsługiwano?** Java 8 lub wyższa.

## Co to jest ustawianie kalendarza ms project?
Ustawienie kalendarza w MS Project określa, które dni są uznawane za dni robocze, liczbę godzin pracy każdego dnia oraz wszelkie specjalne wyjątki, takie jak święta lub zamknięcia całej firmy. Informacje te wpływają na planowanie zadań, przydział zasobów i ogólne terminy projektu, zapewniając, że obliczenia respektują rzeczywiste wzorce pracy organizacji.

## Dlaczego używać Aspose.Tasks do manipulacji kalendarzem?
Aspose.Tasks zapewnia programistyczną kontrolę nad kalendarzami bez uruchamiania interfejsu Microsoft Project. Działa na każdym systemie operacyjnym obsługującym Javę, obsługuje ponad 50 formatów wejściowych i wyjściowych oraz może przetwarzać projekty liczące setki stron bez wczytywania całego pliku do pamięci, co czyni go idealnym do automatyzacji po stronie serwera.

## Wymagania wstępne
- **Java Development Kit (JDK) 8+** – pobierz ze [strony Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
- IDE lub narzędzie budujące (Maven/Gradle), aby dodać plik JAR Aspose.Tasks do ścieżki klas.

## Importowanie pakietów
Importuj klasy, które zapewniają dostęp do projektów, kalendarzy i obiektów czasu pracy.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Przewodnik krok po kroku

### Krok 1: utwórz instancję projektu
Utwórz obiekt `Project`, który reprezentuje plik MS Project, który będziesz modyfikować.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Krok 2: zdefiniuj nowy kalendarz
`Calendar` reprezentuje zestaw godzin pracy, wyjątków i świąt dla projektu.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Krok 3: dodaj standardowe dni robocze (poniedziałek‑czwartek)
`WeekDay` definiuje czas pracy dla konkretnego dnia tygodnia.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Krok 4: dodaj dni pracy w weekend
Jeśli Twój projekt działa w weekendy, dodaj sobotę i niedzielę jako regularne dni robocze. To demonstruje **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Krok 5: ustaw niestandardowy krótki dzień pracy (piątek)
Skonfiguruj piątek z poranną zmianą (9 – 12) i popołudniową zmianą (13 – 16), aby zilustrować **set daily working hours** oraz niestandardowy krótki dzień pracy.

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

### Krok 6: zapisz projekt jako XML
`SaveFileFormat` wymienia obsługiwane formaty plików przy zapisywaniu projektu, takie jak XML lub MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Częste problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Working times not applied** | Upewnij się, że `setDayWorking(true)` jest wywoływane dla każdego niestandardowego `WeekDay`. |
| **File not found when saving** | Sprawdź, czy `dataDir` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu. |
| **Calendar not reflected in tasks** | Przypisz nowo utworzony kalendarz do zasobów lub zadań przy użyciu `task.setCalendar(cal)`. |

## Najczęściej zadawane pytania

**P: Czy mogę zdefiniować niestandardowe dni wolne od pracy przy użyciu Aspose.Tasks dla Javy?**  
O: Tak. Ustaw właściwość `DayWorking` na `false` dla dowolnego `WeekDay`, który chcesz traktować jako dzień wolny od pracy.

**P: Jak dodać święta lub wyjątki obejmujące całą firmę?**  
O: Utwórz obiekty `CalendarException`, określ daty wyjątków i dodaj je do `cal.getExceptions()`.

**P: Czy biblioteka jest kompatybilna ze starszymi wersjami MS Project?**  
O: Zdecydowanie tak. Aspose.Tasks obsługuje formaty MPP, MPT i XML w wielu wersjach Project.

**P: Czy mogę zmodyfikować istniejący kalendarz w zaimportowanym projekcie?**  
O: Załaduj projekt przy użyciu `new Project("existing.mpp")`, pobierz żądany kalendarz, wprowadź zmiany i zapisz.

**P: Czy Aspose.Tasks obsługuje również zadania cykliczne?**  
O: Tak, możesz tworzyć i edytować zadania cykliczne przy użyciu klasy `RecurringTask`.

## Zakończenie
Teraz wiesz, **jak ustawić kalendarz ms project**, zdefiniować dni robocze, dodać dni pracy w weekendy i skonfigurować krótki harmonogram na piątek — wszystko przy użyciu Aspose.Tasks dla Javy. Zapisz wynik jako XML i zintegrować logikę kalendarza z dowolnym rozwiązaniem do zarządzania projektami opartym na Javie.

---

**Ostatnia aktualizacja:** 2026-08-08  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks dla Javy](/tasks/java/calendars/create/)
- [Określ dni robocze i godziny pracy przy użyciu Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Dodaj święta do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}