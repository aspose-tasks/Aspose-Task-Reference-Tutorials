---
title: Zarządzaj czasem trwania zadań w Aspose.Tasks
linktitle: Zarządzaj czasem trwania zadań w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Poznaj Aspose.Tasks dla Java i naucz się bez wysiłku zarządzać czasem trwania zadań. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby skutecznie planować i realizować projekty.
type: docs
weight: 20
url: /pl/java/task-properties/manage-durations/
---
## Wstęp
Aspose.Tasks dla Java zapewnia solidne rozwiązanie do efektywnego zarządzania zadaniami projektowymi i czasem ich trwania. W tym samouczku omówimy, jak zarządzać czasem trwania zadań za pomocą Aspose.Tasks, prowadząc Cię przez każdy krok. Niezależnie od tego, czy jesteś doświadczonym programistą, czy początkującym, ten przewodnik pomoże Ci zrozumieć podstawy pracy z czasem trwania zadań w Twoich projektach.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Zestaw Java Development Kit (JDK): Upewnij się, że na komputerze jest zainstalowana Java. Możesz go pobrać[Tutaj](https://www.oracle.com/java/technologies/javase-downloads.html).
- Biblioteka Aspose.Tasks: Pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety do pracy z Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## Krok 1: Skonfiguruj swój projekt
```java
// Utwórz nowy projekt
Project project = new Project();
```
## Krok 2: Dodaj nowe zadanie
```java
// Dodaj nowe zadanie do projektu
Task task = project.getRootTask().getChildren().add("Task");
```
## Krok 3: Uzyskaj i przekonwertuj czas trwania zadania
```java
// Uzyskaj czas trwania zadania w dniach (domyślna jednostka czasu)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Konwertuj czas trwania na jednostkę czasu w godzinach
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## Krok 4: Zaktualizuj czas trwania zadania do 1 tygodnia
```java
// Zwiększ czas trwania zadania do 1 tygodnia
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## Krok 5: Skróć czas trwania zadania
```java
// Zmniejsz czas trwania zadania
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
Wykonując poniższe kroki, udało Ci się pomyślnie zarządzać czasem trwania zadań w projekcie Aspose.Tasks for Java.
## Wniosek
W tym samouczku omówiliśmy podstawy zarządzania czasem trwania zadań przy użyciu Aspose.Tasks dla Java. Teraz możesz śmiało zastosować te techniki w swoich projektach, aby efektywnie zarządzać czasem trwania zadań.
## Często zadawane pytania
### Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Java?
Aspose.Tasks jest kompatybilny z Java 6 i nowszymi wersjami.
### Czy mogę używać Aspose.Tasks do projektów komercyjnych?
 Tak, możesz używać Aspose.Tasks zarówno do projektów osobistych, jak i komercyjnych. Odwiedzać[Tutaj](https://purchase.aspose.com/buy) w celu uzyskania szczegółów licencji.
### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
 Odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.
### Jak mogę uzyskać tymczasową licencję do celów testowych?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) do testowania i oceny.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/) aby poznać Aspose.Tasks przed dokonaniem zakupu.