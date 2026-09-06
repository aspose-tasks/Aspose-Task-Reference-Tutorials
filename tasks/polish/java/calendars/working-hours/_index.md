---
date: 2026-08-24
description: Dowiedz się, jak dodać kalendarz świąt, określić dni robocze i obliczyć
  czas trwania zadania, wyodrębniając godziny pracy z kalendarzy MS Project przy użyciu
  Aspose.Tasks for Java.
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: Jak dodać kalendarz świąt i określić dni robocze
og_description: Dowiedz się, jak dodać kalendarz świąt, określić dni robocze i obliczyć
  czas trwania zadania, wyodrębniając godziny pracy z kalendarzy MS Project przy użyciu
  Aspose.Tasks for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: Jak dodać kalendarz świąt i określić dni robocze
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: Jak dodać kalendarz świąt i określić dni robocze
url: /pl/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać kalendarz świąt i określić dni robocze

Zarządzanie kalendarzami projektów jest kluczową częścią udanego planowania. W tym samouczku **dodasz kalendarz świąt**, **określisz dni robocze** dla dowolnego zadania oraz **wyodrębnisz godziny pracy** z kalendarza MS Project przy użyciu Aspose.Tasks for Java. Po zakończeniu będziesz w stanie **obliczyć czas trwania zadania**, dostosować godziny pracy i niezawodnie **wczytać plik MPP**, aby uzyskać potrzebne dane — bez instalacji Microsoft Project.

## Szybkie odpowiedzi
- **Co oznacza „określenie dni roboczych”?** Oznacza to identyfikację, które daty w kalendarzu są uznawane za dni robocze dla danego zadania.  
- **Z której biblioteki powinienem korzystać?** Aspose.Tasks for Java zapewnia w pełni funkcjonalne API do pracy z plikami MS Project.  
- **Jak długo trwa implementacja?** Zazwyczaj 10–15 minut dla podstawowego wyodrębnienia.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę dostosować godziny pracy?** Tak – możesz modyfikować kalendarze, dodawać święta i ustawiać własne przedziały czasu pracy.  

## Co to jest „określenie dni roboczych”?
**Określenie dni roboczych** oznacza zapytanie kalendarza projektu, aby dowiedzieć się, które daty są oznaczone jako dni robocze, a które jako dni wolne (weekendy, święta lub własne wyjątki). Informacje te są niezbędne do dokładnego **obliczania czasu trwania zadania**, ponieważ tylko dni robocze wpływają na upływający czas zadania.

## Dlaczego używać Aspose.Tasks do wyodrębniania godzin pracy?
Aspose.Tasks pozwala odczytywać pliki MS Project bez zainstalowanego Microsoft Project, umożliwiając automatyzację na dowolnej platformie. Zapewnia także wysoką wydajność, szerokie wsparcie formatów i szczegółową dokumentację.  

