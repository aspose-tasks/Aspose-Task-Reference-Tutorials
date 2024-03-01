---
title: Podziel datę zakończenia zadania w Aspose.Tasks
linktitle: Podziel datę zakończenia zadania w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak łatwo dzielić daty zakończenia zadań za pomocą Aspose.Tasks dla Java. Usprawnij zarządzanie projektami dzięki dokładnym harmonogramom.
type: docs
weight: 28
url: /pl/java/task-properties/split-task-finish-date/
---
## Wstęp
zarządzaniu projektami zrozumienie harmonogramu zadań ma kluczowe znaczenie dla pomyślnej realizacji projektu. Aspose.Tasks dla Java zapewnia zaawansowane funkcje umożliwiające efektywne manipulowanie zadaniami projektowymi. W tym samouczku zajmiemy się dzieleniem dat zakończenia zadań za pomocą Aspose.Tasks, pomagając Ci efektywnie zarządzać harmonogramem projektu.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Tasks dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/java/).
- Skonfigurowano środowisko programistyczne Java.
## Importuj pakiety
Zacznij od dołączenia niezbędnych pakietów do projektu Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Znajdź podzielone zadanie
Znajdź zadanie, które chcesz podzielić w ramach projektu:
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Przeczytaj projekt
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## Krok 2: Znajdź kalendarz projektu
Pobierz kalendarz projektu, aby uzyskać dokładne obliczenia dat:
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## Krok 3: Oblicz datę zakończenia zadania o różnym czasie trwania
Teraz oblicz datę zakończenia zadania dla różnych czasów trwania:
## Krok 3.1: Czas trwania 8 godzin
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
Powtórz powyższy kod dla różnych czasów trwania, odpowiednio dostosowując godziny.
## Wniosek
Opanowanie sztuki manipulowania terminami zakończenia zadań jest kluczowe dla skutecznego zarządzania projektami. Aspose.Tasks for Java upraszcza ten proces, umożliwiając bezproblemowe usprawnienie harmonogramu projektu.
## Często zadawane pytania
### P1: Jak mogę pobrać Aspose.Tasks dla Java?
 A1: Możesz go pobrać[Tutaj](https://releases.aspose.com/tasks/java/).
### P2: Gdzie mogę znaleźć dokumentację dla Aspose.Tasks?
 Odpowiedź 2: Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/tasks/java/).
### P3: Jak uzyskać tymczasową licencję na Aspose.Tasks?
 A3: Uzyskaj tymczasową licencję[Tutaj](https://purchase.aspose.com/temporary-license/).
### P4: Gdzie mogę szukać wsparcia dla Aspose.Tasks?
 Odpowiedź 4: Odwiedź forum pomocy technicznej[Tutaj](https://forum.aspose.com/c/tasks/15).
### P5: Czy mogę kupić Aspose.Tasks?
 A5: Tak, możesz go kupić[Tutaj](https://purchase.aspose.com/buy).