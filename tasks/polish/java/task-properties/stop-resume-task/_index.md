---
date: 2026-02-26
description: Dowiedz się, jak wznowić i zatrzymać zadanie w Aspose.Tasks dla Javy,
  w tym filtrowanie zadań według daty w celu precyzyjnej kontroli projektu.
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak wznowić zadanie i zatrzymać zadanie w Aspose.Tasks
url: /pl/java/task-properties/stop-resume-task/
weight: 30
---

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wznowić zadanie i zatrzymać zadanie w Aspose.Tasks

## Wprowadzenie
Jeśli tworzysz rozwiązanie do zarządzania projektami oparte na Javie, często będziesz musiał **wstrzymać** zadanie tymczasowo, a następnie **kontynuować** je później. Aspose.Tasks for Java ułatwia to dzięki wbudowanym właściwościom zatrzymywania i wznawiania zadań. W tym samouczku odkryjesz **jak wznowić zadanie** i **jak zatrzymać zadanie** programowo oraz zobaczysz, jak **filtrować zadania po dacie**, aby pracować tylko z odpowiednimi elementami w swoim harmonogramie.

## Szybkie odpowiedzi
- **Co oznacza „stop” dla zadania?** Ustawia datę zatrzymania, wstrzymując pracę po tym punkcie.  
- **Jak mogę wznowić zatrzymane zadanie?** Przypisując datę wznowienia późniejszą niż data zatrzymania.  
- **Czy mogę ograniczyć operację do zakresu dat?** Tak – użyj minimalnej daty do filtrowania zadań.  
- **Jaka wersja biblioteki jest wymagana?** Dowolne niedawne wydanie Aspose.Tasks for Java (API pozostaje stabilne).  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji.

## Co to jest „jak wznowić zadanie” w Aspose.Tasks?
Wznowienie zadania po prostu oznacza podanie daty **RESUME** w obiekcie `Task`. Gdy silnik projektu przetwarza harmonogram, praca będzie kontynuowana od tej daty. Jest to szczególnie przydatne przy obsłudze przerw, takich jak niedostępność zasobów lub zależności zewnętrzne.

## Dlaczego używać funkcji zatrzymania/wznowienia?
- **Kontrola nad harmonogramem:** Wstrzymaj pracę bez usuwania zadania.  
- **Dokładne raportowanie:** Pokaż realistyczne daty rozpoczęcia/zakonczenia na wykresach Gantta.  
- **Łatwa automatyzacja:** Połącz z filtrami dat, aby jednorazowo zaktualizować wiele zadań.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Solidną znajomość podstaw Javy.  
- Zainstalowane JDK na swoim komputerze.  
- Bibliotekę Aspose.Tasks for Java dodaną do projektu (pobierz ją z [tutaj](https://releases.aspose.com/tasks/java/)).

## Importowanie pakietów
Najpierw wprowadź wymagane klasy do zakresu, aby móc pracować z projektami i zadaniami.

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## Krok 1: Inicjalizacja projektu i kolektora
Utwórz instancję `Project` wskazującą na Twój plik MPP i skonfiguruj `ChildTasksCollector`, aby zebrać każde zadanie w hierarchii.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## Krok 2: Zdefiniuj minimalną datę do filtrowania
Jeśli chcesz pracować tylko z zadaniami, które mają istotne daty zatrzymania lub wznowienia, zdefiniuj **minimalną datę**. To jest sedno techniki *filtrowania zadań po dacie*.

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## Krok 3: Iteruj, sprawdzaj i wyświetl wartości Stop/Wznów
Teraz przeiteruj zebrane zadania, zastosuj logikę **jak zatrzymać zadanie** i wypisz daty. Kod również demonstruje **jak wznowić zadanie** poprzez odczytanie właściwości `RESUME`.

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **Porada:** Zastąp wywołania `System.out.println` własną logiką (np. aktualizacją dat, logowaniem do pliku lub modyfikacją obiektów zadania), aby faktycznie *zatrzymać* lub *wznowić* zadania w razie potrzeby.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | Zadanie nie ma ustawionej daty zatrzymania. | Sprawdź, czy wartość nie jest `null` przed wywołaniem `.before(minDate)`. |
| Dates appear as `NA` even after setting | Minimalna data jest zbyt późna. | Użyj wcześniejszej `minDate` lub usuń filtr. |
| Changes not reflected in the saved MPP | Projekt nie został zapisany po modyfikacjach. | Wywołaj `project.save("output.mpp");` po zaktualizowaniu zadań. |

## Najczęściej zadawane pytania

### Czy Aspose.Tasks for Java jest odpowiedni dla dużych projektów?
Zdecydowanie! Aspose.Tasks for Java jest zaprojektowany tak, aby obsługiwać projekty o różnych rozmiarach, zapewniając wydajność i niezawodność.

### Czy mogę dostosować datę zatrzymania i wznowienia zadań?
Tak, podany przykład umożliwia elastyczne ustawienie minimalnej daty zgodnie z wymaganiami Twojego projektu.

### Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks for Java?
Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać wsparcie społeczności i dyskusje.

### Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?
Tak, możesz uzyskać dostęp do [darmowej wersji próbnej](https://releases.aspose.com/), aby wypróbować funkcje przed zakupem.

### Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?
Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.

**Dodatkowe Pytania i Odpowiedzi**

**Q: Jak faktycznie ustawić nową datę zatrzymania dla zadania?**  
A: Użyj `tsk.set(Tsk.STOP, new Date(...));` i następnie zapisz projekt.

**Q: Czy mogę filtrować zadania według określonego zakresu zamiast tylko minimalnej daty?**  
A: Tak — porównaj zarówno `before`, jak i `after` względem dat początkowej i końcowej.

**Q: Czy API automatycznie przelicza harmonogram po zmianie dat zatrzymania/wznowienia?**  
A: Po modyfikacji dat wywołaj `project.calculateCriticalPath();`, aby odświeżyć harmonogram.

## Podsumowanie
W tym przewodniku omówiliśmy **jak wznowić zadanie** i **jak zatrzymać zadanie** przy użyciu Aspose.Tasks for Java, wraz z praktyczną metodą **filtrowania zadań po dacie**. Integrując te fragmenty kodu w swojej aplikacji, zyskujesz precyzyjną kontrolę nad harmonogramem projektu i możesz automatycznie dostosowywać plan z pewnością.

---

**Ostatnia aktualizacja:** 2026-02-26  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}