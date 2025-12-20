---
date: 2025-12-20
description: Dowiedz się, jak używać Aspose.Tasks do wyodrębniania szczegółów kalendarza
  projektu z plików Microsoft Project przy użyciu Javy. Przewodnik krok po kroku z
  przykładami kodu.
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak używać Aspose.Tasks do pobierania informacji o kalendarzu MS Project
url: /pl/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose.Tasks do pobierania informacji o kalendarzu MS Project

## Wprowadzenie
W tym samouczku **dowiesz się, jak używać Aspose.Tasks**, aby programowo pobierać informacje o kalendarzu z plików Microsoft Project. Dostęp do danych kalendarza, takich jak dni robocze, godziny i wyjątki, jest niezbędny, gdy potrzebujesz **wyodrębnić kalendarz projektu** w celu raportowania, integracji lub własnej logiki harmonogramowania. Przejdźmy krok po kroku przez proces.

## Szybkie odpowiedzi
- **Jakiej biblioteki używa ten samouczek?** Aspose.Tasks for Java.  
- **Jakie główne słowo kluczowe jest omówione?** *how to use aspose.tasks*.  
- **Co możesz wyodrębnić?** Kalendarze projektu, w tym dni robocze i godziny.  
- **Czy potrzebna jest licencja?** Dostępna jest bezpłatna wersja próbna; licencja jest wymagana w środowisku produkcyjnym.  
- **Jaką wersję Javy obsługuje?** Java 8 lub wyższą.

## Dlaczego wyodrębniać informacje o kalendarzu projektu?
Kalendarze projektu określają terminy zadań, przydziały zasobów i ogólne obliczenia harmonogramu. Wyodrębniając te dane, możesz:
- Generować niestandardowe raporty odzwierciedlające rzeczywiste harmonogramy pracy.  
- Synchronizować harmonogramy Microsoft Project z zewnętrznymi systemami (ERP, BI itp.).  
- Przeprowadzać analizę „co‑jeśli” poprzez programową modyfikację ustawień kalendarza.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz:

- Podstawową znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK) w systemie.  
- Bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks do swojego projektu Java.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Krok 1: Ustaw katalog danych
Zdefiniuj folder zawierający plik *.mpp*.

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` absolutną ścieżką do folderu, w którym znajduje się **project.mpp**.

## Krok 2: Zdefiniuj jednostki czasu
Utwórz stałe, które pomogą przeliczyć wewnętrzną reprezentację czasu na godziny czytelne dla człowieka.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

Wartości te są wyrażone w mikrosekundach, co jest sposobem, w jaki Aspose.Tasks przechowuje czas wewnętrznie.

## Krok 3: Utwórz instancję projektu
Wczytaj plik Microsoft Project do obiektu `Project`.

```java
Project project = new Project(dataDir + "project.mpp");
```

Konstruktor `Project` parsuje plik *.mpp* i udostępnia wszystkie dane projektu, w tym kalendarze, poprzez API.

## Krok 4: Pobierz informacje o kalendarzach
Uzyskaj kolekcję kalendarzy zdefiniowanych w projekcie.

```java
CalendarCollection alCals = project.getCalendars();
```

Projekt może zawierać wiele kalendarzy (standardowy, zasobów i niestandardowy). Ta kolekcja zapewnia dostęp do każdego z nich.

## Krok 5: Iteruj przez kalendarze
Iteruj przez każdy kalendarz, wyświetl jego UID, nazwę oraz dni robocze z odpowiadającymi godzinami.

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

Wewnętrzna pętla sprawdza każdy obiekt `WeekDay`. Jeśli dzień jest oznaczony jako roboczy, wypisuje typ dnia (Monday, Tuesday, …) wraz z obliczonymi godzinami pracy.

## Krok 6: Wyświetl komunikat o zakończeniu
Zasygnalizuj, że proces wyodrębniania został zakończony.

```java
System.out.println("Process completed Successfully");
```

## Podsumowanie
Postępując zgodnie z tymi krokami, **wiesz już, jak używać Aspose.Tasks do wyodrębniania informacji o kalendarzu projektu** z pliku MS Project przy użyciu Javy. Możesz zintegrować tę logikę z większymi aplikacjami, zautomatyzować raportowanie lub synchronizować harmonogramy z innymi systemami korporacyjnymi.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks w innych językach programowania?**  
A: Tak, Aspose.Tasks obsługuje wiele platform i języków programowania, w tym .NET, C++, Python i Javę.

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?**  
A: Tak, możesz pobrać bezpłatną wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Wsparcie możesz uzyskać na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Q: Czy mogę kupić tymczasową licencję na Aspose.Tasks?**  
A: Tak, tymczasowe licencje są dostępne do zakupu [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks?**  
A: Dokumentację możesz znaleźć [tutaj](https://reference.aspose.com/tasks/java/).

---

**Ostatnia aktualizacja:** 2025-12-20  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}