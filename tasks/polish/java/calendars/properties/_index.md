---
date: 2026-02-07
description: Dowiedz się, jak ustawić kalendarz projektu w Javie i zarządzać właściwościami
  kalendarza MS Project przy użyciu Aspose.Tasks. Przewodnik krok po kroku, jak wyświetlić
  godziny pracy kalendarza i dostosować harmonogramy.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ustawić kalendarz projektu w Javie przy użyciu Aspose.Tasks
url: /pl/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kalendarz projektu w Javie przy użyciu Aspose.Tasks

## Wstęp
W tym samouczku dowiesz się, **jak programowo ustawić kalendarz projektu w Javie** przy użyciu biblioteki Aspose.Tasks dla Javy. Kontrolowanie właściwości kalendarza pozwala **wyświetlać godziny pracy kalendarza**, definiować własne dni robocze oraz dopasować harmonogram projektu do rzeczywistych ograniczeń. Przejdziemy krok po kroku – od przygotowania środowiska po iterację po kalendarzach i odczyt ich właściwości – abyś mógł pewnie **zarządzać ustawieniami kalendarza MS Project** w swoich aplikacjach.

## Szybkie odpowiedzi
- **Co oznacza „ustawienie kalendarza projektu”?** Oznacza to tworzenie lub aktualizację godzin pracy kalendarza, kalendarza bazowego oraz typów dni w pliku MS Project.  
- **Jakiej biblioteki potrzebuję?** Aspose.Tasks dla Javy (dowolna aktualna wersja).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarczy do rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę wyświetlić godziny pracy kalendarza?** Tak – odczytując każdy `WeekDay`, możesz wypisać godziny dla każdego typu dnia.  
- **Czy to działa z Maven/Gradle?** Oczywiście – dodaj plik JAR Aspose.Tasks jako zależność.

## Jak ustawić kalendarz projektu w Javie
Ta sekcja bezpośrednio odnosi się do głównego słowa kluczowego. Przedstawimy dokładne kroki, które pozwolą Ci **ustawić wartości kalendarza projektu w Javie**, modyfikować dni robocze kalendarza oraz obliczać godziny pracy w stylu Java.

## Co to jest kalendarz projektu?
Kalendarz projektu definiuje dni i godziny pracy dla zadań, zasobów oraz całego harmonogramu projektu. W MS Project kalendarze mogą dziedziczyć po kalendarzu bazowym, a każdy typ dnia (np. **Standard**, **Non‑working**) może mieć własny czas pracy. Programowe zarządzanie tymi ustawieniami umożliwia dynamiczne dostosowywanie harmonogramu bez ręcznej edycji.

