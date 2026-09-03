---
date: 2026-06-05
description: Dowiedz się, jak utworzyć przydział zasobów przy użyciu Aspose.Tasks
  dla Javy, dodać zasoby do projektu i zarządzać właściwościami opóźnienia poziomowania.
keywords:
- create resource assignment aspotasks
- Aspose.Tasks Java
- leveling delay properties
linktitle: Obsługa właściwości opóźnienia poziomowania dla przydziałów zasobów w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to create resource assignment with Aspose.Tasks for Java,
    add resources to a project, and manage leveling delay properties.
  headline: Create Resource Assignment with Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates smoothly with libraries such as Jackson for
      JSON handling or Apache POI for additional spreadsheet operations, allowing
      you to build richer project‑management solutions.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Aspose.Tasks supports 12+ file formats—including .MPP (2003‑2021), .XML,
      .XER, .CSV, .PDF, .HTML, and .MPP12—ensuring seamless round‑trip editing across
      all major Project versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: You can find support and community discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, a fully functional free trial is available from the [releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Request a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to run the library without evaluation restrictions.
    question: How can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Utwórz przydział zasobów przy użyciu Aspose.Tasks dla Javy
url: /pl/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz przydział zasobów za pomocą Aspose.Tasks dla Javy

W tym kompleksowym przewodniku nauczysz się **how to create resource assignment aspotasks** przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy budujesz własny silnik harmonogramowania, automatyzujesz masowe aktualizacje projektów, czy po prostu potrzebujesz manipulować plikami Microsoft Project bez aplikacji desktopowej, opanowanie tych kroków pozwoli Ci utrzymać dane projektu dokładne i w pełni kontrolowane.

## Szybkie odpowiedzi
- **Co oznacza „add resource to project”?** Tworzy nowy wpis zasobu, który później może być przypisany do zadań.  
- **Czy mogę ustawić opóźnienie poziomowania po przydziale?** Tak, używając pól `Asn.DELAY` lub `Asn.LEVELING_DELAY`.  
- **Czy potrzebna jest licencja do uruchomienia tego kodu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja płatna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 lub nowsza.  
- **Czy jest to kompatybilne ze wszystkimi formatami plików MS Project?** Aspose.Tasks obsługuje ponad 12 formatów — w tym .MPP, .XML, .XER, .CSV, .PDF i inne.

## Co oznacza „add resource to project” w Aspose.Tasks?
Dodanie zasobu do projektu oznacza utworzenie obiektu `Resource` wewnątrz modelu `Project`. Obiekt ten może później być powiązany z zadaniami za pomocą `ResourceAssignment`, umożliwiając śledzenie pracy, kosztów i ustawień poziomowania. Wstawiając zasób, dajesz harmonogramowi coś do przydzielenia i możesz później zapytać lub zmodyfikować jego właściwości, takie jak dostępność, stawki i przypisania kalendarza.

## Dlaczego obsługiwać właściwości opóźnienia poziomowania?
Opóźnienie poziomowania informuje harmonogram, aby opóźnić rozpoczęcie przydziału przekraczającego dostępność, rozkładając pracę równomierniej w czasie. Konfigurując to opóźnienie, unikasz nierealistycznych dat rozpoczęcia, zmniejszasz ostrzeżenia o przekroczeniu zasobów i tworzysz harmonogram odzwierciedlający rzeczywiste ograniczenia zasobów. Dostosowanie opóźnienia daje także precyzyjną kontrolę nad tym, ile luzu silnik może wstawić, pomagając spełnić terminy projektu przy jednoczesnym poszanowaniu limitów zasobów.

## Jak utworzyć przydział zasobów aspotasks?
Załaduj obiekt `Project`, dodaj zadanie, utwórz zasób, a następnie powiąż je razem za pomocą `ResourceAssignment`. Ten przepływ od początku do końca pozwala programowo zbudować pełną strukturę projektu i natychmiast kontrolować opóźnienie poziomowania przydziału. Proces demonstruje podstawowy przebieg pracy: inicjalizacja projektu, definiowanie zadania, tworzenie zasobu, łączenie przydziału i w końcu zastosowanie parametrów harmonogramowania, takich jak opóźnienie poziomowania.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany Java JDK na swoim systemie. Możesz go pobrać i zainstalować ze [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. Aspose.Tasks for Java Library: Pobierz bibliotekę Aspose.Tasks for Java ze [download page](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Poniższe importy wprowadzają podstawowe klasy Aspose.Tasks potrzebne do manipulacji projektem.  
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

## Jak utworzyć przydział zasobów aspotasks?
Załaduj obiekt `Project`, dodaj zadanie, utwórz zasób, a następnie powiąż je razem za pomocą `ResourceAssignment`. Ten przepływ od początku do końca pozwala programowo zbudować pełną strukturę projektu i natychmiast kontrolować opóźnienie poziomowania przydziału. Proces demonstruje podstawowy przebieg pracy: inicjalizacja projektu, definiowanie zadania, tworzenie zasobu, łączenie przydziału i w końcu zastosowanie parametrów harmonogramowania, takich jak opóźnienie poziomowania.

## Krok 1: Utwórz obiekt Project
Klasa `Project` jest najwyższym kontenerem Aspose.Tasks, który reprezentuje cały plik projektu w pamięci. Utworzenie jej daje czystą bazę do dodawania zadań, zasobów i przydziałów.
```java
Project prj = new Project();
```

## Krok 2: Utwórz zadanie
Klasa `Task` reprezentuje pojedynczy element pracy w harmonogramie. Dodanie zadania demonstruje **how to add task** programowo i zapewnia cel dla nadchodzącego przydziału zasobu.
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## Krok 3: Ustaw datę rozpoczęcia zadania i czas trwania
Zdefiniuj, kiedy zadanie się rozpoczyna i jak długo będzie trwać. Prawidłowe daty rozpoczęcia są niezbędne, ponieważ obliczenia poziomowania używają ich jako podstawy dla wszelkich opóźnień, które później określisz.
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## Krok 4: Dodaj zasób
Teraz **add resource to project** poprzez utworzenie nowego wpisu `Resource`. Klasa `Resource` jest reprezentacją osoby, sprzętu lub materiału, który może być przydzielony do zadań.
```java
Resource resource = prj.getResources().add("Resource 1");
```

## Krok 5: Utwórz przydział zasobu
`ResourceAssignment` łączy `Task` i `Resource`. To powiązanie pozwala rejestrować pracę, koszty i szczegóły poziomowania dla konkretnego zasobu w konkretnym zadaniu.
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## Krok 6: Ustaw opóźnienie poziomowania
Skonfiguruj opóźnienie poziomowania dla przydziału. Ustawienie go na zero oznacza brak dodatkowego opóźnienia, ale możesz dostosować wartość w razie potrzeby. Pole `Asn.DELAY` przechowuje opóźnienie w minutach; `Asn.LEVELING_DELAY` jest aliasem działającym w ten sam sposób.
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## Krok 7: Wyświetl wyniki
Wydrukuj ważne właściwości, aby zweryfikować, że wszystko zostało poprawnie ustawione. Ten krok pomaga potwierdzić, że wartości zasobu, zadania i opóźnienia są dokładnie takie, jakich oczekujesz przed zapisaniem pliku.
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## Częste pułapki i wskazówki
- **Pitfall:** Zapomnienie ustawienia daty rozpoczęcia zadania może spowodować, że przydział domyślnie zacznie się od początku projektu.  
- **Tip:** Użyj `prj.getDuration(value, TimeUnitType.Day)`, aby kontrolować szczegółowość opóźnienia.  
- **Tip:** Po dodaniu wielu zasobów, wywołaj `prj.updateResourceAssignments()`, aby harmonogram przeliczył poziomowanie.  
- **Pro tip:** Dla dużych projektów (10 000+ zadań) włącz `prj.setAutoCalculate(false)` przed masowymi aktualizacjami, a następnie wywołaj `prj.calculate()` raz na końcu, aby poprawić wydajność.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks z innymi bibliotekami Javy?**  
A: Tak, Aspose.Tasks integruje się płynnie z bibliotekami takimi jak Jackson do obsługi JSON lub Apache POI do dodatkowych operacji na arkuszach kalkulacyjnych, co pozwala budować bogatsze rozwiązania do zarządzania projektami.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Aspose.Tasks obsługuje ponad 12 formatów — w tym .MPP (2003‑2021), .XML, .XER, .CSV, .PDF, .HTML oraz .MPP12 — zapewniając płynną edycję w obie strony we wszystkich głównych wersjach Project.

**Q: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks?**  
A: Wsparcie i dyskusje społecznościowe znajdziesz na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak, w pełni funkcjonalna wersja próbna jest dostępna na [releases page](https://releases.aspose.com/).

**Q: Jak mogę uzyskać tymczasową licencję do oceny?**  
A: Poproś o tymczasową licencję na [temporary license page](https://purchase.aspose.com/temporary-license/), aby uruchomić bibliotekę bez ograniczeń oceny.

---

**Ostatnia aktualizacja:** 2026-06-05  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Powiązane samouczki

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Manage Assignment Budget Java using Aspose.Tasks](/tasks/java/resource-assignments/assignment-budget/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}