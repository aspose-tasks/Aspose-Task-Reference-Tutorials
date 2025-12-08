---
date: 2025-12-05
description: Dowiedz się, jak określić dni robocze i obliczyć czas trwania zadania,
  wyodrębniając godziny pracy z kalendarzy MS Project przy użyciu Aspose.Tasks dla
  Javy.
language: pl
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Określ dni robocze i godziny pracy za pomocą Aspose.Tasks
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Określanie dni roboczych i godzin pracy przy użyciu Aspose.Tasks

## Wprowadzenie
Zarządzanie kalendarzami projektu jest kluczowym elementem udanego planowania. W tym samouczku **określisz dni robocze** dla dowolnego zadania i **pobierzesz godziny pracy** z kalendarza MS Project przy użyciu Aspose.Tasks for Java. Po zakończeniu będziesz mógł **obliczyć czas trwania zadania**, dostosować godziny pracy i niezawodnie **załadować plik MPP**, aby uzyskać potrzebne dane.

## Szybkie odpowiedzi
- **Co oznacza „określanie dni roboczych”?** Oznacza to identyfikację, które daty w kalendarzu są uznawane za dni robocze dla danego zadania.  
- **Którą bibliotekę powinienem użyć?** Aspose.Tasks for Java udostępnia w pełni funkcjonalne API do pracy z plikami MS Project.  
- **Jak długo trwa implementacja?** Zazwyczaj 10–15 minut dla podstawowego wyodrębnienia.  
- **Czy potrzebna jest licencja?** Dostępna jest darmowa wersja próbna; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Czy mogę dostosować godziny pracy?** Tak – możesz modyfikować kalendarze, dodawać święta i ustawiać własne przedziały czasu pracy.

## Co to jest „określanie dni roboczych”?
Gdy zadanie jest planowane, kalendarz projektu określa, które dni są dniami pracy, a które są dniami niepracującymi (weekendy, święta). Określanie dni roboczych oznacza zapytanie tego kalendarza, aby dokładnie wiedzieć, kiedy może odbywać się praca, co jest niezbędne do precyzyjnych obliczeń **calculate task duration**.

## Dlaczego warto używać Aspose.Tasks do pobierania godzin pracy?
- **Microsoft Project nie jest wymagany** – pracuj z plikami .MPP na dowolnej platformie.  
- **Pełne wsparcie kalendarzy** – obejmuje kalendarze domyślne, zasobów i zadań.  
- **Wysoka wydajność** – szybkie przetwarzanie dużych projektów.  
- **Obszerna dokumentacja** – przykłady i odniesienia API są łatwo dostępne.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z [tutaj](https://releases.aspose.com/tasks/java/).  
3. Podstawowa znajomość programowania w Javie.  

## Importowanie pakietów
Najpierw zaimportuj podstawowy pakiet Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Krok 1: Załaduj plik MPP
Załaduj plik projektu (krok **load mpp file**) aby móc pracować z jego kalendarzami:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Krok 2: Pobierz informacje o zadaniu i kalendarzu
Wybierz zadanie, które chcesz przeanalizować i pobierz jego powiązany kalendarz. To tutaj **retrieve working hours** dla zadania:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Krok 3: Zdefiniuj daty początkową i końcową
Ustaw przedział czasowy, dla którego chcesz **determine working days**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Krok 4: Iteruj przez daty
Iteruj przez każdą datę w trwania zadania. Ta pętla pomoże nam później **customize working hours**, jeśli będzie to potrzebne:

```java
java.util.Calendar tempDate = calStartDate;
```

## Krok 5: Oblicz czas trwania
Podczas iteracji sprawdzamy, czy każdy dzień jest dniem roboczym, sumujemy godziny pracy i ostatecznie obliczamy czas trwania zadania w minutach, godzinach i dniach:

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

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Zadanie zwraca `null` dla kalendarza** | Upewnij się, że zadanie ma przypisany kalendarz; w przeciwnym razie dziedziczy domyślny kalendarz projektu. |
| **Nieprawidłowy czas trwania z powodu świąt** | Sprawdź, czy święta są zdefiniowane w kalendarzu zadania lub w bazowym kalendarzu projektu. |
| **Niezgodność strefy czasowej** | Użyj `java.util.TimeZone`, aby dopasować strefę czasową kalendarza do systemu, jeśli to konieczne. |

## Najczęściej zadawane pytania
### P: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektów?
Odp: Tak, Aspose.Tasks for Java zapewnia kompleksowe wsparcie przy obsłudze złożonych struktur projektów, w tym zadań, zasobów i kalendarzy.

### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?
Odp: Zdecydowanie, Aspose.Tasks for Java obsługuje różne wersje MS Project, zapewniając kompatybilność w różnych środowiskach.

### P: Czy mogę dostosować godziny pracy i święta w kalendarzach projektu?
Odp: Tak, możesz łatwo dostosować godziny pracy i święta zgodnie z wymaganiami projektu, korzystając z API Aspose.Tasks for Java.

### P: Czy Aspose.Tasks for Java oferuje wsparcie i dokumentację?
Odp: Tak, Aspose.Tasks for Java udostępnia obszerną dokumentację oraz dedykowane fora wsparcia, aby pomóc programistom w efektywnym wykorzystaniu jego funkcji.

### P: Czy dostępna jest wersja próbna Aspose.Tasks for Java?
Odp: Tak, możesz uzyskać darmową wersję próbną Aspose.Tasks for Java z [tutaj](https://releases.aspose.com/).

## Zakończenie
W tym przewodniku pokazaliśmy, jak **determine working days**, **retrieve working hours** i **calculate task duration** z kalendarza MS Project przy użyciu Aspose.Tasks for Java. Postępując zgodnie z powyższymi krokami, możesz zautomatyzować analizę harmonogramu, dostosować kalendarze oraz utrzymać plany projektów dokładne i aktualne.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}