---
date: 2026-03-29
description: Dowiedz się, jak przerejestrować niewykonaną pracę, zaktualizować pracę
  w projekcie i zapisać pliki MS Project jako XML przy użyciu Aspose.Tasks dla Javy.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zaplanuj ponownie niewykonaną pracę i zaktualizuj pliki MS Project przy użyciu
  Aspose.Tasks
url: /pl/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przebuduj niewykonaną pracę i zaktualizuj pliki MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
Microsoft Project to powszechnie używane narzędzie do zarządzania projektami, które pomaga zespołom planować zadania, przydzielać zasoby i śledzić terminy. Aspose.Tasks for Java udostępnia programistom bogate API do programowego manipulowania plikami Microsoft Project. W tym samouczku dowiesz się, jak **zaktualizować pracę w projekcie**, **przebudować niewykonaną pracę** oraz **zapisać plik MS Project** w formacie XML przy użyciu Aspose.Tasks for Java.

## Szybkie odpowiedzi
- **Co oznacza „przebudowanie niewykonanej pracy”?** Przenosi pozostałą pracę zadania, aby rozpoczęła się po wybranej dacie, pozostawiając ukończone części niezmienione.  
- **Która metoda oznacza pracę jako ukończoną?** `project.updateProjectWorkAsComplete(date, false)`.  
- **Jak zachować zmiany?** Użyj `project.save(<path>, SaveFileFormat.Xml)`.  
- **Czy potrzebna jest licencja do produkcji?** Tak, ważna licencja Aspose.Tasks jest wymagana do użytku komercyjnego.  
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze są w pełni obsługiwane.

## Co to jest „przebudowanie niewykonanej pracy”?
Przebudowanie niewykonanej pracy dostosowuje daty rozpoczęcia wszystkich zadań, które nie zostały jeszcze zakończone, przesuwając je tak, aby rozpoczęły się po określonej dacie granicznej. Jest to przydatne, gdy harmonogram projektu zmienia się z powodu opóźnień lub zmian zakresu.

## Dlaczego warto używać Aspose.Tasks do aktualizacji pracy w projekcie i przebudowy zadań?
- **Precyzyjna kontrola:** Bezpośrednie ustawianie procentów ukończenia pracy i dat.  
- **Brak wymogu interfejsu UI:** Automatyzacja masowych aktualizacji w wielu plikach projektów.  
- **Wieloplatformowość:** Działa na każdym systemie, na którym można uruchomić Javę.  
- **Zachowanie integralności danych:** Wszystkie zależności, ograniczenia i zasoby pozostają spójne.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:
1. Zainstalowany Java Development Kit (JDK) na swoim komputerze.  
2. Bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).  
3. Podstawową znajomość języka programowania Java.

## Importowanie pakietów
Najpierw zaimportuj niezbędne pakiety w swoim kodzie Java:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Konfiguracja projektu
Zainicjuj nowy obiekt `Project`, zdefiniuj zadania, ustaw ich czas trwania i ustanów zależności. To tworzy bazowy projekt, który później zaktualizujemy i przebudujemy.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Krok 2: Aktualizacja pracy w projekcie
Oznacz pracę jako ukończoną do określonej daty. Ten krok demonstruje operację **update project work**, która często jest pierwszą akcją przed przebudową.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Krok 3: Przebudowanie niewykonanej pracy
Teraz przesuwamy wszelką pozostałą (niewykonaną) pracę tak, aby rozpoczęła się po tej samej dacie granicznej. To jest sedno funkcjonalności **reschedule uncompleted work**.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Zakończenie
W tym samouczku omówiliśmy, jak **zaktualizować pracę w projekcie**, **przebudować niewykonaną pracę** oraz **zapisać plik MS Project** jako XML przy użyciu Aspose.Tasks for Java. Te możliwości są niezbędne, gdy terminy projektów muszą być dostosowane do rzeczywistego postępu lub zmieniających się priorytetów biznesowych.

## Najczęściej zadawane pytania
### Q: Czy Aspose.Tasks dla Javy radzi sobie ze złożonymi strukturami projektów?
A: Tak, Aspose.Tasks dla Javy udostępnia solidne API do efektywnego zarządzania zadaniami, zależnościami, zasobami i innymi elementami projektu.
### Q: Czy dostępna jest wersja próbna Aspose.Tasks dla Javy?
A: Tak, darmową wersję próbną można uzyskać [tutaj](https://releases.aspose.com/).
### Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Javy?
A: Możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc lub zadać pytania.
### Q: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Javy?
A: Tak, tymczasowe licencje są dostępne do zakupu [tutaj](https://purchase.aspose.com/temporary-license/).
### Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks dla Javy?
A: Dokumentację można znaleźć [tutaj](https://reference.aspose.com/tasks/java/), zawierającą kompleksowe przewodniki i odniesienia do API.

## Dodatkowe często zadawane pytania

**P: Jak zapewnić, że zapisany plik jest kompatybilny ze starszymi wersjami Microsoft Project?**  
A: Zapisz projekt używając `SaveFileFormat.Xml`; XML jest szeroko obsługiwany we wszystkich wersjach Project.

**P: Czy mogę przebudować tylko podzbiór zadań zamiast całego projektu?**  
A: Tak, możesz iterować po konkretnych zadaniach i wywołać `task.setStart(date)` po obliczeniu nowej daty rozpoczęcia.

**P: Co się dzieje z przydziałami zasobów przy przebudowie niewykonanej pracy?**  
A: Przypisania zasobów są automatycznie przesuwane, aby pasowały do nowych dat rozpoczęcia zadań, zachowując logikę przydziału.

**P: Czy można programowo cofnąć operację przebudowy?**  
A: Można ponownie wczytać oryginalny plik projektu (lub kopię zapasową), aby przywrócić zmiany.

**P: Czy Aspose.Tasks obsługuje zapisywanie do innych formatów, takich jak .mpp?**  
A: Oczywiście. Użyj `SaveFileFormat.MPP`, aby zapisać w natywnym formacie Microsoft Project.

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}