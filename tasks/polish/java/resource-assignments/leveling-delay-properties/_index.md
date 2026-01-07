---
date: 2026-01-07
description: Dowiedz się, jak dodać zasób do projektu i obsługiwać właściwości opóźnienia
  poziomowania dla przydziałów zasobów przy użyciu Aspose.Tasks for Java.
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak dodać zasób do projektu i obsłużyć właściwości opóźnienia poziomowania
  w Aspose.Tasks
url: /pl/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać zasób do projektu i obsłużyć właściwości opóźnienia poziomowania w Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się **jak dodać zasób do projektu**, jednocześnie zarządzając właściwościami opóźnienia poziomowania dla przydziałów zasobów przy użyciu Aspose.Tasks dla Javy. Niezależnie od tego, czy budujesz silnik harmonogramowania, czy automatyzujesz aktualizacje projektu, opanowanie tych kroków pozwoli Ci utrzymać dane projektu w dokładności bez konieczności instalacji Microsoft Project.

## Szybkie odpowiedzi
- **Co oznacza „dodanie zasobu do projektu”?** Tworzy nowy wpis zasobu, który może być przypisany do zadań.  
- **Czy mogę ustawić opóźnienie poziomowania po przydzieleniu?** Tak, używając pól `Asn.DELAY` lub `Asn.LEVELING_DELAY`.  
- **Czy potrzebna jest licencja do uruchomienia tego kodu?** Bezpłatna wersja próbna wystarcza do rozwoju; licencja płatna jest wymagana w środowisku produkcyjnym.  
- **Jaką wersję Javy obsługuje?** Java 8 lub nowsza.  
- **Czy jest to kompatybilne ze wszystkimi formatami plików MS Project?** Aspose.Tasks obsługuje .MPP, .XML, .XER i inne.

## Co oznacza „dodanie zasobu do projektu” w Aspose.Tasks?
Dodanie zasobu do projektu oznacza utworzenie obiektu `Resource` wewnątrz modelu `Project`. Obiekt ten może później zostać powiązany z zadaniami za pomocą `ResourceAssignment`, co umożliwia śledzenie pracy, kosztów i ustawień poziomowania.

## Dlaczego obsługiwać właściwości opóźnienia poziomowania?
Opóźnienie poziomowania pomaga harmonogramowi rozłożyć pracę, gdy zasoby są nadmiernie przydzielone. Ustawiając opóźnienie, informujesz silnik, aby odłożył rozpoczęcie przydziału, unikając konfliktów i utrzymując projekt realistycznym.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:
1. **Java Development Kit (JDK):** Upewnij się, że masz zainstalowany Java JDK. Możesz go pobrać i zainstalować ze [strony internetowej](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. **Biblioteka Aspose.Tasks dla Javy:** Pobierz bibliotekę Aspose.Tasks dla Javy ze [strony pobierania](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Najpierw zaimportuj niezbędne pakiety do swojego projektu Java, aby korzystać z funkcjonalności Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Utworzenie obiektu projektu
Zainicjuj obiekt `Project`, który będzie kontenerem dla wszystkich zadań, zasobów i przydziałów:
```java
Project prj = new Project();
```

## Krok 2: Utworzenie zadania
Dodaj zadanie do projektu. To demonstruje **jak dodać zadanie** programowo:
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Krok 3: Ustawienie daty rozpoczęcia i czasu trwania zadania
Zdefiniuj, kiedy zadanie się rozpoczyna i jak długo będzie trwać:
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Krok 4: Dodanie zasobu
Teraz **dodajemy zasób do projektu**, tworząc nowy wpis `Resource`:
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Krok 5: Utworzenie przydziału zasobu
Połącz zadanie i nowo dodany zasób:
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Krok 6: Ustawienie opóźnienia poziomowania
Skonfiguruj opóźnienie poziomowania dla przydziału. Ustawienie go na zero oznacza brak dodatkowego opóźnienia, ale możesz dostosować wartość w razie potrzeby:
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Krok 7: Wyświetlenie wyników
Wydrukuj istotne właściwości, aby zweryfikować, że wszystko zostało poprawnie ustawione:
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Typowe pułapki i wskazówki
- **Pułapka:** Zapomnienie o ustawieniu daty rozpoczęcia zadania może spowodować, że przydział domyślnie zacznie się od daty rozpoczęcia projektu.  
- **Wskazówka:** Użyj `prj.getDuration(value, TimeUnitType.Day)`, aby kontrolować szczegółowość opóźnienia.  
- **Wskazówka:** Po dodaniu wielu zasobów, wywołaj `prj.updateResourceAssignments()`, aby harmonogram przeliczył poziomowanie.

## Zakończenie
Postępując zgodnie z tymi krokami, teraz wiesz **jak dodać zasób do projektu**, przypisać go do zadania i zarządzać właściwościami opóźnienia poziomowania przy użyciu Aspose.Tasks dla Javy. Ta wiedza pozwala budować solidne rozwiązania automatyzacji projektów, które pozostają zgodne z rzeczywistymi ograniczeniami zasobów.

## FAQ
### P: Czy mogę używać Aspose.Tasks z innymi bibliotekami Javy?

O: Tak, Aspose.Tasks może być integrowany z innymi bibliotekami Javy w celu rozszerzenia możliwości zarządzania projektami.

### P: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?

O: Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność w różnych środowiskach.

### P: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks?

O: Wsparcie i zasoby znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### P: Czy mogę wypróbować Aspose.Tasks przed zakupem?

O: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks ze [strony wydań](https://releases.aspose.com/).

### P: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?

O: Tymczasową licencję możesz zamówić na [stronie tymczasowej licencji](https://purchase.aspose.com/temporary-license/) w celu oceny.

## Dodatkowe często zadawane pytania

**P: Co się stanie, jeśli ustawiam niezerowe opóźnienie poziomowania?**  
O: Harmonogram odłoży rozpoczęcie przydziału o określony czas, pomagając rozwiązać nadmierne przydziały.

**P: Czy mogę odczytać opóźnienie poziomowania po zapisaniu projektu?**  
O: Tak, możesz ponownie otworzyć plik projektu i odczytać właściwość `Asn.DELAY` z przydziału.

**P: Czy istnieje sposób, aby zastosować opóźnienie poziomowania do wszystkich przydziałów jednocześnie?**  
O: Możesz iterować przez `prj.getResourceAssignments()` i ustawiać opóźnienie dla każdego przydziału w pętli.

---

**Ostatnia aktualizacja:** 2026-01-07  
**Testowane z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}