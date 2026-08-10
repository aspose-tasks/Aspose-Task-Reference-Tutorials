---
date: 2026-08-03
description: Dowiedz się, jak utworzyć kalendarz ms project, dodać kalendarz do projektu
  i zapisać projekt jako XML przy użyciu Aspose.Tasks dla Java.
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: Dodaj kalendarz do projektu przy użyciu Aspose.Tasks
og_description: Utwórz kalendarz ms project programowo przy użyciu Aspose.Tasks dla
  Java. Dodaj kalendarze, dostosuj harmonogramy i wyeksportuj do XML w kilka minut.
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: Utwórz kalendarz ms project przy użyciu Aspose.Tasks dla Java
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: Utwórz kalendarz ms project przy użyciu Aspose.Tasks dla Java
url: /pl/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kalendarz MS Project przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W nowoczesnych przepływach pracy zarządzania projektami możliwość **utworzyć kalendarz ms project** programowo może zaoszczędzić godziny ręcznej edycji. Aspose.Tasks for Java zapewnia czyste, typowo‑bezpieczne API do manipulacji plikami Microsoft Project bez konieczności otwierania klienta desktopowego. W tym samouczku dowiesz się, jak dodać kalendarz, jak utworzyć kalendarz MS Project oraz jak zapisać projekt jako XML — wszystko przy użyciu kilku linii kodu Java.

## Szybkie odpowiedzi
- **Co oznacza „create ms project calendar”?**  
  Oznacza to wstawienie nowej definicji czasu pracy (kalendarza) do pliku Microsoft Project za pomocą kodu.  
- **Która biblioteka to obsługuje?**  
  Aspose.Tasks for Java udostępnia klasę `Calendar` oraz kontener `Project` do zarządzania kalendarzami.  
- **Czy potrzebna jest licencja?**  
  Tymczasowa licencja ewaluacyjna działa w testach; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zapisać plik jako XML?**  
  Tak — użyj `SaveFileFormat.Xml`, aby wyeksportować projekt jako plik XML.  
- **Jakie są wymagania wstępne?**  
  Java JDK 8+ oraz plik JAR Aspose.Tasks for Java w classpath.

## Czym jest create ms project calendar?
Utworzenie kalendarza MS Project oznacza programowe dodanie nowej definicji kalendarza do pliku projektu, określenie dni roboczych, wyjątków i dziennych godzin pracy, a następnie przypisanie tego kalendarza do zadań, zasobów lub całego projektu, aby obliczenia harmonogramu uwzględniały zdefiniowany czas pracy.

## Dlaczego używać Aspose.Tasks for Java do dodania kalendarza do projektu?
Powinieneś używać Aspose.Tasks for Java, ponieważ zapewnia w pełni typowo‑bezpieczne API działające bez zainstalowanego Microsoft Project, obsługuje wszystkie główne wersje Project (2007‑2021, ponad 5 wydań) oraz może eksportować do XML, MPP i **10+** innych formatów, umożliwiając automatyczne masowe tworzenie kalendarzy na dowolnym serwerze.

## Wymagania wstępne
- **Java Development Kit (JDK) 8 lub nowszy** zainstalowany i skonfigurowany.  
- **Aspose.Tasks for Java** – pobierz z [official website](https://releases.aspose.com/tasks/java/) i dodaj plik JAR do classpath projektu.  
- IDE lub narzędzie budujące (Maven/Gradle) według własnego wyboru.

## Przewodnik krok po kroku

### Krok 1: zaimportuj wymagany pakiet Aspose.Tasks
Najpierw wprowadź klasy Aspose.Tasks do zakresu, aby móc pracować z projektami i kalendarzami.

```java
import com.aspose.tasks.*;
```

### Krok 2: ustaw ścieżkę katalogu danych
Zdefiniuj, gdzie zostanie zapisany wygenerowany plik projektu. Zamień symbol zastępczy na absolutną lub względną ścieżkę na swoim komputerze.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: utwórz nową instancję Project
`Project` to podstawowa klasa reprezentująca plik Microsoft Project w pamięci.

```java
Project prj = new Project();
```

### Krok 4: zdefiniuj kalendarze, które chcesz dodać
`Calendar` definiuje harmonogram z dniami roboczymi, wyjątkami i godzinami pracy dla projektu.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Wskazówka:** Po dodaniu kalendarza możesz dostosować jego dni robocze za pomocą `cal1.getWeekDays().add(...)` oraz ustawić dzienne godziny pracy przy użyciu `cal1.getBaseCalendar().setWorkingTime(...)`.

### Krok 5: zapisz projekt (zapisz projekt jako XML)
`SaveFileFormat.Xml` mówi Aspose.Tasks, aby zapisał projekt w formacie XML.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 6: wyświetl komunikat o zakończeniu
Poinformuj użytkownika, że operacja zakończyła się pomyślnie.

```java
System.out.println("Process completed Successfully");
```

Postępując zgodnie z tymi sześcioma zwięzłymi krokami, pomyślnie **dodałeś kalendarz do projektu** i zapisałeś wynik jako plik XML.

## Typowe problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| **`NullPointerException` on `prj.getCalendars()`** | Obiekt projektu nie został poprawnie zainicjowany. | Upewnij się, że wywołano `new Project()` przed dostępem do kalendarzy. |
| **File not found when saving** | `dataDir` wskazuje na nieistniejący folder. | Utwórz katalog najpierw lub użyj ścieżki absolutnej. |
| **Calendar name appears as “no info”** | W przykładzie użyto nazw zastępczych. | Zamień je na znaczące nazwy odzwierciedlające harmonogram (np. „Kalendarz Świąt USA”). |
| **Saved XML cannot be opened in MS Project** | Używana jest przestarzała wersja Aspose.Tasks. | Zaktualizuj do najnowszej wersji Aspose.Tasks for Java. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks może obsługiwać złożone kalendarze z wieloma wyjątkami?**  
A: Tak — po dodaniu kalendarza możesz definiować wyjątki, godziny pracy i dni wolne przy użyciu klas `WeekDay` i `Exception`.

**Q: Czy można przypisać nowy kalendarz do konkretnych zadań?**  
A: Oczywiście. Pobierz zadanie poprzez `prj.getRootTask().getChildren().add("Task Name")` i ustaw `task.set(Tsk.CALENDAR, cal3);`.

**Q: Czy biblioteka obsługuje zapisy w innych formatach, takich jak MPP?**  
A: Tak. Zamień `SaveFileFormat.Xml` na `SaveFileFormat.Mpp` lub `SaveFileFormat.P6` w zależności od potrzeb; Aspose.Tasks obsługuje **12** formatów wyjściowych.

**Q: Czy potrzebna jest licencja do wersji deweloperskich?**  
A: Tymczasowa licencja ewaluacyjna wystarczy do testów; pełna licencja jest wymagana przy wdrożeniach produkcyjnych.

**Q: Gdzie mogę uzyskać pomoc w razie problemów?**  
A: Forum społeczności Aspose.Tasks jest doskonałym źródłem: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2026-08-03  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak definiować dni tygodnia w kalendarzach MS Project – Aspose.Tasks Java](/tasks/java/calendars/)
- [Jak ustawić kalendarz projektu w Javie przy użyciu Aspose.Tasks](/tasks/java/calendars/properties/)
- [Utwórz własne wyjątki kalendarza przy użyciu Aspose.Tasks dla Javy](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}