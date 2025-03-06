---
title: Pobierz wyjątki kalendarza za pomocą Aspose.Tasks
linktitle: Pobierz wyjątki kalendarza za pomocą Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak pobrać wyjątki kalendarza z MS Project przy użyciu Aspose.Tasks dla Java. Samouczek krok po kroku dotyczący bezproblemowej integracji.
weight: 13
url: /pl/java/calendar-exceptions/retrieve/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz wyjątki kalendarza za pomocą Aspose.Tasks

## Wstęp
W tym samouczku przyjrzymy się, jak pobrać wyjątki kalendarza z MS Project przy użyciu biblioteki Aspose.Tasks dla Java. Aspose.Tasks to potężne narzędzie, które pozwala programistom programowo manipulować plikami Microsoft Project. Poprowadzimy Cię przez proces krok po kroku, dzieląc każdy przykład na wiele kroków, aby ułatwić zrozumienie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Tasks dla Java: Pobierz i zainstaluj Aspose.Tasks dla Java z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Zintegrowane środowisko programistyczne (IDE): Możesz użyć dowolnego wybranego środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do pracy z Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Krok 1: Skonfiguruj swój katalog danych
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
```
 Pamiętaj o wymianie`"Your Data Directory"` ze ścieżką do katalogu zawierającego plik MS Project.
## Krok 2: Załaduj plik projektu MS
```java
Project project = new Project(dataDir + "project.mpp");
```
 Ta linia inicjuje nową`Project` obiekt, ładując plik MS Project określony ścieżką.
## Krok 3: Pobierz wyjątki kalendarza
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
W tym miejscu iterujemy po każdym kalendarzu w projekcie, a następnie po każdym wyjątku kalendarza w tym kalendarzu. Drukujemy datę rozpoczęcia i zakończenia każdego wyjątku.

## Wniosek
W tym samouczku nauczyliśmy się pobierać wyjątki kalendarza z MS Project za pomocą Aspose.Tasks dla Java. Wykonując te proste kroki, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami Java.
## Często Zadawane Pytania
### Czy Aspose.Tasks może obsługiwać różne wersje plików MS Project?
Tak, Aspose.Tasks obsługuje różne wersje plików MS Project, w tym formaty MPP, MPT i XML.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Tasks dla Java?
 Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/java/).
### Jak mogę uzyskać wsparcie dla Aspose.Tasks?
 Możesz uzyskać wsparcie na forum społeczności[Tutaj](https://forum.aspose.com/c/tasks/15).
### Czy istnieje opcja tymczasowych licencji dla Aspose.Tasks?
 Tak, możesz uzyskać tymczasowe licencje od[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
