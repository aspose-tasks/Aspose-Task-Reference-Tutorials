---
date: 2026-01-28
description: Dowiedz się, jak tworzyć wyjątki kalendarza przy użyciu Aspose.Tasks
  dla Javy, efektywnie dodawać i usuwać wyjątki kalendarza oraz usprawniać planowanie
  projektu.
linktitle: Add and Remove Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Utwórz wyjątek kalendarza Aspose dla Java
url: /pl/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz wyjątek kalendarza Aspose dla Java

## Wprowadzenie
Dokładne planowanie projektu często zależy od obsługi **calendar exceptions** — dni, w których zasoby są niedostępne lub zmieniają się harmonogramy pracy. Dzięki **Aspose.Tasks for Java** możesz **create calendar exception** obiekty, dodać je do kalendarza projektu lub usunąć, gdy nie są już potrzebne. W tym samouczku przeprowadzimy Cię przez cały proces, od wczytania pliku projektu po weryfikację zarządzanych wyjątków. Ten przewodnik pokazuje dokładnie, jak **create calendar exception aspose** w środowisku Java.

### Szybkie odpowiedzi
- **What does “create calendar exception” mean?** Oznacza to zdefiniowanie zakresu dat, który odbiega od standardowego kalendarza roboczego.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** Dostępna jest darmowa wersja próbna; licencja jest wymagana do użytku produkcyjnego.  
- **Can I remove an existing exception?** Tak — wystarczy odnaleźć ją na liście wyjątków kalendarza i usunąć.  
- **Is this compatible with Microsoft Project files?** Absolutnie; Aspose.Tasks odczytuje i zapisuje wszystkie główne wersje .mpp.

#### Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK).
- Bibliotekę Aspose.Tasks for Java dodaną do classpathu projektu.
- Podstawową znajomość Javy i terminologii zarządzania projektami.

## Jak utworzyć wyjątek kalendarza Aspose w Javie
Poniżej znajduje się krok po kroku przewodnik, który wyjaśnia cel każdego fragmentu kodu przed jego uruchomieniem. Postępuj zgodnie z sekcjami w kolejności, aby zapewnić prawidłowe obsłużenie wyjątków kalendarza.

## Importowanie pakietów
Najpierw zaimportuj podstawowe klasy Aspose.Tasks, które umożliwiają manipulację kalendarzem.

```java
import com.aspose.tasks.*;
```

## Krok 1: Wczytaj projekt i uzyskaj dostęp do jego kalendarza
Zaczynamy od wczytania istniejącego pliku Microsoft Project (`input.mpp`) i pobrania pierwszego kalendarza z kolekcji. Możesz dostosować indeks, jeśli potrzebujesz innego kalendarza.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## Krok 2: Usuń istniejący wyjątek (jeśli potrzebny)
Czasami kalendarz już zawiera wyjątki, które chcesz usunąć. Poniższy fragment sprawdza listę wyjątków i usuwa pierwszy wpis, gdy istnieje więcej niż jeden wyjątek.

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** Zawsze sprawdzaj rozmiar listy wyjątków przed usuwaniem elementów, aby uniknąć `IndexOutOfBoundsException`.

## Krok 3: Utwórz (dodaj) nowy wyjątek kalendarza
Teraz **create calendar exception** obiekty. W tym przykładzie definiujemy wyjątek obejmujący 1‑3 stycznia 2009. Dostosuj daty do własnego harmonogramu projektu.

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** Dodawanie wyjątków pozwala modelować święta, okna konserwacyjne lub dowolne okresy niepracujące bezpośrednio w harmonogramie projektu. To jest sedno funkcjonalności **create calendar exception aspose**.

## Krok 4: Wyświetl wszystkie wyjątki w celu weryfikacji
Po dodaniu (lub usunięciu) wyjątków dobrą praktyką jest ich wydrukowanie. Pomaga to potwierdzić, że kalendarz odzwierciedla zamierzone zmiany.

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| Brak wyjścia | Lista wyjątków jest pusta | Upewnij się, że dodałeś wyjątek przed iteracją. |
| `NullPointerException` na `project` | Nieprawidłowa ścieżka pliku | Sprawdź, czy `dataDir` wskazuje na prawidłowy plik `.mpp`. |
| Daty są przesunięte o jeden dzień | Różnice stref czasowych | Użyj `java.util.Calendar` z wyraźnie określoną strefą czasową lub API `java.time`. |

## Najczęściej zadawane pytania

**Q: Czy mogę dodać wiele wyjątków do kalendarza przy użyciu Aspose.Tasks for Java?**  
A: Tak. Po prostu utwórz nowy `CalendarException` dla każdego zakresu dat i dodaj go do `cal.getExceptions()` w pętli.

**Q: Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?**  
A: Aspose.Tasks obsługuje szeroki zakres wersji .mpp, od Project 98 aż po najnowsze wydania, zapewniając płynną integrację.

**Q: Jak mogę obsłużyć powtarzające się wyjątki (np. cotygodniowe spotkania) w kalendarzach projektów?**  
A: Użyj właściwości powtarzalności `CalendarException` (`setRecurrencePattern`), aby zdefiniować złożone wzorce, takie jak codzienne, tygodniowe lub miesięczne powtórzenia.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz pobrać darmową wersję próbną ze [strony internetowej](https://releases.aspose.com/), aby przetestować wszystkie funkcje przed zakupem.

**Q: Gdzie mogę uzyskać wsparcie w przypadku problemów lub pytań związanych z Aspose.Tasks for Java?**  
A: Odwiedź forum Aspose.Tasks dla Javy na [stronie internetowej](https://reference.aspose.com/tasks/java/), aby zadawać pytania, lub skontaktuj się bezpośrednio z pomocą techniczną Aspose.

## Zakończenie
Zarządzanie wyjątkami kalendarza jest niezbędne dla realistycznych harmonogramów projektów i planowania zasobów. Dzięki **Aspose.Tasks for Java** możesz **create calendar exception** obiekty, dodać je do dowolnego kalendarza projektu i usuwać, gdy przestaną być istotne — wszystko przy użyciu kilku linii kodu. Ta możliwość **create calendar exception aspose** pozwala tworzyć harmonogramy, które naprawdę odzwierciedlają rzeczywiste ograniczenia.

---

**Ostatnia aktualizacja:** 2026-01-28  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}