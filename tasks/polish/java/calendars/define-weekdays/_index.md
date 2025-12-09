---
date: 2025-12-02
description: Dowiedz się, jak ustawić kalendarz, zdefiniować dni robocze w MS Project
  i ustawić niestandardowe dni pracy przy użyciu Aspose.Tasks dla Javy. Zapisz projekt
  jako XML za pomocą zaledwie kilku linii kodu.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ustawić kalendarz i zdefiniować dni tygodnia w MS Project przy użyciu Aspose.Tasks
url: /pl/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kalendarz i zdefiniować dni tygodnia w MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku odkryjesz **jak ustawić kalendarz** programowo i zdefiniować dni tygodnia w pliku Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy potrzebujesz utworzyć standardowy tydzień pracy, dodać dni robocze w weekendy, czy skonfigurować krótki harmonogram na piątek, ten przewodnik przeprowadzi Cię przez każdy krok — od utworzenia projektu po zapisanie pliku jako XML.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Tasks for Java  
- **Czy mogę dodać dni robocze w weekendy?** Tak — wystarczy dodać sobotę i niedzielę jako dni robocze.  
- **Jak zapisać projekt?** Użyj `prj.save(..., SaveFileFormat.Xml)`.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do oceny; licencja jest wymagana w produkcji.  
- **Jaka wersja Javy jest wymagana?** Java 8 lub wyższa.

## Co oznacza „jak ustawić kalendarz” w kontekście MS Project?
Ustawienie kalendarza w MS Project oznacza określenie, które dni są dniami roboczymi, dzienne godziny pracy oraz wszelkie wyjątki, takie jak święta. Ten kalendarz steruje planowaniem zadań, przydziałem zasobów i ogólnymi terminami projektu.

## Dlaczego warto używać Aspose.Tasks do manipulacji kalendarzem?
- **Pełna kontrola** — programowo twórz, modyfikuj lub usuwaj kalendarze bez otwierania interfejsu użytkownika.  
- **Cross‑platform** — działa na każdym systemie operacyjnym obsługującym Javę.  
- **Obsługuje wszystkie formaty plików** — MPP, MPT i XML, dzięki czemu możesz *zapisz projekt jako XML* w celu łatwej integracji z innymi systemami.  
- **Brak zależności COM** — w przeciwieństwie do biblioteki Microsoft Project Interop.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK) 8+** — pobierz ze [strony Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** — pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. IDE lub narzędzie budujące (Maven/Gradle), aby dodać plik JAR Aspose.Tasks do classpath projektu.

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy. Te importy dają dostęp do obiektów projektu, kalendarza i czasu pracy.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz instancję projektu
Utwórz nowy obiekt `Project`. Ten obiekt reprezentuje plik MS Project, który będziesz edytować.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Krok 2: Zdefiniuj nowy kalendarz
Dodaj nowy kalendarz do projektu. Nadanie mu czytelnej nazwy pomaga, gdy masz wiele kalendarzy.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Krok 3: Dodaj standardowe dni robocze (poniedziałek‑czwartek)
Użyj wbudowanego pomocnika `WeekDay.createDefaultWorkingDay`, aby ustawić domyślny harmonogram 9 – 17 dla podstawowego tygodnia pracy.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Krok 4: Dodaj dni robocze w weekendy
Jeśli Twój projekt działa w weekendy, po prostu dodaj sobotę i niedzielę jako regularne dni robocze. To demonstruje **dodawanie dni roboczych w weekendy**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Krok 5: Ustaw niestandardowy krótki dzień roboczy (piątek)
Tutaj **ustawiamy niestandardowe dni robocze** dla piątku: zmiana poranna (9 – 12) oraz zmiana popołudniowa (13 – 16).

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

### Krok 6: Zapisz projekt jako XML
Na koniec zapisz zmiany. Opcja `SaveFileFormat.Xml` pozwala **zapisz projekt jako XML**, co jest przydatne przy integracji z innymi narzędziami.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Częste problemy i rozwiązania

| Problem | Rozwiązanie |
|---------|-------------|
| **Czasy pracy nie zostały zastosowane** | Upewnij się, że `setDayWorking(true)` jest wywoływane dla niestandardowego `WeekDay`. |
| **Plik nie znaleziony podczas zapisywania** | Sprawdź, czy `dataDir` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu. |
| **Kalendarz nie jest odzwierciedlony w zadaniach** | Przypisz nowo utworzony kalendarz do zasobów lub zadań za pomocą `task.setCalendar(cal)`. |

## Często zadawane pytania

**Q: Czy mogę zdefiniować niestandardowe dni wolne od pracy przy użyciu Aspose.Tasks dla Javy?**  
A: Tak. Ustaw właściwość `DayWorking` na `false` dla dowolnego `WeekDay`, który chcesz traktować jako dzień wolny od pracy.

**Q: Jak mogę dodać święta lub wyjątki obowiązujące w całej firmie?**  
A: Utwórz obiekty `CalendarException`, określ daty wyjątków i dodaj je do `cal.getExceptions()`.

**Q: Czy biblioteka jest kompatybilna ze starszymi wersjami MS Project?**  
A: Zdecydowanie tak. Aspose.Tasks obsługuje formaty MPP, MPT i XML w wielu wersjach Project.

**Q: Czy mogę zmodyfikować istniejący kalendarz w zaimportowanym projekcie?**  
A: Wczytaj projekt za pomocą `new Project("existing.mpp")`, pobierz żądany kalendarz, wprowadź zmiany i zapisz.

**Q: Czy Aspose.Tasks obsługuje także zadania cykliczne?**  
A: Tak, możesz tworzyć i edytować zadania cykliczne przy użyciu klasy `RecurringTask`.

## Zakończenie
Teraz wiesz **jak ustawić kalendarz**, **zdefiniować dni tygodnia w MS Project**, dodać dni robocze w weekendy oraz utworzyć krótki harmonogram na piątek — wszystko przy użyciu Aspose.Tasks dla Javy. Zapisz wynik jako XML i zintegrować logikę kalendarza w dowolnym rozwiązaniu do zarządzania projektami opartym na Javie.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}