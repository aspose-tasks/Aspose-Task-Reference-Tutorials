---
date: 2026-07-29
description: Dowiedz się, jak planować dni niepracujące, tworząc kalendarz projektu
  za pomocą Aspose.Tasks for Java, definiując weekday exceptions i zarządzając holiday
  schedules.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Planowanie dni niepracujących – Tworzenie kalendarza projektu Aspose
og_description: Planowanie dni niepracujących przy użyciu Aspose.Tasks for Java. Dowiedz
  się, jak definiować weekdays, dodawać calendar exceptions i efektywnie zarządzać
  holiday schedules.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Planowanie dni niepracujących – Tworzenie kalendarza projektu Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Planowanie dni niepracujących – Tworzenie kalendarza projektu Aspose
url: /pl/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Harmonogram dni niepracujących – Tworzenie kalendarza projektu Aspose

### Wprowadzenie
Kiedy potrzebujesz **zaplanować dni niepracujące** w projekcie, musisz mieć możliwość modelowania świąt, specjalnych zmian lub tymczasowych zamknięć bezpośrednio w planie projektu. Aspose.Tasks for Java daje pełną kontrolę nad definicjami kalendarzy, umożliwiając dodawanie wyjątków odzwierciedlających rzeczywiste harmonogramy. W tym samouczku przeprowadzimy Cię przez dokładne kroki definiowania dni tygodnia dla wyjątków kalendarza, aby Twoje terminy projektowe były dokładne i wiarygodne. Na końcu zobaczysz również, jak to wpisuje się w szerszą strategię **harmonogramu dni niepracujących** dla każdego projektu korporacyjnego.

## Szybkie odpowiedzi
- **Co oznacza „schedule non working days”?**  
  Oznacza to użycie Aspose.Tasks do stworzenia kalendarza, który oznacza określone daty jako niepracujące, automatycznie wpływając na daty zadań.  
- **Czy potrzebuję licencji, aby uruchomić przykład?**  
  Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w produkcji.  
- **Jakie IDE są obsługiwane?**  
  IntelliJ IDEA, Eclipse, NetBeans lub dowolne IDE obsługujące Java 8+.  
- **Czy mogę dodać wiele wyjątków do tego samego kalendarza?**  
  Tak – możesz dodać dowolną liczbę obiektów `CalendarException`.  
- **W jakich formatach plików mogę zapisać projekt?**  
  XML, MPP oraz kilka innych formatów obsługiwanych przez Aspose.Tasks.  

## Co to jest Kalendarz Projektu w Aspose.Tasks?
**Kalendarz projektu** to obiekt najwyższego poziomu w Aspose.Tasks, który definiuje dni i godziny pracy dla projektu. Bezpośrednio wpływa na daty rozpoczęcia/zakonczenia zadań, przydział zasobów oraz ogólne obliczenia harmonogramu. Dostosowując kalendarz, zapewniasz, że harmonogram respektuje rzeczywiste ograniczenia, takie jak święta firmowe czy zasady pracy w weekendy.

## Dlaczego definiować dni tygodnia dla wyjątków kalendarza?
Definiowanie wyjątków dni tygodnia zapewnia, że silnik projektu traktuje te dni jako niepracujące, zapobiegając automatycznemu planowaniu zadań w tych terminach i utrzymując oś czasu zgodną z rzeczywistymi ograniczeniami, takimi jak święta, okna konserwacyjne czy specjalne wzorce zmian w organizacji.

- **Dokładne terminy:** Zadania nie będą umieszczane w okresach świątecznych ani blackout.  
- **Planowanie zasobów:** Zasoby są przydzielane wyłącznie w dni robocze, co zapobiega nadmiernemu obciążeniu.  
- **Zgodność:** Harmonogramy automatycznie stosują się do polityk organizacyjnych lub kalendarzy świąt prawnych.  

