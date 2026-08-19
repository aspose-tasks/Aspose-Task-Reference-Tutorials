---
date: 2026-02-28
description: Dowiedz się, jak uzyskać czas trwania w minutach, dniach, godzinach,
  tygodniach i miesiącach przy użyciu Aspose.Tasks dla Javy. Szczegółowy przewodnik
  z przykładami kodu.
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak uzyskać czas trwania w różnych jednostkach przy użyciu Aspose.Tasks
url: /pl/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uzyskać czas trwania w różnych jednostkach przy użyciu Aspose.Tasks

## Wprowadzenie
Zrozumienie **jak uzyskać czas trwania** zadań jest podstawowym elementem każdego przepływu pracy w zarządzaniu projektami. Niezależnie od tego, czy potrzebujesz minut do szczegółowego śledzenia, czy miesięcy do planowania na wysokim poziomie, Aspose.Tasks for Java ułatwia konwersję. W tym samouczku przeprowadzimy Cię przez pobieranie czasu trwania zadania w minutach, dniach, godzinach, tygodniach i miesiącach, wyjaśniając, dlaczego każda jednostka może być przydatna w rzeczywistych projektach.

## Szybkie odpowiedzi
- **Co oznacza „jak uzyskać czas trwania”?** To proces wyodrębniania przedziału czasowego zadania i konwertowania go na potrzebną jednostkę.  
- **Która metoda API wykonuje konwersję?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę konwertować do jednostek niestandardowych?** Możesz łączyć konwersje lub używać `TimeSpan` do własnych obliczeń.  
- **Czy kod jest kompatybilny z Java 17?** Tak, Aspose.Tasks obsługuje Java 8 i nowsze wersje.

## Co oznacza „jak uzyskać czas trwania” w Aspose.Tasks?
Aspose.Tasks przechowuje długość zadania jako obiekt `Duration`. Wywołując metodę `convert` i podając `TimeUnitType` (Minute, Hour, Day, Week, Month), możesz uzyskać tę samą wartość wyrażoną w żądanej jednostce. Ta elastyczność pozwala generować raporty, wykonywać obliczenia lub przekazywać dane do innych systemów bez ręcznych obliczeń.

## Dlaczego warto używać Aspose.Tasks do konwersji czasu trwania?
- **Dokładność:** Automatycznie obsługuje wyjątki kalendarzowe, czas pracy i niestandardowe kalendarze.  
- **Wydajność:** Jednowierszowa konwersja eliminuje pętle i własne parsowanie.  
- **Przenośność:** Działa tak samo w środowiskach Windows, Linux i macOS.  
- **Integracja:** Bezproblemowo wpasowuje się w istniejące aplikacje Java, które już korzystają z Aspose.Tasks.

## Wymagania wstępne
Przed przystąpieniem do kodu upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK)
- Bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/)
- Podstawową znajomość programowania w języku Java

## Importowanie pakietów
W swoim projekcie Java dołącz bibliotekę Aspose.Tasks. Dodaj następujące polecenie importu na początku swojego kodu:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Krok 1: Konfiguracja projektu
Utwórz nowy projekt Java w ulubionym IDE (IntelliJ, Eclipse, VS Code itp.) i dodaj plik JAR Aspose.Tasks do ścieżki klas projektu. Dzięki temu klasy będą dostępne w czasie kompilacji.

## Krok 2: Odczyt szablonu projektu
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

Zastąp `"Your Document Directory"` rzeczywistym folderem zawierającym plik projektu `.xml` lub `.mpp`.

## Krok 3: Pobranie zadania
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

Wywołanie `getById(1)` pobiera zadanie o identyfikatorze 1. Zmień identyfikator, aby odwołać się do innego zadania w pliku.

## Krok 4: Czas trwania w minutach – Jak uzyskać czas trwania w minutach?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

Zmienna `mins` zawiera teraz długość zadania wyrażoną w minutach.

## Krok 5: Czas trwania w dniach – Jak uzyskać czas trwania w dniach?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

Użyj tej wartości, gdy potrzebna jest precyzja na poziomie dni do raportowania lub przydziału zasobów.

## Krok 6: Czas trwania w godzinach – Jak uzyskać czas trwania w godzinach?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

Godziny są przydatne przy kartach czasu pracy lub gdy chcesz podzielić dzień na zmiany robocze.

## Krok 7: Czas trwania w tygodniach – Jak uzyskać czas trwania w tygodniach?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

Tygodnie są często używane w wykresach Gantta na wysokim poziomie lub przy planowaniu kamieni milowych.

## Krok 8: Czas trwania w miesiącach – Jak uzyskać czas trwania w miesiącach?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

Czas trwania na poziomie miesięcy pomaga przy dopasowywaniu faz projektu do okresów fiskalnych.

## Typowe problemy i rozwiązania
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| `NullPointerException` na `task` | Nieprawidłowy identyfikator zadania lub brak dzieci | Sprawdź, czy identyfikator zadania istnieje, używając `project.getRootTask().getChildren()` |
| Nieoczekiwane wartości (np. 0) | Projekt używa niestandardowego kalendarza z dniami niepracującymi | Upewnij się, że kalendarz projektu jest poprawnie zdefiniowany lub użyj `project.getCalendar()`, aby go sprawdzić |
| Konwersja zwraca ułamkowe tygodnie | Tygodnie są obliczane na podstawie domyślnej długości tygodnia w projekcie (zwykle 5 dni) | Pomnóż przez 5, jeśli potrzebujesz tygodni kalendarzowych, lub dostosuj ustawienia kalendarza |

## Najczęściej zadawane pytania
### Q: Czy mogę używać Aspose.Tasks for Java w dowolnym IDE Java?
A: Tak, Aspose.Tasks for Java jest kompatybilny z dowolnym zintegrowanym środowiskiem programistycznym (IDE) Java.

### Q: Jak mogę uzyskać identyfikator zadania w pliku Microsoft Project?
A: Możesz ręcznie przejrzeć plik projektu lub wywołać `project.getRootTask().getChildren()` i iterować po kolekcji, aby odczytać `ID` każdego zadania.

### Q: Czy Aspose.Tasks nadaje się do obsługi projektów dużej skali?
A: Zdecydowanie. Aspose.Tasks jest zaprojektowany do efektywnego przetwarzania projektów z tysiącami zadań i zasobów.

### Q: Gdzie mogę znaleźć dalszą dokumentację?
A: Odwiedź [dokumentację](https://reference.aspose.com/tasks/java/) aby uzyskać pełne odniesienia API, przykłady kodu i przewodniki najlepszych praktyk.

### Q: Czy mogę wypróbować Aspose.Tasks for Java przed zakupem?
A: Tak, możesz wypróbować [bezpłatną wersję próbną](https://releases.aspose.com/) aby ocenić jego możliwości.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}