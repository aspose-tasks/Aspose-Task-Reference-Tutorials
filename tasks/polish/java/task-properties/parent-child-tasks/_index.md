---
date: 2026-02-23
description: Dowiedz się, jak ustawić datę rozpoczęcia projektu, określić czas trwania
  zadania i zapisać projekt jako plik MPP przy użyciu Aspose.Tasks dla Javy. Efektywnie
  zarządzaj zadaniami nadrzędnymi i podrzędnymi.
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Ustaw datę rozpoczęcia projektu i zarządzaj zadaniami nadrzędnymi oraz podrzędnymi
  w Aspose.Tasks
url: /pl/java/task-properties/parent-child-tasks/
weight: 24
---

dź notatki wydania pod kątem ewentualnych zmian łamiących kompatybilność."

Next after Q&A, there is a horizontal rule "---". Keep.

Then "**Last Updated:** 2026-02-23" translate "Ostatnia aktualizacja:".

**Tested With:** Aspose.Tasks for Java 24.11 -> "Testowano z:".

**Author:** Aspose -> "Autor:".

Then closing shortcodes.

Also there is a backtop button shortcode after.

We must ensure we keep all shortcodes exactly.

Now produce final content.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw datę rozpoczęcia projektu i zarządzaj zadaniami nadrzędnymi i podrzędnymi w Aspose.Tasks

## Wprowadzenie
Efektywna organizacja zadań jest podstawą udanego zarządzania projektami, a **ustawienie daty rozpoczęcia projektu** prawidłowo jest pierwszym krokiem w kierunku dobrze ustrukturyzowanego harmonogramu. W tym samouczku zobaczysz, jak **ustawić datę rozpoczęcia projektu**, skonfigurować czasy trwania zadań oraz zarządzać relacjami nadrzędny‑podrzędny przy użyciu Aspose.Tasks for Java. Po zakończeniu będziesz gotowy, aby **zapisać projekt jako MPP**, zaktualizować procenty ukończenia zadań i dostosować właściwości zadań do dowolnego scenariusza rzeczywistego.

## Szybkie odpowiedzi
- **Jak ustawić datę rozpoczęcia projektu?** Użyj `proj.set(Prj.START_DATE, startDate);` po zainicjowaniu obiektu `Project`.  
- **Czy mogę dodać zadania podrzędne pod zadaniem nadrzędnym?** Tak – wywołaj `parentTask.getChildren().add("Child Task")`.  
- **W jakim formacie Aspose.Tasks zapisuje plik?** Użyj `SaveFileFormat.Mpp`, aby **zapisać projekt jako MPP**.  
- **Jak zaktualizować postęp zadania?** Ustaw `Tsk.PERCENT_COMPLETE` na obiekcie zadania.  
- **Gdzie mogę uzyskać tymczasową licencję?** Odwiedź stronę tymczasowej licencji podaną w FAQ.

## Wymagania wstępne
Zanim zagłębisz się w samouczek, upewnij się, że spełniasz następujące wymagania:
- Podstawowa znajomość programowania w języku Java.  
- Zainstalowana biblioteka Aspose.Tasks for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).  
- Zintegrowane środowisko programistyczne Java (IDE) skonfigurowane w systemie.

## Importowanie pakietów
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Pakiety te ułatwiają płynną integrację z funkcjami Aspose.Tasks for Java.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Krok 1: Ustaw datę rozpoczęcia projektu
Rozpocznij od ustawienia daty rozpoczęcia projektu oraz innych istotnych parametrów.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Krok 2: Dodaj zadanie nadrzędne (Task 1)
Utwórz zadanie nadrzędne o nazwie "Task 1" i skonfiguruj jego właściwości, w tym **ustawienie czasu trwania zadania**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Krok 3: Dodaj zadanie nadrzędne (Task 2) z zadaniami podrzędnymi
Teraz dodaj kolejne zadanie nadrzędne o nazwie "Task 2" i dołącz zadania podrzędne (Task 3 i Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Krok 4: Skonfiguruj zadania podrzędne
Określ daty rozpoczęcia, czasy trwania i ograniczenia dla Task 3 i Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Krok 5: Zaktualizuj procent ukończenia zadania
Dostosuj procent ukończenia dla Task 3 i Task 4 – w ten sposób **zaktualizujesz postęp zadania**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Krok 6: Zapisz projekt
Na koniec, **zapisz projekt jako MPP** z zastosowanymi zmianami.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

Ten przewodnik krok po kroku pokazuje, jak skutecznie zarządzać zadaniami nadrzędnymi i podrzędnymi przy użyciu Aspose.Tasks for Java. Eksperymentuj z różnymi konfiguracjami, aby dopasować je do wymagań swojego projektu.

## Dlaczego dostosowywać właściwości zadań?
Dostosowywanie właściwości zadań, takich jak daty rozpoczęcia, czasy trwania, ograniczenia i procenty ukończenia, daje Ci szczegółową kontrolę nad zachowaniem harmonogramu. Niezależnie od tego, czy musisz dopasować zadania do dostępności zasobów, czy egzekwować zasady biznesowe, Aspose.Tasks pozwala **programowo dostosowywać właściwości zadań**.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Start date not applied** | Upewnij się, że wywołujesz `proj.set(Prj.START_DATE, …)` **po** utworzeniu obiektu `Project` i przed dodaniem zadań. |
| **Child tasks inherit wrong constraints** | Ustaw explicite `ConstraintType` i `ConstraintDate` każdego zadania podrzędnego, jak pokazano w Kroku 4. |
| **Saved file cannot be opened in MS Project** | Sprawdź, czy używasz najnowszej wersji Aspose.Tasks i zapisujesz przy użyciu `SaveFileFormat.Mpp`. |
| **Percentage not reflecting in UI** | Po ustawieniu `Tsk.PERCENT_COMPLETE` wywołaj `proj.calculateTaskSchedule()`, jeśli potrzebne są przeliczone daty. |

## FAQ
### Czy Aspose.Tasks for Java jest kompatybilny z różnymi formatami plików projektów?
Tak, Aspose.Tasks for Java obsługuje różne formaty plików projektów, w tym MPP i XML.

### Czy mogę dostosować właściwości zadań poza zakresem tego samouczka?
Oczywiście! Aspose.Tasks for Java oferuje rozbudowane możliwości dostosowywania właściwości zadań.

### Czy istnieje forum społecznościowe Aspose.Tasks, gdzie mogę uzyskać wsparcie?
Tak, możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania wsparcia społeczności.

### Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?
Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę znaleźć pełną dokumentację Aspose.Tasks for Java?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/tasks/java/).

**Dodatkowe pytania i odpowiedzi**

**P: Jak programowo uzyskać tymczasową licencję?**  
O: Załaduj plik tymczasowej licencji używając `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**P: Czy mogę zmienić domyślną jednostkę czasu trwania zadania?**  
O: Tak – zmodyfikuj argument `TimeUnitType` w wywołaniu `proj.getDuration(value, TimeUnitType.YourChoice)`.

**P: Jaka wersja Aspose.Tasks jest wymagana do użycia `SaveFileFormat.Mpp`?**  
O: Wszystkie najnowsze wersje (2022‑2026) obsługują zapisywanie jako MPP; sprawdź notatki wydania pod kątem ewentualnych zmian łamiących kompatybilność.

---

**Ostatnia aktualizacja:** 2026-02-23  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}