## Dlaczego warto zarządzać kalendarzem MS Project programowo?
- **Automatyzacja:** Dostosuj kalendarze w wielu projektach jednym skryptem.  
- **Spójność:** Wymuszaj organizacyjne zasady czasu pracy.  
- **Integracja:** Synchronizuj kalendarze z zewnętrznymi systemami (HR, ERP).  
- **Widoczność:** Szybko **wyświetl godziny pracy kalendarza** w raportach lub podczas debugowania.  
- **Elastyczność:** Możesz **modyfikować dni robocze kalendarza** lub dodawać wyjątki w locie.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- **Java Development Kit (JDK) 8+** z ustawioną zmienną `JAVA_HOME`.  
- **Aspose.Tasks dla Javy** pobraną ze [strony pobierania](https://releases.aspose.com/tasks/java/). Dodaj plik JAR do classpath projektu lub jako zależność Maven/Gradle.  

## Importowanie pakietów
Najpierw zaimportuj podstawowe klasy Aspose.Tasks, które będą używane w całym samouczku:

```java
import com.aspose.tasks.*;
```

## Krok 1: Ustawienie katalogu danych
Zdefiniuj folder zawierający pliki projektu. Zamień symboliczny placeholder na rzeczywistą ścieżkę na swoim komputerze.

```java
String dataDir = "Your Data Directory";
```

## Krok 2: Definicja jednostek czasu
Czasy pracy wyrażane są w milisekundach. Zdefiniowanie stałych ułatwia czytelność kodu i pomaga **dokładnie obliczyć godziny pracy w Javie**.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Krok 3: Ładowanie danych projektu
Utwórz instancję `Project`, ładując istniejący plik MS Project XML (`.xml` lub `.mpp`). Dzięki temu uzyskasz dostęp do wszystkich kalendarzy zapisanych w pliku.

```java
Project project = new Project(dataDir + "project.xml");
```

## Iteracja po kalendarzach w Javie
Teraz przechodzimy przez każdy kalendarz, wypisując jego unikalny identyfikator, nazwę, kalendarz bazowy oraz godziny pracy dla każdego typu dnia. To pokazuje **jak ustawić kalendarz projektu w Javie** oraz **wyświetlić godziny pracy kalendarza**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### Co robi ten kod
- **Filtruje kalendarze bez nazwy** (niektóre wewnętrzne kalendarze mogą mieć `null` jako nazwę).  
- **Wypisuje UID i nazwę** – przydatne do późniejszej identyfikacji kalendarza.  
- **Pokazuje kalendarz bazowy** – „Self” (kalendarz jest własnym bazowym) lub nazwę dziedziczonego kalendarza.  
- **Iteruje po każdym `WeekDay`**, aby obliczyć i wyświetlić całkowite godziny pracy (`workingTime` jest w milisekundach, więc dzielimy przez `OneHour`).  

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| `NullPointerException` przy `cal.getBaseCalendar()` | Kalendarz jest kalendarzem bazowym (`isBaseCalendar()` zwraca `true`). | Użyj warunku trójargumentowego, jak w przykładzie (`cal.isBaseCalendar() ? "Self" : ...`). |
| Brak wyjścia dla godzin pracy | Plik projektu używa innej jednostki czasu (ticks). | Sprawdź format pliku; Aspose.Tasks normalizuje do milisekund, ale upewnij się, że wczytujesz właściwy typ pliku. |
| Nie można znaleźć `project.xml` | Nieprawidłowa ścieżka `dataDir`. | Użyj ścieżki bezwzględnej lub `Paths.get(dataDir, "project.xml").toString()`. |

## Najczęściej zadawane pytania

**P: Czy mogę modyfikować właściwości kalendarza programowo przy użyciu Aspose.Tasks?**  
O: Tak, API zapewnia pełny dostęp odczyt/zapis do kalendarzy, umożliwiając dodawanie, edytowanie lub usuwanie czasów pracy, wyjątków oraz relacji z kalendarzem bazowym.

**P: Czy istnieją ograniczenia w dostosowywaniu kalendarza przy użyciu Aspose.Tasks?**  
O: Biblioteka odzwierciedla możliwości Microsoft Project, więc możesz dostosować praktycznie wszystkie aspekty kalendarza. Jedynie bardzo stare wersje plików Project mogą mieć drobne niezgodności.

**P: Czy mogę zintegrować zarządzanie kalendarzem z istniejącymi projektami Java?**  
O: Oczywiście. Wystarczy dodać plik JAR Aspose.Tasks do ścieżki kompilacji i używać tych samych wzorców kodu, które pokazano w tym przewodniku.

**P: Czy Aspose.Tasks obsługuje inne funkcjonalności zarządzania projektami poza kalendarzem?**  
O: Tak, obejmuje zadania, zasoby, przydziały, struktury, baseline’y i wiele więcej – co czyni go kompleksowym rozwiązaniem do automatyzacji projektów w Javie.

**P: Czy dostępne jest wsparcie techniczne dla deweloperów korzystających z Aspose.Tasks?**  
O: Tak, Aspose oferuje dedykowane fora, wsparcie e‑mail oraz obszerną dokumentację dla wszystkich licencjonowanych użytkowników.

---

**Ostatnia aktualizacja:** 2026-02-07  
**Testowano z:** Aspose.Tasks dla Javy 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}