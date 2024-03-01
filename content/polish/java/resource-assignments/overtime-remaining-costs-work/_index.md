---
title: Monitoruj nadgodziny, pozostałe koszty i pracę w Aspose.Tasks
linktitle: Monitoruj nadgodziny, pozostałe koszty i pracę w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak monitorować nadgodziny, pozostałe koszty i pracować w projektach Java za pomocą Aspose.Tasks. Proste kroki do skutecznego zarządzania projektami.
type: docs
weight: 18
url: /pl/java/resource-assignments/overtime-remaining-costs-work/
---
## Wstęp
W tym samouczku nauczymy się używać Aspose.Tasks dla Java do monitorowania nadgodzin, pozostałych kosztów i pracy w projekcie. Może to być nieocenione dla kierowników projektów i kierowników zespołów, ponieważ pozwalają mieć pewność, że projekty przebiegają zgodnie z planem i mieszczą się w budżecie.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK): Aspose.Tasks for Java wymaga Java SE 6 lub nowszego.
2.  Aspose.Tasks dla biblioteki Java: Pobierz i zainstaluj bibliotekę z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Zintegrowane środowisko programistyczne (IDE): dowolne środowisko Java IDE, takie jak Eclipse, IntelliJ IDEA lub NetBeans.

## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów do pliku Java:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## Krok 1: Skonfiguruj katalog danych
Zdefiniuj katalog, w którym znajduje się plik projektu:
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` ze ścieżką do pliku projektu.
## Krok 2: Załaduj projekt
 Utwórz instancję a`Project` obiekt i załaduj plik projektu:
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
 Zastępować`"ResourceAssignmentOvertimes.mpp"` z nazwą pliku projektu.
## Krok 3: Iteruj po przypisaniach zasobów
Przejdź w pętli każde przypisanie zasobów w projekcie:
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## Krok 4: Wydrukuj koszty pracy w nadgodzinach i pracę
Pobierz i wydrukuj koszty pracy w nadgodzinach i pracę dla każdego przydziału zasobów:
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## Krok 5: Wydrukuj pozostałe koszty i pracę
Pobierz i wydrukuj pozostałe koszty i pracę dla każdego przydziału zasobów:
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## Krok 6: Wydrukuj pozostałe koszty pracy w nadgodzinach i pracę
Pobierz i wydrukuj pozostałe koszty pracy w nadgodzinach i pracę dla każdego przydziału zasobów:
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## Wniosek
Monitorowanie nadgodzin, pozostałych kosztów i pracy w projekcie ma kluczowe znaczenie dla skutecznego zarządzania projektem. Dzięki Aspose.Tasks dla Java możesz łatwo uzyskać dostęp do tych informacji i je śledzić, zapewniając, że Twoje projekty będą realizowane zgodnie z harmonogramem i budżetem.
## Często zadawane pytania
### Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?
Tak, Aspose.Tasks for Java jest kompatybilny z innymi bibliotekami i frameworkami Java.
### Czy Aspose.Tasks obsługuje różne formaty plików projektów?
Tak, Aspose.Tasks obsługuje różne formaty plików projektów, w tym MPP, XML i inne.
### Czy dostępna jest wersja próbna?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć pomoc, jeśli napotkam problemy?
 Możesz odwiedzić forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15) dla wsparcia.
### Jak mogę kupić licencję na Aspose.Tasks?
 Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy).