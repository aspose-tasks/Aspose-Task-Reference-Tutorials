---
date: 2026-02-26
description: Dowiedz się, jak podzielić daty zakończenia zadań i zarządzać harmonogramami
  projektów przy użyciu Aspose.Tasks dla Javy. Ten przewodnik pokazuje, jak efektywnie
  podzielić zadanie.
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zarządzaj harmonogramami projektu – podziel datę zakończenia zadania w Aspose.Tasks
url: /pl/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Data zakończenia podzielonego zadania w Aspose.Tasks

## Wprowadzenie
Skuteczne **zarządzanie terminami projektu** jest podstawą udanej realizacji projektu. Gdy zmienia się czas trwania zadania, jego data zakończenia musi zostać przeliczona, aby harmonogram był dokładny. W tym samouczku pokażemy, **jak podzielić daty zakończenia zadania** przy użyciu Aspose.Tasks dla Javy, dając Ci precyzyjną kontrolę nad harmonogramem projektu.

## Szybkie odpowiedzi
- **Co osiąga podzielenie daty zakończenia zadania?** Pozwala obliczyć datę końcową dla dowolnego czasu trwania, pomagając na bieżąco dostosowywać harmonogramy.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (do pobrania ze strony oficjalnej).  
- **Czy potrzebna jest licencja do rozwoju?** Tymczasowa licencja działa w testach; pełna licencja jest wymagana w produkcji.  
- **Czy mogę używać tego z dowolnym kalendarzem projektu?** Tak, API korzysta z kalendarza projektu, aby uwzględniać dni robocze i święta.  
- **Ile linii kodu jest potrzebnych?** Mniej niż dziesięć linii, aby uzyskać datę zakończenia dla dowolnego czasu trwania.

## Co oznacza „zarządzanie terminami projektu” w kontekście Aspose.Tasks?
Zarządzanie terminami projektu oznacza utrzymywanie dat rozpoczęcia i zakończenia każdego zadania w synchronizacji z ogólnym harmonogramem, uwzględniając kalendarze, zasoby i zależności zadań. Dokładne obliczenia dat zakończenia są niezbędne do realistycznych prognoz i zaufania interesariuszy.

## Dlaczego podzielić datę zakończenia zadania?
- **Elastyczność:** Szybko zobacz, jak różne przydziały godzin pracy wpływają na termin dostawy.  
- **Ocena ryzyka:** Oceń scenariusze „co‑by‑było”, nie modyfikując pierwotnego planu.  
- **Planowanie zasobów:** Dopasuj czasy trwania zadań do pojemności zespołu i ograniczeń kalendarza.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawową znajomość programowania w Javie.  
- Zainstalowaną bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).  
- Skonfigurowane środowisko programistyczne Java.

## Importowanie pakietów
Rozpocznij od dołączenia niezbędnych pakietów w swoim projekcie Java:
```java
import com.aspose.tasks.*;
```

## Krok 1: Znalezienie podzielonego zadania
Zlokalizuj zadanie, które chcesz podzielić w projekcie:
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## Krok 2: Znalezienie kalendarza projektu
Pobierz kalendarz projektu, aby uzyskać dokładne obliczenia dat:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## Krok 3: Obliczanie daty zakończenia zadania dla różnych czasów trwania
Teraz oblicz datę zakończenia zadania dla różnych czasów trwania.

### Krok 3.1: Czas trwania 8 godzin
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*Powtórz powyższy kod dla różnych czasów trwania, odpowiednio dostosowując liczbę godzin, aby zobaczyć, jak każda zmiana wpływa na datę zakończenia.*

## Częste problemy i rozwiązania
- **Nieprawidłowe odniesienie do kalendarza:** Upewnij się, że pobierasz kalendarz projektu (`project.get(Prj.CALENDAR)`) zamiast tworzyć nowy.  
- **Nieprawidłowy UID zadania:** UID musi odpowiadać istniejącemu zadaniu; w przeciwnym razie `getByUid` zwraca `null` i powoduje `NullPointerException`.  
- **Niezgodności strefy czasowej:** API działa w strefie czasowej kalendarza; sprawdź domyślną strefę systemu, jeśli wyniki wydają się nieprawidłowe.

## Zakończenie
Opanowanie sztuki **zarządzania terminami projektu** poprzez podział dat zakończenia zadań jest kluczowe dla efektywnego zarządzania projektami. Aspose.Tasks for Java upraszcza ten proces, umożliwiając płynne usprawnienie harmonogramów.

## FAQ
### P1: Jak mogę pobrać Aspose.Tasks for Java?
O1: Możesz go pobrać [tutaj](https://releases.aspose.com/tasks/java/).

### P2: Gdzie mogę znaleźć dokumentację Aspose.Tasks?
O2: Zapoznaj się z dokumentacją [tutaj](https://reference.aspose.com/tasks/java/).

### P3: Jak uzyskać tymczasową licencję na Aspose.Tasks?
O3: Uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### P4: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
O4: Odwiedź forum wsparcia [tutaj](https://forum.aspose.com/c/tasks/15).

### P5: Czy mogę kupić Aspose.Tasks?
O5: Tak, możesz go kupić [tutaj](https://purchase.aspose.com/buy).

## Dodatkowe często zadawane pytania

**Q: Czy mogę używać tej techniki z własnym kalendarzem?**  
**A:** Oczywiście. Po prostu zamień `project.get(Prj.CALENDAR)` na swoją własną instancję `Calendar`.

**Q: Czy metoda uwzględnia dni niepracujące?**  
**A:** Tak, definicje czasu pracy kalendarza są stosowane przy obliczaniu daty zakończenia.

**Q: Czy istnieje sposób na uzyskanie daty zakończenia dla ułamkowych godzin (np. 3,5 godziny)?**  
**A:** Przekaż wartość `double`, taką jak `3.5d`, do `getTaskFinishDateFromDuration`; API obsługuje ułamkowe czasy trwania.

**Q: Jak sformatować wyjściową datę?**  
**A:** Użyj `java.time.format.DateTimeFormatter` na zwróconym obiekcie `Date`, aby wyświetlić go w wybranym formacie.

---

**Ostatnia aktualizacja:** 2026-02-26  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}