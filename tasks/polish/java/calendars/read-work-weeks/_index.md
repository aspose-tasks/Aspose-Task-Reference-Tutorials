---
date: 2025-12-03
description: Dowiedz się, jak odczytywać tygodnie robocze w Javie z kalendarza Microsoft
  Project przy użyciu Aspose.Tasks. Postępuj zgodnie z przewodnikiem krok po kroku
  z pełnymi przykładami kodu.
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Odczyt tygodni roboczych w Javie z kalendarza MS Project przy użyciu Aspose.Tasks
url: /pl/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt tygodni pracy w Javie z kalendarza MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku **read work weeks Java** odczytasz z kalendarza Microsoft Project przy użyciu biblioteki Aspose.Tasks. Niezależnie od tego, czy tworzysz narzędzie raportujące, synchronizujesz harmonogramy, czy automatyzujesz ekstrakcję danych projektowych, możliwość programowego dostępu do definicji tygodni pracy oszczędza niezliczone godziny ręcznej pracy. Przeprowadzimy Cię przez niezbędną konfigurację, pokażemy dokładny kod do pobrania szczegółów tygodni pracy i wyjaśnimy każdy krok, abyś mógł dostosować rozwiązanie do własnych projektów.

## Szybkie odpowiedzi
- **Co oznacza „read work weeks java”?** Odnosi się do wyodrębniania definicji tygodni pracy z pliku Project przy użyciu kodu Java.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (dostępna darmowa wersja próbna).  
- **Czy potrzebna jest licencja do rozwoju?** Wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jakie formaty plików są obsługiwane?** Obsługiwane są zarówno *.mpp*, jak i pliki Project XML.  
- **Jak długo trwa implementacja?** Zazwyczaj mniej niż 10 minut po skonfigurowaniu biblioteki.

## Co to jest „read work weeks java”?
Odczyt tygodni pracy w Javie oznacza użycie API Aspose.Tasks do uzyskania dostępu do `WorkWeekCollection` obiektu kalendarza wewnątrz pliku Microsoft Project. Każdy `WorkWeek` zawiera daty rozpoczęcia/zakonczenia oraz dzienne definicje czasu pracy, które określają, jak zasoby są planowane.

## Dlaczego odczytywać tygodnie pracy w Javie z kalendarza Microsoft Project?
- **Automatyzacja:** Eliminacja ręcznego kopiowania i wklejania danych harmonogramu.  
- **Integracja:** Dostarczanie informacji o tygodniach pracy do systemów ERP, HR lub własnych systemów raportowania.  
- **Spójność:** Zapewnienie, że wszystkie narzędzia downstream respektują te same reguły kalendarza zdefiniowane w pliku Project.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – wersja 8 lub nowsza zainstalowana.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR z oficjalnej strony: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. Przykładowy plik Project (`ReadWorkWeeksInformation.mpp`) umieszczony w znanym folderze.

## Importowanie pakietów
Najpierw zaimportuj klasy, których będziemy potrzebować do interakcji z kalendarzami i tygodniami pracy:

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
Zdefiniuj folder zawierający plik `.mpp`. Zastąp placeholder rzeczywistą ścieżką na swoim komputerze:

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Utwórz instancję Project i uzyskaj dostęp do kalendarza
Zainicjuj obiekt `Project`, wybierz kalendarz, którego potrzebujesz (według UID), i uzyskaj jego `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** Jeśli nie jesteś pewien UID kalendarza, możesz iterować po `project.getCalendars()` i wypisać nazwę oraz UID każdego kalendarza.

## Krok 3: Iteruj przez tygodnie pracy
Przejdź pętlą przez każdy `WorkWeek`, aby wyświetlić jego nazwę, daty rozpoczęcia/zakonczenia oraz dzienne godziny pracy:

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

**Co zobaczysz:** Konsola wypisuje etykietę każdego tygodnia pracy (np. „Standard”), jego zakres dat obowiązywania oraz umożliwia zagłębienie się w dokładne godziny pracy dla każdego dnia.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| `NullPointerException` podczas dostępu do `calendar` | Nieprawidłowy UID lub kalendarz nie istnieje | Sprawdź UID przy użyciu `project.getCalendars().size()` i najpierw wyświetl dostępne kalendarze. |
| Brak wyjścia dla tygodni pracy | Wybrany kalendarz nie ma niestandardowych tygodni pracy (używa domyślnego) | Użyj domyślnego kalendarza (`project.getDefaultCalendar()`) lub utwórz tydzień pracy programowo. |
| Format daty wygląda dziwnie | `System.out.println` używa domyślnego formatu `java.util.Date` | Zastosuj `SimpleDateFormat`, aby sformatować daty według potrzeb. |

## Najczęściej zadawane pytania

**Q: Czy mogę modyfikować informacje o tygodniach pracy przy użyciu Aspose.Tasks for Java?**  
A: Tak. API udostępnia metody takie jak `addWorkWeek()`, `removeWorkWeek()` oraz settery właściwości, aby zmieniać nazwy, daty i godziny pracy.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Zdecydowanie. Obsługuje pliki MPP od Project 98 aż do najnowszych wersji, a także pliki Project XML.

**Q: Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?**  
A: Tak. Biblioteka jest czystą Javą, więc możesz używać jej razem ze Spring, Jakarta EE lub dowolnym innym frameworkiem.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks?**  
A: Tak, możesz pobrać darmową 30‑dniową wersję próbną z oficjalnej strony: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?**  
A: Najlepszym miejscem jest forum społeczności Aspose: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Podsumowanie
Teraz opanowałeś **read work weeks java** przy użyciu Aspose.Tasks. Postępując zgodnie z powyższymi krokami, możesz programowo pobierać definicje tygodni pracy z dowolnego kalendarza MS Project, integrować te dane w swoich aplikacjach i automatyzować przepływy pracy związane z harmonogramem. Śmiało eksperymentuj z tworzeniem lub aktualizacją tygodni pracy — Aspose.Tasks ułatwia to zadanie.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}