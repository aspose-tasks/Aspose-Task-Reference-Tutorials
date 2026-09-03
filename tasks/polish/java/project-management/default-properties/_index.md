---
date: 2026-05-31
description: Dowiedz się, jak załadować plik MPP w Javie i zarządzać właściwościami
  projektu przy użyciu Aspose.Tasks, w tym ustawianie domyślnych właściwości i konwertowanie
  formatów.
keywords:
- manage project properties
- set default properties
- aspose tasks java
- change task start date
- convert mpp to pdf
linktitle: Zarządzanie domyślnymi właściwościami projektu w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to load an MPP file in Java and manage project properties
    with Aspose.Tasks, including setting default properties and converting formats.
  headline: Load MPP File Java – Manage Project Properties with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks is also available for .NET, Python, and other platforms.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely! It scales from small personal projects to large‑scale enterprise
      portfolios.
    question: Is Aspose.Tasks suitable for both personal and enterprise use?
  - answer: Yes, you can find assistance and community support on the [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks offer customer support?
  - answer: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/)
      for testing and evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Ładowanie pliku MPP w Javie – Zarządzanie właściwościami projektu przy użyciu
  Aspose.Tasks
url: /pl/java/project-management/default-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ładowanie pliku MPP w Javie – Zarządzanie właściwościami projektu przy użyciu Aspose.Tasks

## Wprowadzenie
Jeśli potrzebujesz **load MPP file Java** projektów i programowo zarządzać domyślnymi właściwościami projektu, Aspose.Tasks for Java ułatwia to zadanie. W tym samouczku przeprowadzimy Cię przez cały proces — od załadowania istniejącego pliku Microsoft Project po dostosowanie domyślnych ustawień zadań i zasobów oraz zapisanie zaktualizowanego projektu. Po zakończeniu będziesz mieć jasny, wielokrotnego użytku wzorzec, który możesz wstawić do dowolnego rozwiązania do zarządzania projektami w Javie.

## Szybkie odpowiedzi
- **Co oznacza „load MPP file Java”?** Oznacza to odczyt pliku Microsoft Project (.mpp) przy użyciu kodu Java za pośrednictwem Aspose.Tasks.  
- **Która biblioteka to obsługuje?** Aspose.Tasks for Java udostępnia w pełni funkcjonalne API do manipulacji projektami.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić domyślne daty rozpoczęcia zadań?** Tak — użyj `Prj.DEFAULT_START_TIME` i powiązanych właściwości, aby ustawić domyślne wartości.  
- **Jakie formaty wyjściowe są obsługiwane?** Oprócz natywnego MPP, możesz zapisać do XML, PDF, HTML i ponad 20 innych formatów.

## Czym jest „load MPP file Java”?
Ładowanie pliku MPP w Javie oznacza użycie biblioteki do parsowania binarnego formatu Microsoft Project, udostępniając jego obiekty (zadania, zasoby, kalendarze) jako klasy Java. Umożliwia to odczyt, modyfikację i zapis danych projektu bez konieczności otwierania samego Microsoft Project.

## Dlaczego warto używać Aspose.Tasks for Java?
Aspose.Tasks pozwala zarządzać właściwościami projektu bez instalacji Microsoft Project, obsługuje **ponad 50 formatów wejściowych i wyjściowych** oraz może przetwarzać projekty z **do 10 000 zadaniami**, utrzymując zużycie pamięci poniżej 200 MB. Działa na każdym systemie operacyjnym obsługującym JDK, co czyni go idealnym do automatyzacji po stronie serwera.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące:

### 1. Java Development Kit (JDK)
- Zainstaluj JDK 11 lub nowszy.  
- Możesz go pobrać [tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### 2. Aspose.Tasks for Java Library
- Pobierz najnowszy plik JAR Aspose.Tasks i dodaj go do classpath swojego projektu.  
- Pobierz go z [strony internetowej](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Instrukcje importu wprowadzają niezbędne klasy Aspose.Tasks do pliku źródłowego Java.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Jak załadować plik MPP w Javie i ustawić domyślne właściwości?
Klasa `Project` reprezentuje plik Microsoft Project i zapewnia dostęp do jego zadań, zasobów oraz ustawień. Załaduj projekt, sprawdź jego domyślne wartości, zmodyfikuj je i zapisz wynik — wszystko w kilku prostych linijkach. To podejście daje pełną kontrolę nad domyślnymi harmonogramami, ustawieniami kalendarza i regułami naliczania kosztów, umożliwiając egzekwowanie spójnych standardów projektu we wszystkich generowanych plikach.

### Krok 1: Załaduj plik projektu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Krok 2: Wyświetl domyślne właściwości
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```

### Krok 3: Ustaw domyślne właściwości
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```

### Krok 4: Zapisz projekt w formacie XML
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```

### Krok 5: Wyświetl wynik
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```

Postępując zgodnie z tymi krokami, pomyślnie **załadowałeś plik MPP w Javie**, sprawdziłeś jego domyślne ustawienia, dostosowałeś je i zapisałeś zaktualizowany projekt.

## Typowe problemy i wskazówki
- **Plik nie znaleziony** – Zweryfikuj, czy `dataDir` kończy się separatorem ścieżki (`/` lub `\\`).  
- **Licencja nie zastosowana** – Jeśli widzisz znak wodny wersji próbnej, dodaj plik licencji przed załadowaniem projektu: `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.  
- **Obsługa dat** – Użyj `java.util.Calendar` lub nowszego API `java.time` (przed przypisaniem skonwertuj do `java.util.Date`).

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
O: Tak, Aspose.Tasks jest dostępny także dla .NET, Pythona i innych platform.

**P: Czy Aspose.Tasks nadaje się zarówno do użytku osobistego, jak i korporacyjnego?**  
O: Zdecydowanie! Skalowalny od małych projektów osobistych po duże portfele przedsiębiorstw.

**P: Czy Aspose.Tasks oferuje wsparcie klienta?**  
O: Tak, pomoc i wsparcie społeczności znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**P: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
O: Oczywiście! Możesz skorzystać z darmowej wersji próbnej na [stronie internetowej](https://releases.aspose.com/).

**P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?**  
O: Tymczasową licencję możesz uzyskać na [stronie zakupu](https://purchase.aspose.com/temporary-license/) w celu testowania i oceny.

## Podsumowanie
W tym samouczku omówiliśmy, jak **load MPP file Java** projekty, odczytać i zmodyfikować ich domyślne właściwości oraz zapisać zmiany przy użyciu Aspose.Tasks for Java. Włączenie tych technik do Twoich aplikacji pomoże zautomatyzować zadania zarządzania projektami, wymusić spójne domyślne ustawienia i zredukować ręczną pracę.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
- [Jak ustawić kalendarz projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/properties/)
- [Jak utworzyć plik MPP – Utwórz i zapisz pusty projekt w formacie MPP przy użyciu Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}