---
date: 2026-08-13
description: Dowiedz się, jak odczytać tygodnie robocze z kalendarza MS Project przy
  użyciu Aspose.Tasks dla Javy. Postępuj zgodnie z przewodnikiem krok po kroku, zawierającym
  przykłady kodu i wskazówki rozwiązywania problemów.
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Odczytaj tygodnie robocze z kalendarza przy użyciu Aspose.Tasks
og_description: Jak odczytać tygodnie robocze z kalendarza MS Project przy użyciu
  Aspose.Tasks dla Javy. Skorzystaj z zwięzłego samouczka zawierającego kroki konfiguracji,
  fragmenty kodu i wskazówki rozwiązywania problemów.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: Jak odczytać tygodnie robocze z kalendarza MS przy użyciu Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: Jak odczytać tygodnie robocze z kalendarza MS przy użyciu Aspose.Tasks
url: /pl/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać tygodnie robocze z kalendarza MS przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku **dowiesz się, jak odczytać tygodnie robocze** z kalendarza Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz pulpit raportowy, synchronizujesz harmonogramy z systemem ERP, czy automatyzujesz pobieranie danych do analiz, programowy dostęp do definicji tygodni roboczych oszczędza niezliczone godziny ręcznej pracy. Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** i może przetwarzać projekty liczące setki stron bez wczytywania całego pliku do pamięci, zapewniając zarówno elastyczność, jak i wydajność.

## Szybkie odpowiedzi
- **Co oznacza „odczyt tygodni roboczych”?** Odwołuje się do wyodrębniania definicji tygodni roboczych (dat i dziennych reguł czasu pracy) z pliku Project przy użyciu kodu Java.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Tasks for Java (dostępna darmowa wersja próbna).  
- **Czy potrzebuję licencji do rozwoju?** Wersja próbna działa do testów; licencja komercyjna jest wymagana przy wdrożeniach produkcyjnych.  
- **Jakie formaty plików są obsługiwane?** Obsługiwane są zarówno pliki *.mpp*, jak i Project XML, a także ponad 50 innych formatów do importu/eksportu.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut po skonfigurowaniu biblioteki.

## Czym jest tydzień roboczy w MS Project?
Tydzień roboczy definiuje reguły kalendarza określające, kiedy zasoby są dostępne w określonym okresie. Zawiera datę rozpoczęcia, datę zakończenia oraz dzienne przedziały czasu pracy (np. 9 – 17). W MS Project każdy kalendarz może zawierać wiele tygodni roboczych, co pozwala modelować święta, zmiany robocze lub sezonowe harmonogramy.

## Jak Aspose.Tasks odczytuje tygodnie robocze z kalendarza?
Aspose.Tasks udostępnia `WorkWeekCollection` obiektu `Calendar`. Tworząc instancję `Project`, wybierając odpowiedni kalendarz (według UID lub nazwy) i iterując po jego `WorkWeekCollection`, możesz pobrać etykietę każdego tygodnia roboczego, obowiązujący zakres dat oraz szczegółowe dzienne przedziały czasu pracy. API automatycznie obsługuje wszystkie konwersje dat i czasu oraz respektuje ustawienia strefy czasowej projektu.

## Dlaczego odczytywać tygodnie robocze w Javie z kalendarza Microsoft Project?
Programowe odczytywanie tygodni roboczych eliminuje ręczne kopiowanie‑wklejanie, zapewnia, że systemy zależne (ERP, HR, raportowanie) używają dokładnie tych samych reguł harmonogramowania, oraz gwarantuje spójność w wielu projektach. Automatyzacja zmniejsza także liczbę błędów ludzkich i przyspiesza procesy integracyjne, szczególnie gdy trzeba przetwarzać dziesiątki plików projektów każdej nocy.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz:

1. **Java Development Kit (JDK)** – zainstalowana wersja 8 lub nowsza.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z oficjalnej strony: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Przykładowy plik Project** (`ReadWorkWeeksInformation.mpp`) umieszczony w znanym folderze na Twoim komputerze.

## Importowanie pakietów
Najpierw zaimportuj klasy, których będziemy potrzebować do interakcji z kalendarzami i tygodniami roboczymi:

`Project` reprezentuje plik Microsoft Project, `Calendar` udostępnia jego kalendarze, `WorkWeek` definiuje tydzień roboczy, a `WeekDay` reprezentuje dzień.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Krok 1: ustaw katalog danych
Zdefiniuj folder zawierający plik `.mpp`. Zastąp symbol zastępczy rzeczywistą ścieżką na swoim komputerze:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: utwórz instancję Project i uzyskaj dostęp do kalendarza
Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego struktur danych, w tym kalendarzy, zadań i zasobów.  
Utwórz obiekt `Project`, wybierz kalendarz, którego potrzebujesz (według UID), i pobierz jego `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Wskazówka:** Jeśli nie jesteś pewien UID kalendarza, przeiteruj `project.getCalendars()` i najpierw wypisz nazwę oraz UID każdego kalendarza.

## Krok 3: iteruj po tygodniach roboczych
Klasa `WorkWeek` kapsułkuje definicję tygodnia roboczego, zawierającą daty rozpoczęcia/zakończenia oraz dzienne ustawienia czasu pracy.  
Iteruj po każdym `WorkWeek`, aby wyświetlić jego nazwę, daty rozpoczęcia/zakończenia oraz dzienne godziny pracy:

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**Co zobaczysz:** Konsola wypisuje etykietę każdego tygodnia roboczego (np. „Standard”), jego obowiązujący zakres dat oraz umożliwia zagłębienie się w dokładne godziny pracy dla każdego dnia.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| `NullPointerException` przy dostępie do `calendar` | Nieprawidłowy UID lub kalendarz nie istnieje | Sprawdź UID przy pomocy `project.getCalendars().size()` i najpierw wyświetl dostępne kalendarze. |
| Brak wyjścia dla tygodni roboczych | Wybrany kalendarz nie ma niestandardowych tygodni roboczych (używa domyślnego) | Użyj domyślnego kalendarza (`project.getDefaultCalendar()`) lub utwórz tydzień roboczy programowo. |
| Format daty wygląda dziwnie | `System.out.println` używa domyślnego formatu `java.util.Date` | Zastosuj `SimpleDateFormat`, aby sformatować daty według potrzeb. |

## Najczęściej zadawane pytania
**P:** Czy mogę modyfikować informacje o tygodniach roboczych przy użyciu Aspose.Tasks for Java?  
**O:** Tak. API udostępnia `addWorkWeek()`, `removeWorkWeek()` oraz settery właściwości umożliwiające zmianę nazw, dat i godzin pracy.

**P:** Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?  
**O:** Zdecydowanie. Obsługuje pliki MPP od Project 98 aż po najnowsze wersje, a także pliki Project XML.

**P:** Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?  
**O:** Tak. Biblioteka jest czystą Javą, więc możesz jej używać razem ze Spring, Jakarta EE lub dowolnym innym frameworkiem.

**P:** Czy dostępna jest wersja próbna Aspose.Tasks?  
**O:** Tak, możesz pobrać darmową 30‑dniową wersję próbną ze strony: [Aspose.Tasks trial](https://releases.aspose.com/).

**P:** Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?  
**O:** Najlepszym miejscem jest forum społeczności Aspose: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2026-08-13  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Pobierz wyjątki kalendarza przy użyciu Aspose.Tasks – samouczek asp tasks java](/tasks/java/calendar-exceptions/retrieve/)
- [Jak ustawić kalendarz i zdefiniować dni tygodnia w MS Project przy użyciu Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}