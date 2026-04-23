---
date: 2026-02-20
description: Dowiedz się, jak ustawić datę rozpoczęcia projektu i zarządzać odchyleniami
  projektu przy użyciu Aspose.Tasks dla Javy. Ten przewodnik pokazuje również, jak
  efektywnie ustawiać czas trwania zadania.
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ustaw datę rozpoczęcia projektu i obsłuż odchylenia zadań Aspose.Tasks
url: /pl/java/task-properties/handle-variances/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw datę rozpoczęcia projektu i obsłuż odchylenia zadań Aspose.Tasks

## Wprowadzenie
W świecie zarządzania projektami **ustawienie daty rozpoczęcia projektu** jest jedną z pierwszych czynności, które nadają Twojemu harmonogramowi solidne podstawy. Aspose.Tasks for Java upraszcza ten krok — a także późniejsze zarządzanie odchyleniami zadań — czyniąc je prostymi i niezawodnymi. W tym samouczku dowiesz się, jak ustawić datę rozpoczęcia projektu, określić czas trwania zadania oraz efektywnie zarządzać odchyleniami projektu.

## Szybkie odpowiedzi
- **Jaka jest podstawowa metoda ustawienia daty rozpoczęcia projektu?** Użyj `project.set(Prj.START_DATE, …)` z instancją `java.util.Calendar`.  
- **Która klasa reprezentuje bazę odniesienia do śledzenia odchyleń?** `BaselineType.Baseline`.  
- **Czy mogę zmienić daty rozpoczęcia i zakończenia zadania po ustawieniu bazy?** Tak, po prostu zaktualizuj `Tsk.START` i `Tsk.STOP`.  
- **Czy potrzebna jest licencja do użytku deweloperskiego?** Dostępna jest tymczasowa licencja do oceny.  
- **Jakiej wersji Aspose.Tasks dotyczy ten kod?** Najnowsze wydanie Aspose.Tasks for Java.

## Co to jest **ustawienie daty rozpoczęcia projektu**?
Ustawienie daty rozpoczęcia projektu definiuje dzień kalendarzowy, od którego obliczane są wszystkie daty zadań. Ma to wpływ na obliczenia harmonogramu, analizę ścieżki krytycznej oraz tworzenie bazy odniesienia, co czyni go niezbędnym do dokładnego zarządzania odchyleniami.

## Dlaczego warto ustawić datę rozpoczęcia projektu i zarządzać odchyleniami?
- **Przewidywalność:** Tworzy znaną bazę odniesienia do porównania z rzeczywistym postępem.  
- **Elastyczność:** Pozwala dostosować daty poszczególnych zadań bez utraty pierwotnego planu.  
- **Raportowanie:** Umożliwia przejrzyste raporty odchyleń, które podkreślają opóźnienia lub wcześniejsze zakończenia.

## Wymagania wstępne
Zanim przejdziesz dalej, upewnij się, że masz następujące elementy:

- Środowisko programistyczne Java – zainstalowany JDK oraz gotowe IDE lub narzędzie budujące.  
- Biblioteka Aspose.Tasks – pobierz bibliotekę **[tutaj](https://releases.aspose.com/tasks/java/)**.  

## Importowanie pakietów
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Konfiguracja projektu
Utwórz nową instancję `Project`, która będzie przechowywać wszystkie zadania i informacje o harmonogramie.

```java
Project project = new Project();
```

## Krok 2: Dodawanie zadania
Dodaj zadanie pod zadaniem głównym. To będzie element pracy, który później dostosujemy.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Krok 3: Ustawianie daty rozpoczęcia i czasu trwania
Zdefiniuj datę rozpoczęcia projektu i przydziel zadaniu czas trwania. To demonstruje **ustawienie czasu trwania zadania** w praktyce.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## Krok 4: Ustawianie bazy odniesienia
Utwórz bazę odniesienia, aby później móc porównać planowane i rzeczywiste daty — kluczowe dla **zarządzania odchyleniami projektu**.

```java
project.setBaseline(BaselineType.Baseline);
```

## Krok 5: Modyfikacja dat rozpoczęcia i zakończenia zadania
Zmień daty rozpoczęcia i zakończenia zadania, aby zasymulować scenariusz odchylenia.

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*Śmiało modyfikuj daty i czasy trwania, aby dopasować je do konkretnych potrzeb Twojego projektu.*

## Typowe problemy i wskazówki
- **Baza musi być ustawiona przed zmianą dat.** Jeśli najpierw zmienisz daty, baza przechwyci zmodyfikowany harmonogram zamiast pierwotnego planu.  
- **Miesiące w Calendar są zerowe.** Pamiętaj, że `Calendar.FEBRUARY` odpowiada miesiącowi 1, a nie 2.  
- **Jednostki czasu trwania:** `project.getDuration(2)` domyślnie tworzy czas trwania dwóch dni; zmień jednostkę, jeśli potrzebujesz godzin lub tygodni.

## Podsumowanie
Opanowując **ustawienie daty rozpoczęcia projektu**, **ustawienie czasu trwania zadania** oraz **zarządzanie odchyleniami projektu**, zyskujesz pełną kontrolę nad harmonogramem projektu przy użyciu Aspose.Tasks for Java. Powyższe kroki zapewniają solidną podstawę, którą możesz rozbudować o bardziej złożone scenariusze, takie jak projekty wieloetapowe, przydział zasobów i automatyczne raportowanie.

## Najczęściej zadawane pytania
### Czy Aspose.Tasks nadaje się do wszystkich potrzeb zarządzania projektami?
Aspose.Tasks to wszechstronne narzędzie, które sprawdza się w szerokim zakresie wymagań zarządzania projektami, oferując elastyczność i solidne funkcje.

### Czy mogę zintegrować Aspose.Tasks z istniejącym projektem Java?
Tak, możesz łatwo zintegrować Aspose.Tasks ze swoim projektem Java, postępując zgodnie z dostarczoną dokumentacją **[tutaj](https://reference.aspose.com/tasks/java/)**.

### Czy dostępna jest tymczasowa licencja dla Aspose.Tasks?
Tak, tymczasową licencję dla Aspose.Tasks możesz uzyskać **[tutaj](https://purchase.aspose.com/temporary-license/)**.

### Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
Wsparcie i dyskusje znajdziesz na forum Aspose.Tasks **[tutaj](https://forum.aspose.com/c/tasks/15)**.

### Czy mogę pobrać Aspose.Tasks dla Java?
Tak, pobierz najnowszą wersję Aspose.Tasks for Java **[tutaj](https://releases.aspose.com/tasks/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-02-20  
**Testowano z:** najnowsze wydanie Aspose.Tasks dla Java  
**Autor:** Aspose