---
date: 2026-08-13
description: Dowiedz się, jak dodać dni wolne do kalendarza, przypisać kalendarz do
  projektu oraz zapisać plik MS Project jako MPP przy użyciu Aspose.Tasks for Java.
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Zaktualizuj kalendarz do formatu MPP w Aspose.Tasks
og_description: Dodaj dni wolne do kalendarza, przypisz go do projektu i przekształć
  harmonogram na MPP przy użyciu Aspose.Tasks for Java. Dowiedz się, jak zautomatyzować
  proces krok po kroku.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Dodaj dni wolne do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: Dodaj dni wolne do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks
url: /pl/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj święta do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks

## Wprowadzenie

We współczesnym zarządzaniu projektami często trzeba **add holidays to calendar** plików, utworzyć **MS Project calendar**, i następnie udostępnić harmonogram w natywnym formacie MPP. Niezależnie od tego, czy konsolidujesz harmonogramy z wielu źródeł, czy migrujesz starsze dane, programowe generowanie kalendarza eliminuje błędy ręczne i przyspiesza realizację. Ten samouczek przeprowadzi Cię przez cały proces tworzenia kalendarza w MS Project, dostosowywania go za pomocą świąt, **assign calendar to project**, a w końcu **convert project to MPP** przy użyciu Aspose.Tasks Java API.

## Szybkie odpowiedzi
- **Co obejmuje ten samouczek?** Dodawanie świąt do kalendarza, przypisywanie go do projektu i zapisywanie wyniku jako plik MPP przy użyciu Aspose.Tasks for Java.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakiej wersji Java wymaga się?** Java 8 lub wyższa (JDK 8+).  
- **Czy mogę dostosować kalendarz?** Tak – możesz dodać godziny pracy, wyjątki i święta.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego kalendarza.  

## Co to jest „create calendar MS Project”?

Tworzenie kalendarza MS Project oznacza definiowanie dni roboczych, godzin i wyjątków, które sterują planowaniem zadań w pliku Microsoft Project. Korzystając z Aspose.Tasks możesz programowo zbudować ten kalendarz, ustawić święta i osadzić go w projekcie bez otwierania interfejsu MS Project.

## Dlaczego używać Aspose.Tasks do tego zadania?

Powinieneś używać Aspose.Tasks, ponieważ oferuje pełną kompatybilność z Javą, nie wymaga Microsoft Office i pozwala generować oraz zapisywać natywne pliki MPP bezpośrednio z kodu. Biblioteka obsługuje wszystkie funkcje kalendarza, działa w dowolnym środowisku serwerowym i przetwarza projekty zawierające do 10 000 zadań w czasie krótszym niż sekunda.

## Wymagania wstępne

1. **Java Development Kit (JDK) 8+** – upewnij się, że `java -version` zwraca 1.8 lub nowszą wersję.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony Aspose](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor, którego używasz.  
4. **Podstawowa znajomość Javy** – znajomość klas, metod i operacji I/O na plikach.  

## Jak dodać święta do kalendarza

Aby dodać święta, tworzysz nowy obiekt `Calendar`, pobierasz jego kolekcję `Exceptions` i dodajesz wpisy `DateException` dla każdej daty święta. `DateException` reprezentuje pojedynczą niepracującą datę lub zakres w kalendarzu. Aspose.Tasks traktuje te daty jako dni wolne, zapewniając, że zadania są planowane wokół zdefiniowanych świąt.

### Krok 1: import wymaganych pakietów

Najpierw wprowadź klasy Aspose.Tasks oraz narzędzia Java do zakresu.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Krok 2: ustaw katalog danych

Określ, gdzie będą przechowywane szablony wejściowe i pliki wyjściowe. Zastąp symbol zastępczy rzeczywistą ścieżką na swoim komputerze.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: zdefiniuj nazwy plików wejściowych i wyjściowych

Wczytamy istniejący plik MPP (lub pusty projekt) i zapisujemy wynik do nowego pliku.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Krok 4: wczytaj projekt i dodaj nowy kalendarz

`Project` to klasa reprezentująca plik MS Project w pamięci i zapewnia dostęp do jego kalendarzy, zadań i zasobów.

Utwórz instancję `Project` z pliku źródłowego i dodaj kalendarz o nazwie **„Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Krok 5: dostosuj kalendarz (opcjonalnie)

Obiekt `Calendar` definiuje dni robocze, godziny i wyjątki dla harmonogramu projektu.

Jeśli potrzebujesz określonych godzin pracy, świąt lub wyjątków, wywołaj własną metodę pomocniczą. Przykład używa `GetTestCalendar` jako symbolu zastępczego.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** Możesz bezpośrednio manipulować `cal1.getWeekDays()`, aby ustawić godziny pracy dla każdego dnia tygodnia, lub użyć `cal1.getExceptions()`, aby **add holidays to calendar**.

### Krok 6: przypisz kalendarz do projektu

Powiedz projektowi, aby używał nowo utworzonego kalendarza do wszystkich obliczeń harmonogramu.

```java
project.set(Prj.CALENDAR, cal1);
```

### Krok 7: zapisz projekt jako MPP

`SaveFileFormat` to wyliczenie określające format wyjściowy, przy czym `Mpp` wskazuje natywny format Microsoft Project.

Teraz **convert project to MPP** zapisując go z opcją `SaveFileFormat.Mpp`.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Krok 8: potwierdź pomyślne zakończenie

Prosta wiadomość w konsoli informuje, że proces zakończył się bez błędów.

```java
System.out.println("Process completed Successfully");
```

## Typowe przypadki użycia

- **Automated schedule generation** dla powtarzających się projektów (np. tygodniowe sprinty).  
- **Migrating legacy CSV or Excel calendars** do w pełni funkcjonalnego pliku MS Project.  
- **Server‑side reporting** gdzie usługa sieciowa zwraca plik MPP na żądanie.  

## Rozwiązywanie problemów i typowe pułapki

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` przy `project.save` | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub utwórz go programowo. |
| Kalendarz nie zastosowany do zadań | Zadania nadal odwołują się do domyślnego kalendarza | Po ustawieniu `Prj.CALENDAR` zaktualizuj również `Task.CALENDAR` każdego zadania, jeśli zostały wcześniej nadpisane. |
| Plik wyjściowy ma 0 KB | Brak uprawnień do zapisu | Uruchom JVM z odpowiednimi uprawnieniami do systemu plików lub wybierz ścieżkę zapisu. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?**  
A: Tak, Aspose.Tasks obsługuje wszystkie formaty plików Microsoft Project od wersji Project 2007 do Project 2024, obejmując ponad 10 wersji.

**Q: Czy mogę dostosować kalendarze do konkretnych wymagań projektu?**  
A: Oczywiście. Możesz definiować dni robocze, ustawiać niestandardowe tygodnie pracy, dodawać święta i nawet tworzyć wiele kalendarzy w jednym pliku projektu.

**Q: Czy Aspose.Tasks for Java oferuje wsparcie w rozwiązywaniu problemów i pomoc?**  
A: Tak, możesz uzyskać pomoc na forum społeczności Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?**  
A: Tak, w pełni funkcjonalna wersja próbna jest dostępna [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?**  
A: Tymczasowe licencje można zamówić poprzez stronę Aspose [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

**Ostatnia aktualizacja:** 2026-08-13  
**Testowane z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Jak zdefiniować dni tygodnia w kalendarzach MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Utwórz niestandardowe wyjątki kalendarza przy użyciu Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}