---
date: 2026-07-14
description: Dowiedz się, jak zatrzymać przydzielanie zasobów w Javie, zarządzać przydziałami
  zasobów i przeglądać przykłady przy użyciu Aspose.Tasks for Java w tym przewodniku
  krok po kroku.
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: Zatrzymaj i wznów przydziały zasobów w Aspose.Tasks
og_description: Zatrzymaj przydzielanie zasobów w Javie przy użyciu Aspose.Tasks.
  Ten samouczek pokazuje, jak wstrzymać i wznowić przydziały, obsługiwać daty oraz
  integrować API bez Microsoft Project.
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: Zatrzymaj przydzielanie zasobów w Javie – przewodnik Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: Jak zatrzymać przydzielanie zasobów w Javie – wznów z Aspose.Tasks
url: /pl/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zatrzymać przydział zasobów w Javie – wznowienie przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku dowiesz się **jak zatrzymać przydział zasobów w Javie** i później go wznowić przy użyciu Aspose.Tasks dla Javy. Aspose.Tasks to solidne API Java, które pozwala czytać i zapisywać pliki Microsoft Project, manipulować harmonogramami i kontrolować przydziały zasobów — wszystko bez konieczności instalacji Microsoft Project. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każda linia ma znaczenie, i podzielimy się praktycznymi wskazówkami, które możesz zastosować w rzeczywistych planach projektów.

## Szybkie odpowiedzi
- **Co oznacza „zatrzymanie przydziału”?** Oznacza to, że przydział zasobu jest tymczasowo nieaktywny od określonej daty zatrzymania.  
- **Czy mogę później wznowić ten sam przydział?** Tak, ustawiając datę wznowienia w tym samym przydziale.  
- **Czy potrzebuję Microsoft Project, aby używać tego API?** Nie, Aspose.Tasks działa niezależnie od Microsoft Project.  
- **Jaka wersja Javy jest wymagana?** Zalecana jest Java 8 lub nowsza.  
- **Gdzie mogę pobrać bibliotekę?** Ze strony oficjalnego pobierania Aspose.Tasks Java.

## Jak zatrzymać przydział zasobów w Javie?
Załaduj swój projekt, znajdź docelowy `ResourceAssignment`, ustaw datę `STOP`, opcjonalnie ustaw datę `RESUME`, a następnie zapisz plik. Ta sekwencja wstrzymuje pracę na określony okres i automatycznie ją ponownie aktywuje po dacie wznowienia, dając precyzyjną kontrolę nad kalendarzami zasobów bez ręcznej edycji pliku.

## Co oznacza „jak zatrzymać przydział” w kontekście Aspose.Tasks?
Zatrzymanie przydziału informuje harmonogram, aby ignorował pracę przydzieloną zasobowi po **dacie zatrzymania** aż do **daty wznowienia** (jeśli istnieje). Jest to przydatne przy obsłudze urlopów, przestojów sprzętu lub dowolnego okresu, w którym zasób nie powinien być uznawany za aktywny.

## Dlaczego warto używać Aspose.Tasks do zarządzania przydziałami zasobów?
Aspose.Tasks pozwala programowo kontrolować daty przydziałów, eliminując ręczne edycje i zmniejszając ryzyko błędów. Obsługuje **ponad 50 formatów wejściowych i wyjściowych** oraz może przetwarzać projekty z **do 10 000 zadaniami**, utrzymując zużycie pamięci poniżej 200 MB, ponieważ strumieniuje dane zamiast ładować cały plik do pamięci. API działa na każdym systemie operacyjnym obsługującym Javę, zapewniając elastyczność wieloplatformową.

## Wymagania wstępne
- Zainstalowany Java Development Kit (JDK) 8 lub nowszy.  
- Pobraną bibliotekę Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).  
- Podstawowa znajomość programowania w Javie.  

## Importowanie pakietów
Klasy `Project`, `ResourceAssignment` i `Asn` znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku swojego pliku źródłowego:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Krok 1: Załaduj plik projektu
Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Microsoft Project w pamięci. Utworzenie instancji ładuje plik i daje dostęp do zadań, zasobów i przydziałów.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## Krok 2: Iteruj przez przydziały zasobów
Obiekty `ResourceAssignment` udostępniają wszystkie pola związane z przydziałami. Ustawiamy **minimalną datę**, aby odfiltrować daty zastępcze, a następnie iterujemy po każdym przydziale. Ten wzorzec jest standardowym *przykładem przydziału zasobów* do inspekcji lub modyfikacji.

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## Krok 3: Sprawdź daty STOP i RESUME
W tym bloku sprawdzamy pola `STOP` i `RESUME` dla każdego przydziału. Jeśli data jest wcześniejsza niż nasza `minDate`, traktujemy ją jako nieustawioną (`"NA"`); w przeciwnym razie wyświetlamy rzeczywistą datę. Ta logika jest niezbędna do prawidłowego **zarządzania przydziałami zasobów**.

```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

## Typowe problemy i rozwiązania
- **Daty null** – `ra.get(Asn.STOP)` może zwrócić `null`. Zabezpiecz się przed tym, dodając sprawdzenie null przed wywołaniem `.before(minDate)`.  
- **Nieprawidłowa ścieżka pliku** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`/` lub `\\`) odpowiednim dla Twojego systemu operacyjnego.  
- **Niezgodność wersji** – Użyj najnowszej wersji Aspose.Tasks for Java, aby uniknąć brakujących wartości wyliczeń.

## Najczęściej zadawane pytania

**P: Jak programowo ustawić datę zatrzymania dla przydziału?**  
O: Użyj `ra.set(Asn.STOP, yourDateObject);`, gdzie `yourDateObject` jest obiektem `java.util.Date`.

**P: Co się stanie, jeśli data wznowienia jest wcześniejsza niż data zatrzymania?**  
O: API nie wymusza kolejności chronologicznej; jednak harmonogram będzie traktował przydział jako aktywny dopiero po późniejszej z tych dwóch dat, więc powinieneś samodzielnie walidować daty.

**P: Czy mogę filtrować przydziały, aby wyświetlać tylko te z ustawioną datą zatrzymania?**  
O: Tak, iteruj przez `prj.getResourceAssignments()` i sprawdzaj `ra.get(Asn.STOP) != null`.

**P: Czy można usunąć ustawioną datę zatrzymania?**  
O: Ustaw datę zatrzymania na `null` za pomocą `ra.set(Asn.STOP, null);`, a następnie zapisz projekt.

**P: Czy Aspose.Tasks obsługuje inne pola związane z datami, takie jak start, finish czy actual start?**  
O: Zdecydowanie tak. Enum `Asn` udostępnia stałe dla wszystkich pól przydziału, takich jak `Asn.START`, `Asn.FINISH` itp.

## Podsumowanie
Postępując zgodnie z tymi krokami, teraz wiesz **jak zatrzymać przydział zasobów w Javie**, sprawdzić daty zatrzymania/wznowienia i wznowić przydział w razie potrzeby. Ta możliwość pozwala **zarządzać przydziałami zasobów** precyzyjniej, szczególnie w sytuacjach takich jak urlopy zasobów czy przestoje sprzętu. Śmiało rozbudowuj przykład, aby aktualizować daty, generować raporty lub integrować go z własną logiką harmonogramowania.

---

**Ostatnia aktualizacja:** 2026-07-14  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Tworzenie przydziałów zasobów w Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Jak obliczyć odchylenie kosztów i zarządzać kosztami przydziałów w Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Jak dodać notatki do przydziałów zasobów w Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}