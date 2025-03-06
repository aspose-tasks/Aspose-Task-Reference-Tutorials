---
title: Zatrzymaj i wznów przydziały zasobów w Aspose.Tasks
linktitle: Zatrzymaj i wznów przydziały zasobów w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak efektywnie zarządzać przydziałami zasobów w Aspose.Tasks dla Java, korzystając z tego samouczka krok po kroku.
weight: 23
url: /pl/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zatrzymaj i wznów przydziały zasobów w Aspose.Tasks

## Wstęp
W tym samouczku dowiemy się, jak zatrzymywać i wznawiać przydzielanie zasobów za pomocą Aspose.Tasks dla Java. Aspose.Tasks to potężny interfejs API języka Java, który umożliwia programistom pracę z plikami programu Microsoft Project bez konieczności instalowania programu Microsoft Project w ich systemach. Podzielimy ten proces na łatwe do wykonania kroki, aby ułatwić jego śledzenie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Pobrano bibliotekę Aspose.Tasks dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
- Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do naszego projektu Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## Krok 1: Załaduj plik projektu
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
// Załaduj plik projektu
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
 W tym kroku ładujemy plik projektu do pliku`Project` obiekt przy użyciu ścieżki pliku.
## Krok 2: Iteruj po przypisaniach zasobów
```java
// Określ minimalną datę
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iteruj poprzez przypisania zasobów
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
Tutaj definiujemy minimalną datę i rozpoczynamy iterację każdego przypisania zasobów w projekcie.
## Krok 3: Sprawdź daty zakończenia i wznowienia
```java
    // Sprawdź datę zatrzymania
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Sprawdź datę wznowienia
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
Na tym etapie sprawdzamy, czy daty zakończenia i wznowienia każdego przydziału zasobów są wcześniejsze niż data minimalna. Jeżeli tak, drukujemy „NA”, w przeciwnym razie drukujemy odpowiednie daty.
## Wniosek
W tym samouczku dowiedzieliśmy się, jak zatrzymywać i wznawiać przydziały zasobów w Aspose.Tasks dla Java. Postępując zgodnie z podanymi krokami, możesz łatwo zaimplementować tę funkcjonalność w swoich projektach Java.

## Często zadawane pytania
### Czy mogę używać Aspose.Tasks bez zainstalowanego programu Microsoft Project?
Tak, Aspose.Tasks umożliwia pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project w systemie.
### Gdzie mogę znaleźć więcej dokumentacji?
 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/tasks/java/).
### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz skorzystać z bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy?
Możesz uzyskać wsparcie od społeczności[Tutaj](https://forum.aspose.com/c/tasks/15).
### Czy mogę kupić licencję tymczasową?
 Tak, możesz kupić licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
