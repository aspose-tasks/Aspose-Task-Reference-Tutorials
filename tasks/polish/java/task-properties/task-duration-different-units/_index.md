---
title: Czas trwania zadania w różnych jednostkach z Aspose.Tasks
linktitle: Czas trwania zadania w różnych jednostkach z Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Poznaj zarządzanie czasem trwania zadań w projektach Java za pomocą Aspose.Tasks. Dokładnie obliczaj i konwertuj czasy trwania w minutach, dniach, godzinach, tygodniach i miesiącach.
weight: 32
url: /pl/java/task-properties/task-duration-different-units/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Czas trwania zadania w różnych jednostkach z Aspose.Tasks

## Wstęp
W dziedzinie zarządzania projektami zrozumienie czasu trwania zadania i zarządzanie nim jest aspektem krytycznym. Aspose.Tasks dla Java zapewnia potężny zestaw narzędzi do efektywnej obsługi tego problemu. W tym samouczku poprowadzimy Cię przez pobieranie czasów trwania zadań w różnych jednostkach przy użyciu Aspose.Tasks.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
- Zainstalowany zestaw Java Development Kit (JDK).
-  Aspose.Tasks dla biblioteki Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/java/)
- Podstawowa znajomość programowania w języku Java
## Importuj pakiety
swoim projekcie Java dołącz bibliotekę Aspose.Tasks. Dodaj następującą instrukcję importu na początku kodu:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Krok 1: Skonfiguruj swój projekt
Rozpocznij od utworzenia nowego projektu Java w preferowanym zintegrowanym środowisku programistycznym (IDE). Pamiętaj o uwzględnieniu biblioteki Aspose.Tasks w zależnościach projektu.
## Krok 2: Przeczytaj szablon projektu
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Przeczytaj plik szablonu MS Project
String fileName = dataDir + "project.xml";
// Przeczytaj plik wejściowy jako Project
Project project = new Project(fileName);
```
 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do plików projektu.
## Krok 3: Pobierz zadanie
```java
// Uzyskaj zadanie obliczenia czasu jego trwania w różnych formatach
Task task = project.getRootTask().getChildren().getById(1);
```
 Tutaj pozyskujemy zadanie z projektu. Regulować`getById(1)` na podstawie identyfikatora zadania projektu.
## Krok 4: Czas trwania w minutach
```java
// Uzyskaj czas trwania w minutach
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```
W tym kroku obliczany jest czas trwania zadania w minutach.
## Krok 5: Czas trwania w dniach
```java
// Uzyskaj czas trwania w dniach
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```
W tym kroku obliczany jest czas trwania zadania w dniach.
## Krok 6: Czas trwania w godzinach
```java
// Uzyskaj czas trwania w godzinach
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```
tym kroku obliczany jest czas trwania zadania w godzinach.
## Krok 7: Czas trwania w tygodniach
```java
// Uzyskaj czas trwania w tygodniach
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```
W tym kroku obliczany jest czas trwania zadania w tygodniach.
## Krok 8: Czas trwania w miesiącach
```java
// Uzyskaj czas trwania w miesiącach
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```
W tym kroku obliczany jest czas trwania zadania w miesiącach.
## Wniosek
Zarządzanie czasem trwania zadań jest proste dzięki Aspose.Tasks dla Java. Ten samouczek przeprowadził Cię krok po kroku przez proces, zapewniając przejrzystość różnych jednostek czasu.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.Tasks dla Java z dowolnym IDE Java?
Tak, Aspose.Tasks for Java jest kompatybilny z dowolnym zintegrowanym środowiskiem programistycznym Java (IDE).
### P: Jak mogę uzyskać identyfikator zadania w pliku Microsoft Project?
Możesz sprawdzić plik projektu lub użyć interfejsu API Aspose.Tasks, aby programowo pobrać identyfikatory zadań.
### P: Czy Aspose.Tasks nadaje się do obsługi dużych projektów?
Absolutnie. Aspose.Tasks został zaprojektowany do wydajnej obsługi projektów o różnej wielkości.
### P: Gdzie mogę znaleźć dalszą dokumentację?
 Odwiedzić[dokumentacja](https://reference.aspose.com/tasks/java/)dla kompleksowych zasobów.
### P: Czy mogę wypróbować Aspose.Tasks dla Java przed zakupem?
 Tak, możesz poznać m.in[bezpłatna wersja próbna](https://releases.aspose.com/) aby ocenić jego możliwości.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
