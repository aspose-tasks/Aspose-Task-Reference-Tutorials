---
date: 2025-12-23
description: Dowiedz się, jak aktualizować pliki MS Project i przeszeregować niewykonane
  zadania przy użyciu Aspose.Tasks dla Javy. Zobacz także, jak zapisać plik XML MS
  Project.
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Zaktualizuj MS Project i przesuń pracę za pomocą Aspose.Tasks
url: /pl/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aktualizacja MS Project i przestawienie pracy przy użyciu Aspose.Tasks

## Wprowadzenie
Microsoft Project jest powszechnie używanym narzędziem do zarządzania projektami, które pomaga zespołom planować, śledzić i dostarczać pracę na czas. Gdy harmonogramy się zmieniają, często trzeba **update MS Project** programowo — oznaczyć pracę jako ukończoną, przenieść pozostałe zadania i utrzymać dokładną bazę projektu. Aspose.Tasks for Java zapewnia czyste, typowo‑bezpieczne API, które umożliwia to bez otwierania interfejsu graficznego. W tym samouczku zobaczysz, jak zaktualizować projekt, oznaczyć pracę jako zakończoną do określonej daty, a następnie **how to reschedule MS Project** pracę, która nadal jest w toku.

## Szybkie odpowiedzi
- **Co oznacza „update MS Project”?** Oznacza to, że zadania są oznaczane jako ukończone do podanej daty i zmiany są zapisywane z powrotem do pliku.  
- **Czy mogę automatycznie przestawić pozostałą pracę?** Tak — użyj `rescheduleUncompletedWorkToStartAfter`, aby przesunąć nieukończone zadania do przodu.  
- **W jakim formacie zapisywany jest plik?** Przykłady zapisują projekt jako XML (`SaveFileFormat.Xml`).  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jaka wersja Javy jest wymagana?** JDK 8 lub wyższa.

## Co oznacza „update MS Project” w kodzie?
Aktualizacja projektu oznacza programowe zmienianie dat zadań, ich trwania lub procentu ukończenia oraz zachowanie tych zmian. Aspose.Tasks udostępnia metody takie jak `updateProjectWorkAsComplete`, które stosują zmiany na podstawie podanej referencyjnej `Date`.

## Dlaczego używać Aspose.Tasks for Java do aktualizacji MS Project?
- **Brak zależności od interfejsu UI** – automatyzuj masowe zmiany w wielu plikach.  
- **Wysoka wierność** – biblioteka zachowuje wszystkie natywne dane Project (zasoby, kalendarze, pola niestandardowe).  
- **Wieloplatformowość** – uruchamiaj ten sam kod na Windows, Linux lub macOS.  
- **Zapisz MS Project XML** – możesz wyeksportować zaktualizowany projekt do szeroko wspieranego formatu XML dla narzędzi downstream.

## Wymagania wstępne
1. Zainstalowany Java Development Kit (JDK).  
2. Biblioteka Aspose.Tasks for Java – pobierz ją z [here](https://releases.aspose.com/tasks/java/).  
3. Podstawowa znajomość składni Javy i koncepcji programowania obiektowego.

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks oraz narzędzia Java:

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Krok 1: Konfiguracja projektu
Utwórz nową instancję `Project`, zdefiniuj kilka przykładowych zadań, ustaw ich trwania i ustanów zależności. Następnie zapisz początkowy stan, aby móc zobaczyć efekt przed‑ i po.

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Krok 2: Aktualizacja pracy w projekcie
Oznacz pracę jako ukończoną do określonej daty odcięcia. To jest sedno **update MS Project** — API automatycznie dostosuje postęp zadań i daty.

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Krok 3: Przestawienie nieukończonej pracy
Po oznaczeniu ukończonej pracy często trzeba przesunąć pozostałe zadania do przodu. Poniższe wywołanie przenosi wszelką nieukończoną pracę, aby rozpoczęła się po tej samej dacie odcięcia, skutecznie **how to reschedule MS Project**.

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Zadania nie wyświetlają zaktualizowanych dat | Projekt został zapisany w innym formacie (np. `.mpp`) | Użyj `SaveFileFormat.Xml`, aby zachować integralność struktury XML. |
| `updateProjectWorkAsComplete` wydaje się nie działać | Data referencyjna jest wcześniejsza niż początek projektu | Upewnij się, że data w `Calendar` znajduje się w ramach harmonogramu projektu. |
| Przestawione zadania nakładają się | Nie zastosowano kalendarza ani wyrównywania zasobów | Zastosuj kalendarz `Project` lub ręcznie użyj `Task.setStart` po przestawieniu. |

## Najczęściej zadawane pytania (rozszerzone)

**Q: Czy Aspose.Tasks for Java radzi sobie ze złożonymi strukturami projektów?**  
A: Tak, Aspose.Tasks for Java udostępnia solidne API do efektywnego zarządzania zadaniami, zależnościami, zasobami i innymi elementami projektu.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz uzyskać darmową wersję próbną z [here](https://releases.aspose.com/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub zapytań.

**Q: Czy mogę zakupić tymczasową licencję na Aspose.Tasks for Java?**  
A: Tak, tymczasowe licencje są dostępne do zakupu [here](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks for Java?**  
A: Dokumentację znajdziesz [here](https://reference.aspose.com/tasks/java/), zawierającą kompleksowe przewodniki i odniesienia do API.

## Zakończenie
W tym samouczku przeprowadziliśmy pełny proces **updating MS Project** plików, oznaczania pracy jako ukończonej, a następnie **how to reschedule MS Project** zadań, które pozostają nieukończone. Zapisując projekt jako XML, zachowujesz kompatybilność z innymi narzędziami i utrzymujesz przejrzysty ślad zmian. Użyj tych wzorców do automatyzacji korekt harmonogramów w dużych portfelach, integracji z pipeline'ami CI lub tworzenia własnych pulpitów raportowych.

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}