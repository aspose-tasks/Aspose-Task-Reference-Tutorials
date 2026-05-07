---
date: 2026-02-23
description: Dowiedz się, jak zarządzać nadgodzinami w zadaniach projektowych przy
  użyciu Aspose.Tasks dla Javy, w tym jak obliczyć koszt nadgodzin i uprościć śledzenie
  zasobów.
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak zarządzać nadgodzinami w zadaniach przy użyciu Aspose.Tasks
url: /pl/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zarządzać nadgodzinami w zadaniach przy użyciu Aspose.Tasks

## Introduction
Jeśli szukasz **jak zarządzać nadgodzinami** w pliku Microsoft Project, trafiłeś we właściwe miejsce. W tym samouczku pokażemy, jak Aspose.Tasks for Java pozwala czytać, modyfikować i raportować właściwości związane z nadgodzinami każdego zadania, abyś mógł utrzymać swój harmonogram i budżet w dokładności.  

## Quick Answers
- **Co oznacza „nadgodziny” w projekcie?** Dodatkowe godziny pracy ponad regularną pojemność zasobu.  
- **Która klasa API dostarcza dane o nadgodzinach?** `Task` z kolekcją pól `Tsk` (np. `Tsk.OVERTIME_COST`).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Tak, wymagana jest tymczasowa lub pełna licencja Aspose.Tasks do użytku produkcyjnego.  
- **Czy mogę automatycznie obliczyć koszt nadgodzin?** Oczywiście – pobierz `Tsk.OVERTIME_COST` i zastosuj swoją logikę stawek kosztowych.  
- **Czy jest to kompatybilne z Java 17?** Tak, Aspose.Tasks for Java obsługuje Java 8 i nowsze.

## What is Overtime Management in Project Tasks?
Zarządzanie nadgodzinami oznacza śledzenie dodatkowej pracy i kosztów, które pojawiają się, gdy zasoby przekraczają swój normalny czas pracy. Dokładne rejestrowanie tych danych pomaga prognozować budżety, dostosowywać harmonogramy i raportować realistyczny stan projektu.

## Why Use Aspose.Tasks for Overtime?
* **Microsoft Project nie jest wymagany** – pracuj bezpośrednio z plikami .MPP.  
* **Pełny dostęp do pól nadgodzin** – wartości kosztu, pracy i procentu ukończenia są udostępniane przez wyliczenie `Tsk`.  
* **Programowa kontrola** – możesz odczytywać, modyfikować lub obliczać koszt nadgodzin bez ręcznych kroków w interfejsie użytkownika.

## Prerequisites
Zanim zagłębisz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Środowisko programistyczne Java: Upewnij się, że masz skonfigurowane środowisko programistyczne Java na swoim komputerze.  
- Aspose.Tasks for Java: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Bibliotekę i jej dokumentację znajdziesz [tutaj](https://reference.aspose.com/tasks/java/).  
- Plik projektu: Przygotuj plik projektu (np. TaskOvertimes.mpp), z którym będziesz pracować podczas samouczka.

## Import Packages
W swoim projekcie Java zaimportuj niezbędne pakiety Aspose.Tasks, aby wykorzystać ich funkcjonalności. Dodaj następujące instrukcje importu:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
Utworzenie nowego projektu (lub wczytanie istniejącego) jest pierwszym krokiem każdej analizy. To także spełnia drugorzędne słowo kluczowe **create new project**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
Teraz przejdziemy przez każde zadanie najwyższego poziomu, wyświetlimy jego informacje o nadgodzinach i pokażemy, jak **obliczyć koszt nadgodzin** poprzez odczyt pola `OVERTIME_COST`.

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **Wskazówka:** Wartość `OVERTIME_COST` jest już obliczana przez Aspose.Tasks na podstawie stawki nadgodzin zasobu. Jeśli potrzebujesz własnego obliczenia, pomnóż `OVERTIME_WORK` przez własną stawkę i zaktualizuj pole za pomocą `tsk.set(Tsk.OVERTIME_COST, yourValue);`.

## Common Issues and Solutions
| Problem | Rozwiązanie |
|-------|----------|
| **Null values for overtime fields** | Upewnij się, że źródłowy plik .MPP rzeczywiście zawiera dane o nadgodzinach; w przeciwnym razie pola zwracają `null`. |
| **Incorrect cost after modification** | Po zmianie pracy lub kosztu nadgodzin wywołaj `project.save()`, aby zapisać zmiany. |
| **License not found** | Umieść plik `Aspose.Tasks.lic` w katalogu głównym projektu lub ustaw licencję programowo przed wczytaniem projektu. |

## Frequently Asked Questions

**Q: Czy Aspose.Tasks jest odpowiedni do zarządzania projektami na dużą skalę?**  
A: Tak, Aspose.Tasks jest zaprojektowany tak, aby obsługiwać projekty o różnych rozmiarach, od małych inicjatyw po duże i złożone programy.

**Q: Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?**  
A: Absolutnie! Aspose.Tasks bezproblemowo integruje się ze Spring, Jakarta EE i innymi ekosystemami Java, zwiększając swoją wszechstronność.

**Q: Czy istnieją kwestie licencyjne związane z używaniem Aspose.Tasks?**  
A: Tak, szczegóły licencjonowania oraz możliwość uzyskania tymczasowej licencji znajdziesz [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę uzyskać pomoc lub dyskutować o pytaniach związanych z Aspose.Tasks?**  
A: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby skontaktować się ze społecznością i uzyskać wsparcie.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
A: Tak, darmową wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

**Q: Jak obliczyć koszt nadgodzin dla konkretnego zasobu?**  
A: Pobierz stawkę nadgodzin zasobu, pomnóż ją przez `OVERTIME_WORK` (w godzinach) i, jeśli potrzebujesz własnego obliczenia, ustaw wynik z powrotem w `OVERTIME_COST`.

## Conclusion
Aspose.Tasks for Java upraszcza **zarządzanie nadgodzinami** w zadaniach projektowych, dając programistom bezpośredni programowy dostęp do kosztów, pracy i wskaźników postępu nadgodzin. Postępując zgodnie z tym przewodnikiem, możesz wczytać projekt, odczytać szczegóły nadgodzin, dostosować procenty i nawet obliczyć własne koszty nadgodzin — wszystko bez otwierania Microsoft Project.

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** Aspose.Tasks for Java (latest version)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}