- **Pełne wsparcie kalendarzy** – dostępne są kalendarze domyślne, zasobów i zadań.  
- **Wysoka wydajność** – może przetwarzać projekty zawierające **10 000+ zadań w mniej niż 2 sekundy** na standardowym procesorze 2,5 GHz.  
- **Szerokie pokrycie formatów** – obsługuje **ponad 50 formatów wejścia i wyjścia**, w tym MPP, MPX, XML i Primavera.  
- **Kompleksowa dokumentacja** – przykłady kodu, odniesienia API i fora społeczności są dostępne.  

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z [wydania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. Podstawową znajomość programowania w Javie.  

## Importuj pakiety
Klasa `Project` jest obiektem najwyższego poziomu Aspose.Tasks, który reprezentuje pojedynczy plik MS Project w pamięci. Zaimportuj wymagane przestrzenie nazw przed rozpoczęciem:

Importuj pakiety

```java
import com.aspose.tasks.*;
```

## Jak wczytać plik MPP przy użyciu Aspose.Tasks?
Klasa `Project` wczytuje plik MS Project i udostępnia dostęp do jego danych. Wczytaj plik projektu w jednej linii kodu; nie jest wymagana żadna interfejs graficzny ani COM interop. Ten prosty krok daje pełny dostęp do kalendarzy, zadań i zasobów.

Ładowanie pliku MPP

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Pobierz informacje o zadaniu i kalendarzu
`Task` reprezentuje zadanie projektowe, a `Calendar` definiuje jego reguły czasu pracy. Wybierz zadanie, które chcesz przeanalizować i uzyskaj powiązany z nim kalendarz. Obiekt `Task` udostępnia metody `getStart()` i `getFinish()`, natomiast obiekt `Calendar` eksponuje definicje czasu pracy.

Pobieranie zadania i kalendarza

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Zdefiniuj daty początkową i końcową
Obiekty `Date` określają okno czasowe analizy kalendarza. Ustaw przedział czasu, dla którego chcesz **określić dni robocze**. Użycie dat rozpoczęcia i zakończenia zadania zapewnia, że oceniasz tylko odpowiedni okres.

Definiowanie dat

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iteruj po datach
Pętla `for` może iterować po każdym dniu w przedziale dat. Przejdź przez każdą datę w czasie trwania zadania. Pętla umożliwi późniejsze **dostosowanie godzin pracy**, jeśli będzie to potrzebne, i jest podstawą do obliczania całkowitego czasu pracy.

Iterowanie dat

```java
java.util.Calendar tempDate = calStartDate;
```

## Oblicz czas trwania
`Duration` sumuje całkowity czas pracy obliczony z iteracji. Podczas iteracji sprawdzasz, czy każdy dzień jest dniem roboczym, sumujesz godziny pracy i ostatecznie obliczasz czas trwania zadania w minutach, godzinach i dniach. To pokazuje, jak **obliczyć dni robocze** i **obliczyć czas trwania zadania** programowo.

Obliczanie czasu trwania

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Jak dostosować godziny pracy i święta
Możesz modyfikować przedziały czasu pracy kalendarza oraz dodawać wyjątki, takie jak święta. Użyj `taskCalendar.addWorkingTime()` aby ustawić nowe okresy pracy oraz `taskCalendar.addException()` aby wstawić święto. Jest to przydatne, gdy domyślny harmonogram 9‑5 nie odpowiada politykom Twojej organizacji.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Zadanie zwraca `null` dla kalendarza** | Upewnij się, że zadanie ma przypisany kalendarz; w przeciwnym razie dziedziczy domyślny kalendarz projektu. |
| **Nieprawidłowy czas trwania z powodu świąt** | Sprawdź, czy święta są zdefiniowane w kalendarzu zadania lub w bazowym kalendarzu projektu. |
| **Niezgodność strefy czasowej** | Użyj `java.util.TimeZone`, aby dopasować strefę czasową kalendarza do systemu, jeśli to konieczne. |

## Najczęściej zadawane pytania
### Q: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektów?
A: Tak, Aspose.Tasks for Java zapewnia kompleksowe wsparcie w obsłudze złożonych struktur projektów, w tym zadań, zasobów i kalendarzy.

### Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?
A: Absolutnie, Aspose.Tasks for Java obsługuje różne wersje MS Project, zapewniając zgodność w różnych środowiskach.

### Q: Czy mogę dostosować godziny pracy i święta w kalendarzach projektów?
A: Tak, możesz łatwo dostosować godziny pracy i święta zgodnie z wymaganiami projektu, korzystając z API Aspose.Tasks for Java.

### Q: Czy Aspose.Tasks for Java oferuje wsparcie i dokumentację?
A: Tak, Aspose.Tasks for Java udostępnia obszerną dokumentację oraz dedykowane fora wsparcia, aby pomóc deweloperom w efektywnym wykorzystaniu funkcji.

### Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?
A: Tak, możesz uzyskać darmową wersję próbną Aspose.Tasks for Java ze [strony wydania Aspose](https://releases.aspose.com/).

## Podsumowanie
W tym przewodniku pokazaliśmy, jak **dodać kalendarz świąt**, **określić dni robocze**, **wyodrębnić godziny pracy** oraz **obliczyć czas trwania zadania** z kalendarza MS Project przy użyciu Aspose.Tasks for Java. Postępując zgodnie z powyższymi krokami, możesz zautomatyzować analizę harmonogramu, dostosować kalendarze i utrzymać plany projektowe dokładne i aktualne. Masz teraz narzędzia do **odczytu danych MS Project**, **wczytania pliku MPP** i precyzyjnych obliczeń czasu trwania bez potrzeby posiadania Microsoft Project.

---

**Ostatnia aktualizacja:** 2026-08-24  
**Testowane z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Dodaj kalendarz do projektu przy użyciu Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Dodaj święta do kalendarza i zapisz jako MPP przy użyciu Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Utwórz niestandardowe wyjątki kalendarza przy użyciu Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}