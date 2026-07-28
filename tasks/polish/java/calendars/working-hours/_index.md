---
date: 2026-02-05
description: Dowiedz się, jak określić dni robocze i obliczyć czas trwania zadania,
  wyodrębniając godziny pracy z kalendarzy MS Project przy użyciu Aspose.Tasks dla
  Javy.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Określ dni robocze i godziny pracy z Aspose.Tasks
url: /pl/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Określanie dni roboczych i godzin pracy przy użyciu Aspose.Tasks

## Wprowadzenie
Zarządzanie kalendarzami projektów jest kluczową częścią skutecznego planowania projektu. W tym samouczku **określisz dni robocze** dla dowolnego zadania i **wyodrębnisz godziny pracy** z kalendarza MS Project przy użyciu Aspose.Tasks dla Javy. Po zakończeniu przewodnika będziesz w stanie **obliczyć czas trwania zadania**, dostosować godziny pracy oraz niezawodnie **załadować plik MPP**, aby uzyskać potrzebne dane. Zobaczysz także, jak **czytać pliki MS Project** bez zainstalowanego Microsoft Project, co umożliwia automatyzację na dowolnej platformie.

## Szybkie odpowiedzi
- **Co oznacza „określanie dni roboczych”?** Oznacza to identyfikację, które daty w kalendarzu są uznawane za dni pracy dla danego zadania.  
- **Którą bibliotekę powinienem używać?** Aspose.Tasks for Java udostępnia w pełni funkcjonalne API do pracy z plikami MS Project.  
- **Jak długo trwa implementacja?** Zazwyczaj 10–15 minut dla podstawowego wyodrębnienia.  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna; licencja komercyjna jest wymagana do użytku produkcyjnego.  
- **Czy mogę dostosować godziny pracy?** Tak – możesz modyfikować kalendarze, dodawać święta i ustawiać własne przedziały czasu pracy.  

## Co to jest „określanie dni roboczych”?
Gdy zadanie jest planowane, kalendarz projektu określa, które dni są dniami pracy, a które są dniami niepracującymi (weekendy, święta). Określanie dni roboczych oznacza zapytanie tego kalendarza, aby dokładnie wiedzieć, kiedy może odbywać się praca, co jest niezbędne do precyzyjnych obliczeń **calculate task duration**.

## Dlaczego używać Aspose.Tasks do pobierania godzin pracy?
- **Nie wymaga Microsoft Project** – możesz odczytywać pliki MS Project bezpośrednio z kodu Java.  
- **Pełne wsparcie kalendarzy** – obejmuje kalendarze domyślne, zasobów i zadań.  
- **Wysoka wydajność** – szybkie przetwarzanie dużych projektów.  
- **Obszerna dokumentacja** – przykłady i odniesienia API są łatwo dostępne.  

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z [tutaj](https://releases.aspose.com/tasks/java/).  
3. Podstawowa znajomość programowania w Javie.  

## Importowanie pakietów
Najpierw zaimportuj podstawowy namespace Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Jak załadować plik MPP przy użyciu Aspose.Tasks?
Załadowanie pliku projektu jest pierwszym krokiem do każdej analizy kalendarza. API pozwala **załadować plik MPP** w jednej linii kodu, bez potrzeby interfejsu MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Pobieranie informacji o zadaniu i kalendarzu
Wybierz zadanie, które chcesz przeanalizować i pobierz jego powiązany kalendarz. To tutaj **pobieramy godziny pracy** dla zadania:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definiowanie dat początkowej i końcowej
Ustaw przedział czasowy, dla którego chcesz **określić dni robocze**. Użycie daty rozpoczęcia i zakończenia zadania zapewnia, że oceniasz tylko odpowiedni okres.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterowanie przez daty
Iteruj przez każdą datę w czasie trwania zadania. Ta pętla pomoże nam później **dostosować godziny pracy**, jeśli będzie to potrzebne:

```java
java.util.Calendar tempDate = calStartDate;
```

## Obliczanie czasu trwania
Podczas iteracji sprawdzamy, czy każdy dzień jest dniem roboczym, sumujemy godziny pracy i ostatecznie obliczamy czas trwania zadania w minutach, godzinach i dniach. Ten krok pokazuje, jak programowo **obliczyć dni robocze** i **obliczyć czas trwania zadania**.

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
Aspose.Tasks umożliwia modyfikację zakresów czasu pracy w kalendarzu oraz dodawanie wyjątków, takich jak święta. Możesz wywołać `taskCalendar.addWorkingTime()` lub `taskCalendar.addException()`, aby dostosować harmonogram do polityk Twojej organizacji. Jest to przydatne, gdy domyślny harmonogram 9‑17 nie odzwierciedla rzeczywistości.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Zadanie zwraca `null` dla kalendarza** | Upewnij się, że zadanie ma przypisany kalendarz; w przeciwnym razie dziedziczy domyślny kalendarz projektu. |
| **Nieprawidłowy czas trwania z powodu świąt** | Sprawdź, czy święta są zdefiniowane w kalendarzu zadania lub w bazowym kalendarzu projektu. |
| **Niezgodność strefy czasowej** | Użyj `java.util.TimeZone`, aby dopasować strefę czasową kalendarza do systemu, jeśli to konieczne. |

## Najczęściej zadawane pytania
### Q: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektu?
A: Tak, Aspose.Tasks for Java zapewnia kompleksowe wsparcie dla obsługi złożonych struktur projektów, w tym zadań, zasobów i kalendarzy.

### Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami MS Project?
A: Zdecydowanie, Aspose.Tasks for Java obsługuje różne wersje MS Project, zapewniając kompatybilność w różnych środowiskach.

### Q: Czy mogę dostosować godziny pracy i święta w kalendarzach projektu?
A: Tak, możesz łatwo dostosować godziny pracy i święta zgodnie z wymaganiami projektu, używając API Aspose.Tasks for Java.

### Q: Czy Aspose.Tasks for Java oferuje wsparcie i dokumentację?
A: Tak, Aspose.Tasks for Java udostępnia obszerną dokumentację oraz dedykowane fora wsparcia, aby pomóc programistom w efektywnym wykorzystaniu funkcji.

### Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?
A: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks for Java z [tutaj](https://releases.aspose.com/).

## Podsumowanie
W tym przewodniku pokazaliśmy, jak **określić dni robocze**, **pobrać godziny pracy** oraz **obliczyć czas trwania zadania** z kalendarza MS Project przy użyciu Aspose.Tasks dla Javy. Postępując zgodnie z powyższymi krokami, możesz automatyzować analizę harmonogramu, dostosowywać kalendarze i utrzymywać plany projektów w dokładnym i aktualnym stanie. Masz teraz narzędzia, aby **czytać dane MS Project**, **załadować plik MPP** i wykonywać precyzyjne obliczenia czasu trwania bez potrzeby posiadania Microsoft Project.

---

**Last Updated:** 2026-02-05  
**Testowano z:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}