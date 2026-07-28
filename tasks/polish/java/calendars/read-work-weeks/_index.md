---
date: 2026-02-05
description: Dowiedz się, jak odczytywać tygodnie robocze w Javie z kalendarza Microsoft
  Project przy użyciu Aspose.Tasks. Postępuj zgodnie z przewodnikiem krok po kroku,
  zawierającym pełne przykłady kodu.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak odczytać tygodnie robocze w Javie z kalendarza MS Project przy użyciu Aspose.Tasks
url: /pl/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać tygodnie robocze Java z kalendarza MS Project przy użyciu Aspose.Tasks

## Wstęp
W tym samouczku **dowiesz się, jak odczytać tygodnie robocze Java** z kalendarza Microsoft Project przy użyciu biblioteki Aspose.Tasks. Niezależnie od tego, czy tworzysz narzędzie raportujące, synchronizujesz harmonogramy, czy automatyzujesz ekstrakcję danych projektowych, programowy dostęp do definicji tygodni roboczych oszczędza niezliczone godziny ręcznej pracy. Przeprowadzimy Cię przez niezbędną konfigurację, pokażemy dokładny kod pobierający szczegóły tygodni roboczych oraz wyjaśnimy każdy krok, abyś mógł dostosować rozwiązanie do własnych projektów.

## Szybkie odpowiedzi
- **Co oznacza „read workweeks java”?** Odwołuje się do wyodrębniania definicji tygodni roboczych z pliku Project przy użyciu kodu Java.  
- **Jakiej biblioteki potrzebuję?** Aspose.Tasks for Java (dostępna wersja próbna).  
- **Czy potrzebna jest licencja do rozwoju?** Wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie formaty plików są obsługiwane?** Obsługiwane są zarówno *.mpp*, jak i pliki Project XML.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut po skonfigurowaniu biblioteki.

## Jak odczytać tygodnie robocze Java z kalendarza Microsoft Project
Odczytywanie tygodni roboczych w Java oznacza użycie API Aspose.Tasks do uzyskania `WorkWeekCollection` obiektu kalendarza znajdującego się w pliku Microsoft Project. Każdy `WorkWeek` zawiera daty rozpoczęcia/zakończenia oraz dzienne definicje czasu pracy, które określają, jak zasoby są planowane.

## Dlaczego warto odczytywać tygodnie robocze Java z kalendarza Microsoft Project?
- **Automatyzacja:** Eliminacja ręcznego kopiowania danych harmonogramu.  
- **Integracja:** Dostarczanie informacji o tygodniach roboczych do systemów ERP, HR lub własnych systemów raportujących.  
- **Spójność:** Zapewnienie, że wszystkie narzędzia downstream respektują te same reguły kalendarza zdefiniowane w pliku Project.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub nowsza zainstalowana.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze strony: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. **Przykładowy plik Project** (`ReadWorkWeeksInformation.mpp`) umieszczony w znanym folderze.

## Import pakietów
Najpierw zaimportuj klasy, które będą potrzebne do pracy z kalendarzami i tygodniami roboczymi:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Krok 1: Ustaw katalog danych
Zdefiniuj folder zawierający plik `.mpp`. Zastąp symboliczny placeholder rzeczywistą ścieżką na swoim komputerze:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Utwórz instancję projektu i uzyskaj dostęp do kalendarza
Zainicjuj obiekt `Project`, wybierz kalendarz (przez UID) i pobierz jego `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Wskazówka:** Jeśli nie znasz UID kalendarza, możesz przeiterować `project.getCalendars()` i wypisać nazwę oraz UID każdego kalendarza.

## Krok 3: Iteruj przez tygodnie robocze
Przejdź pętlą po każdym `WorkWeek`, aby wyświetlić jego nazwę, daty rozpoczęcia/zakończenia oraz dzienne godziny pracy:

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

**Co zobaczysz:** Konsola wypisze etykietę każdego tygodnia roboczego (np. „Standard”), jego zakres dat oraz szczegółowe godziny pracy dla każdego dnia.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| `NullPointerException` przy dostępie do `calendar` | Nieprawidłowy UID lub kalendarz nie istnieje | Sprawdź UID przy pomocy `project.getCalendars().size()` i najpierw wyświetl dostępne kalendarze. |
| Brak wyjścia dla tygodni roboczych | Wybrany kalendarz nie ma niestandardowych tygodni (używa domyślnego) | Użyj kalendarza domyślnego (`project.getDefaultCalendar()`) lub utwórz tydzień roboczy programowo. |
| Format dat wygląda dziwnie | `System.out.println` używa domyślnego formatu `java.util.Date` | Zastosuj `SimpleDateFormat`, aby sformatować daty według potrzeb. |

## Najczęściej zadawane pytania

**P: Czy mogę modyfikować informacje o tygodniach roboczych przy użyciu Aspose.Tasks for Java?**  
O: Tak. API udostępnia metody takie jak `addWorkWeek()`, `removeWorkWeek()` oraz settery właściwości umożliwiające zmianę nazw, dat i godzin pracy.

**P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
O: Zdecydowanie. Obsługuje pliki MPP od Project 98 aż po najnowsze wersje, a także pliki Project XML.

**P: Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?**  
O: Tak. Biblioteka jest czystą Javą, więc możesz używać jej razem ze Spring, Jakarta EE lub dowolnym innym frameworkiem.

**P: Czy dostępna jest wersja próbna Aspose.Tasks?**  
O: Tak, możesz pobrać bezpłatną 30‑dniową wersję próbną ze strony: [Aspose.Tasks trial](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?**  
O: Najlepszym miejscem jest forum społeczności Aspose: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Zakończenie
Teraz opanowałeś **sposób odczytywania tygodni roboczych Java** przy użyciu Aspose.Tasks. Postępując zgodnie z powyższymi krokami, możesz programowo pobierać definicje tygodni roboczych z dowolnego kalendarza MS Project, integrować te dane w swoich aplikacjach i automatyzować procesy związane z harmonogramem. Śmiało eksperymentuj z tworzeniem lub aktualizacją tygodni roboczych — Aspose.Tasks czyni to prostym.

---

**Ostatnia aktualizacja:** 2026-02-05  
**Testowane z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}