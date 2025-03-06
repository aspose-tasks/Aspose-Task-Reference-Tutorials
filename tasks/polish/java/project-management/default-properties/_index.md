---
title: Efektywnie zarządzaj właściwościami projektu MS w Aspose.Tasks
linktitle: Zarządzaj domyślnymi właściwościami projektu w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zarządzać domyślnymi właściwościami MS Project za pomocą Aspose.Tasks dla Java. Usprawnij przepływ pracy w zarządzaniu projektami bez wysiłku.
weight: 11
url: /pl/java/project-management/default-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Efektywnie zarządzaj właściwościami projektu MS w Aspose.Tasks

## Wstęp
Czy chcesz usprawnić proces zarządzania projektami dzięki Aspose.Tasks dla Java? Zarządzanie domyślnymi właściwościami w plikach Microsoft Project może znacznie zwiększyć wydajność. W tym samouczku przejdziemy przez instrukcje krok po kroku dotyczące zarządzania domyślnymi właściwościami MS Project za pomocą Aspose.Tasks.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
### 1. Zestaw programistyczny Java (JDK)
   - Upewnij się, że JDK jest zainstalowany w twoim systemie.
   -  Można go pobrać z[Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks dla biblioteki Java
   - Pobierz i dołącz bibliotekę Aspose.Tasks for Java do swojego projektu.
   -  Można go pobrać z[strona internetowa](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do pliku Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Podzielmy proces na łatwe do wykonania etapy:
## Krok 1: Załaduj plik projektu
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Krok 2: Wyświetl właściwości domyślne
```java
// Wyświetl właściwości domyślne
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Krok 3: Ustaw właściwości domyślne
```java
// Ustaw domyślne właściwości
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Krok 4: Zapisz projekt w formacie XML
```java
// Zapisz projekt w formacie XML
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Krok 5: Wyświetl wynik
```java
// Wyświetl wynik konwersji.
System.out.println("Process completed Successfully");
```
Wykonując poniższe kroki, możesz efektywnie zarządzać domyślnymi właściwościami MS Project przy użyciu Aspose.Tasks dla Java.
## Wniosek
W tym samouczku nauczyliśmy się, jak zarządzać domyślnymi właściwościami MS Project za pomocą Aspose.Tasks dla Java. Korzystając z tych technik, możesz zoptymalizować przepływ pracy w zarządzaniu projektami, zwiększając produktywność i organizację.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks z innymi językami programowania?
O1: Tak, Aspose.Tasks obsługuje różne języki programowania, takie jak .NET, Python i Java.
### P2: Czy Aspose.Tasks nadaje się zarówno do użytku osobistego, jak i korporacyjnego?
A2: Absolutnie! Niezależnie od tego, czy zarządzasz małymi projektami osobistymi, czy inicjatywami korporacyjnymi na dużą skalę, Aspose.Tasks zaspokaja potrzeby wszystkich.
### P3: Czy Aspose.Tasks oferuje obsługę klienta?
Odpowiedź 3: Tak, pomoc i wsparcie społeczności można znaleźć na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P4: Czy mogę wypróbować Aspose.Tasks przed zakupem?
 A4: Oczywiście! Możesz skorzystać z bezpłatnego okresu próbnego w witrynie[strona internetowa](https://releases.aspose.com/).
### P5: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?
 Odpowiedź 5: Możesz uzyskać tymczasową licencję od[strona zakupu](https://purchase.aspose.com/temporary-license/) do celów testowania i oceny.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
