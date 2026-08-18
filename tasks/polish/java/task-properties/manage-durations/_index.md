---
date: 2026-02-20
description: Poznaj, jak dodać zadanie do projektu i zarządzać czasami trwania przy
  użyciu Aspose.Tasks dla Javy. Dowiedz się, jak ustawić czas trwania i jak łatwo
  go konwertować.
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Dodaj zadanie do projektu i zarządzaj czasem trwania przy użyciu Aspose.Tasks
url: /pl/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj zadanie do projektu i zarządzaj czasami trwania przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się **jak dodać zadanie do projektu** i kontrolować jego czas trwania przy użyciu Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz nowe narzędzie do planowania projektów, czy rozszerzasz istniejące rozwiązanie, opanowanie obsługi czasu trwania zadań jest niezbędne do dokładnego harmonogramowania i raportowania.

## Szybkie odpowiedzi
- **Co oznacza „add task to project”?** Tworzy nowy obiekt `Task` w korzeniu projektu lub w określonym zadaniu podsumowującym.  
- **Która klasa reprezentuje czas trwania?** `com.aspose.tasks.Duration`.  
- **Jak ustawić czas trwania?** Użyj `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Czy mogę przekonwertować czas trwania na inną jednostkę?** Tak, wywołaj `duration.convert(TimeUnitType.Hour)` lub dowolny inny `TimeUnitType`.  
- **Czy potrzebna jest licencja do produkcji?** Do komercyjnego użycia wymagana jest ważna licencja Aspose.Tasks.

## Co to jest „add task to project”?
Dodanie zadania do projektu oznacza utworzenie obiektu `Task` i dołączenie go do hierarchii zadań projektu. Ta operacja jest pierwszym krokiem, zanim będziesz mógł zdefiniować pracę, zasoby lub czas trwania dla tego zadania.

## Dlaczego warto zarządzać czasami trwania zadań?
Dokładne czasy trwania zapewniają realistyczne terminy, alokację zasobów oraz analizę ścieżki krytycznej. Dzięki Aspose.Tasks możesz programowo ustawiać, odczytywać, konwertować i modyfikować czasy trwania, dając pełną kontrolę nad harmonogramem projektu.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

- Java Development Kit (JDK): Upewnij się, że Java jest zainstalowana na Twoim komputerze. Możesz ją pobrać [tutaj](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteka Aspose.Tasks: Pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu. Bibliotekę znajdziesz [tutaj](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne pakiety do pracy z Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Krok 1: Konfiguracja projektu
```java
// Create a new project
Project project = new Project();
```

## Krok 2: Dodanie nowego zadania (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## Jak ustawić czas trwania
Teraz, gdy zadanie istnieje, możesz określić jego długość. Domyślnie czasy trwania wyrażane są w dniach.

## Krok 3: Pobranie i konwersja czasu trwania zadania
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## Jak konwertować czas trwania
Metoda `convert` pozwala przetłumaczyć `Duration` z jednego `TimeUnitType` na inny (np. dni → godziny, tygodnie → dni).

## Krok 4: Aktualizacja czasu trwania zadania do 1 tygodnia
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Krok 5: Zmniejszenie czasu trwania zadania
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

Postępując zgodnie z tymi krokami, pomyślnie **dodałeś zadanie do projektu** i zarządzałeś jego czasem trwania przy użyciu Aspose.Tasks dla Javy.

## Częste pułapki i wskazówki
- **Pułapka:** Zapomnienie o konwersji czasu trwania przed wykonaniem operacji arytmetycznych może prowadzić do niepoprawnych wyników. Zawsze weryfikuj jednostkę za pomocą `duration.getTimeUnit()`.
- **Wskazówka:** Używaj `project.getDuration(value, TimeUnitType)`, aby tworzyć czasy trwania w żądanej jednostce, zamiast konwertować je później.
- **Pułapka:** Ustawienie ujemnego czasu trwania spowoduje wyrzucenie wyjątku. Upewnij się, że walidujesz wartości wejściowe.

## Zakończenie
W tym przewodniku omówiliśmy, jak **dodać zadanie do projektu**, odczytać jego domyślny czas trwania, **ustawić czas trwania** oraz **konwertować czas trwania** na różne jednostki czasu. Teraz możesz włączać te techniki w większe aplikacje harmonogramujące, aby uzyskać precyzyjne planowanie projektów.

## FAQ
### Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Javy?
Aspose.Tasks jest kompatybilny z Javą 6 i późniejszymi wersjami.

### Czy mogę używać Aspose.Tasks w projektach komercyjnych?
Tak, możesz używać Aspose.Tasks zarówno w projektach prywatnych, jak i komercyjnych. Szczegóły licencjonowania znajdziesz [tutaj](https://purchase.aspose.com/buy).

### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać wsparcie społeczności i dyskusje.

### Jak uzyskać tymczasową licencję do celów testowych?
Tymczasową licencję możesz pobrać [tutaj](https://purchase.aspose.com/temporary-license/) do testów i ewaluacji.

### Czy dostępna jest darmowa wersja próbna Aspose.Tasks?
Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/), aby wypróbować Aspose.Tasks przed zakupem.

## Najczęściej zadawane pytania

**P: Jak zmienić czas trwania zadania po jego ustawieniu?**  
O: Pobierz bieżący czas trwania za pomocą `task.get(Tsk.DURATION)`, zmodyfikuj go (np. `add`, `subtract` lub `convert`) i ustaw ponownie przy użyciu `task.set(Tsk.DURATION, newDuration)`.

**P: Czy mogę ustawić czas trwania w minutach?**  
O: Tak, użyj `TimeUnitType.Minute` przy wywołaniu `project.getDuration(value, TimeUnitType.Minute)`.

**P: Czy zmiana czasu trwania automatycznie aktualizuje daty rozpoczęcia i zakończenia zadania?**  
O: Tylko jeśli tryb harmonogramowania projektu jest ustawiony na automatyczny. W przeciwnym razie może być konieczne ponowne przeliczenie harmonogramu przy użyciu `project.calculateCriticalPath()`.

**P: Czy można uzyskać czas trwania jako surową liczbę?**  
O: Wywołaj `duration.getTimeSpan()`, aby otrzymać wartość liczbową w bieżącej jednostce czasu.

**P: Co się stanie, jeśli odejmę więcej niż wynosi bieżący czas trwania?**  
O: API wyrzuci `ArgumentOutOfRangeException`. Zawsze waliduj, aby wynikowy czas trwania pozostał dodatni.

---

**Ostatnia aktualizacja:** 2026-02-20  
**Testowane z:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}