## Harmonogram dni niepracujących z wyjątkami kalendarza
Gdy utrzymujesz **harmonogram dni niepracujących**, zazwyczaj posiadasz główną listę świąt, okien konserwacyjnych lub innych okresów blackout. Dodanie tych dat jako obiektów `CalendarException` gwarantuje, że każde obliczenie — czy to analiza ścieżki krytycznej, czy wyrównywanie zasobów — automatycznie respektuje te ograniczenia. To podejście eliminuje ręczne korekty dat i zmniejsza ryzyko odchylenia harmonogramu.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub nowsza.  
2. **Aspose.Tasks for Java** – pobierz z oficjalnej [strony pobierania Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans lub dowolny edytor kompatybilny z Java.  

## Jak zaplanować dni niepracujące przy użyciu wyjątków kalendarza

Załaduj projekt, utwórz niestandardowy kalendarz i dodaj obiekty `CalendarException`, które oznaczą wybrane dni tygodnia jako niepracujące. Cały proces można wykonać w kilku prostych krokach, a wynikowy kalendarz automatycznie wpłynie na wszystkie logiki planowania zadań.

### Przewodnik krok po kroku

### Krok 1: Import wymaganych pakietów
Potrzebujemy podstawowych klas Aspose.Tasks oraz `GregorianCalendar` z Javy do obsługi dat.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Krok 2: Zdefiniuj katalog danych
Określ, gdzie zostanie zapisany wygenerowany plik projektu.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Utwórz instancję projektu
`Project` jest głównym obiektem, który przechowuje wszystkie dane projektu, w tym zadania, zasoby i kalendarze.

```java
Project project = new Project();
```

### Krok 4: Zdefiniuj kalendarz
`Calendar` reprezentuje harmonogram dni i godzin pracy oraz niepracujących w ramach projektu.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Krok 5: Zdefiniuj wyjątek dni tygodnia
`CalendarException` reprezentuje okres oznaczony jako niepracujący w kalendarzu.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Krok 6: Zapisz projekt
Zachowaj projekt, w tym niestandardowy kalendarz i jego wyjątek, w pliku XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Częste problemy i rozwiązania
| Problem | Rozwiązanie |
|---------|-------------|
| **Daty wyjątków nie zastosowane** | Upewnij się, że `setEnteredByOccurrences(false)` i prawidłowe wartości `FromDate/ToDate`. |
| **Zapisany plik jest pusty** | Sprawdź, czy `dataDir` wskazuje na folder zapisywalny i czy nazwa pliku kończy się na `.xml`. |
| **Kalendarz nie odzwierciedla się w harmonogramie zadań** | Przypisz kalendarz do zadań lub zasobów używając `task.setCalendar(cal)` lub `resource.setCalendar(cal)`. |

## Najczęściej zadawane pytania

**P: Czy mogę zdefiniować wiele wyjątków dla różnych dni tygodnia w tym samym kalendarzu?**  
O: Tak. Dodaj dodatkowe obiekty `CalendarException` do `cal.getExceptions()` dla każdego odrębnego okresu lub reguły.

**P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi IDE Java?**  
O: Absolutnie. Biblioteka działa z IntelliJ IDEA, Eclipse, NetBeans oraz każdym IDE obsługującym standardowe projekty Java.

**P: Czy mogę dostosować typy wyjątków poza codziennymi wyjątkami?**  
O: Tak. Użyj `CalendarExceptionType.Weekly`, `Monthly` lub `Yearly`, aby dopasować je do potrzeb planowania.

**P: Jak mogę obsługiwać wyjątki dynamicznie w zależności od wymagań projektu?**  
O: Twórz obiekty wyjątków programowo — np. odczytuj daty świąt z bazy danych lub pliku konfiguracyjnego i twórz instancje `CalendarException` w pętli.

**P: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
O: Tak, możesz pobrać darmową wersję próbną z [strony pobierania Aspose.Tasks Java](https://releases.aspose.com/tasks/java/).

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz, jak **zaplanować dni niepracujące** poprzez stworzenie kalendarza projektu i zdefiniowanie wyjątków dni tygodnia, które dokładnie odzwierciedlają święta lub specjalne okresy niepracujące. Prawidłowa konfiguracja kalendarza jest kluczowa dla realistycznych harmonogramów, przydziału zasobów i sukcesu projektu. Eksperymentuj, przypisując niestandardowy kalendarz do zadań lub zasobów oraz testując inne typy wyjątków, aby zbudować kompleksowy **harmonogram dni niepracujących** dla dowolnego projektu.

---

**Ostatnia aktualizacja:** 2026-07-29  
**Testowane z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Utwórz wyjątek kalendarza Aspose dla Java](/tasks/java/calendar-exceptions/add-remove/)
- [Jak ustawić kalendarz i zdefiniować dni tygodnia w MS Project przy użyciu Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}