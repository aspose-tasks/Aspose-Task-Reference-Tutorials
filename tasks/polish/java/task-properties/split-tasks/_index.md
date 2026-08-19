---
date: 2026-02-26
description: Dowiedz się, jak dzielić zadania przy użyciu Aspose.Tasks for Java –
  definitywny przewodnik, jak dzielić zadania, ustawiać kalendarz projektu i tworzyć
  przydział zasobów.
linktitle: Split Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak podzielić zadania w Aspose.Tasks
url: /pl/java/task-properties/split-tasks/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak podzielić zadania w Aspose.Tasks

## Wprowadzenie
Jeśli szukasz **sposobu podziału zadań** w projekcie opartym na Javie, trafiłeś we właściwe miejsce. Aspose.Tasks for Java zapewnia czysty, programistyczny sposób na podzielenie długotrwałego zadania na mniejsze, łatwiejsze do zarządzania części, co pomaga w wyrównywaniu zasobów, dokładnym raportowaniu i ściślejszych terminach projektu. W tym samouczku przeprowadzimy Cię przez cały proces — od ustawienia kalendarza projektu, przez utworzenie przydziału zasobu, aż po podzielenie zadania na wiele segmentów.

## Szybkie odpowiedzi
- **Czym jest podział zadań?** Podzielenie jednego zadania na kilka mniejszych przedziałów przy zachowaniu całkowitego czasu trwania.  
- **Dlaczego dzielić zadania w Javie?** Umożliwia precyzyjne przydzielanie zasobów i lepsze śledzenie postępu.  
- **Która biblioteka pomaga?** Aspose.Tasks for Java udostępnia wbudowane metody do podziału i fazowania w czasie.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja jest wymagana w środowisku produkcyjnym.  
- **Jaką wersję Javy obsługuje?** Biblioteka działa z Java 8 i nowszymi.

## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz spełnione następujące wymagania:
- Zainstalowany Java Development Kit (JDK) na Twoim komputerze.  
- Biblioteka Aspose.Tasks for Java pobrana i dodana do projektu. Możesz ją pobrać z [dokumentacji Aspose.Tasks for Java](https://reference.aspose.com/tasks/java/).

## Importowanie pakietów
Rozpocznij od zaimportowania niezbędnych pakietów do swojego projektu Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
```

## Krok 1: Utwórz nowy projekt
Zacznij od stworzenia nowego projektu przy użyciu biblioteki Aspose.Tasks:

```java
// Create a new project
Project splitTaskProject = new Project();
```

## Krok 2: Ustaw kalendarz projektu
Ustawienie **kalendarza projektu** definiuje dni robocze, święta oraz ogólny harmonogram Twojego planu. Ten krok jest niezbędny do dokładnych obliczeń fazowanych w czasie.

```java
// Get a standard calendar
Calendar calendar = splitTaskProject.get(Prj.CALENDAR);
// Set project's calendar settings
java.util.Calendar cal = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Krok 3: Dodaj zadanie główne
Każdy projekt potrzebuje kontenera głównego. Dodanie zadania głównego daje miejsce, do którego można podpiąć wszystkie kolejne zadania.

```java
// Root task
Task rootTask = splitTaskProject.getRootTask();
rootTask.set(Tsk.NAME, "Root");
```

## Krok 4: Dodaj nowe zadanie do podziału
Utwórz zadanie, które zamierzasz podzielić. Tutaj jako przykład ustawiamy czas trwania na trzy dni.

```java
// Add a new task
Task taskToSplit = rootTask.getChildren().add("Task1");
taskToSplit.set(Tsk.DURATION, splitTaskProject.getDuration(3));
```

## Krok 5: Utwórz przydział zasobu
**Przydział zasobu** łączy zasób (lub placeholder) z zadaniem. Jest to wymagane przed generowaniem danych fazowanych w czasie.

```java
// Create a new resource assignment
ResourceAssignment splitResourceAssignment = splitTaskProject.getResourceAssignments().add(taskToSplit, null);
```

## Krok 6: Wygeneruj dane fazowane w czasie
Dane fazowane w czasie przedstawiają, jak praca jest rozłożona na czas trwania zadania. Ich wygenerowanie przygotowuje zadanie do podziału.

```java
// Generate resource assignment timephased data
splitResourceAssignment.timephasedDataFromTaskDuration(calendar);
```

## Krok 7: Podziel zadanie
Teraz **dzielimy zadanie na części**. W tym przykładzie dzielimy trzydniowe zadanie na trzy jednodniowe segmenty.

```java
// Split the task into 3 parts
java.util.Calendar cal = java.util.Calendar.getInstance();
java.util.Calendar cal2 = java.util.Calendar.getInstance();
// ... (continue with the example)
```

## Dlaczego dzielić zadania?
Podział zadań daje bardziej szczegółową kontrolę nad:
- **Wyrównywaniem zasobów:** Przypisywanie różnych zasobów do każdego segmentu.  
- **Śledzeniem postępu:** Aktualizowanie statusu na poziomie poszczególnych segmentów.  
- **Raportowaniem:** Tworzenie bardziej szczegółowych wykresów Gantta i raportów.

## Typowe problemy i rozwiązania
- **Brak danych kalendarza:** Upewnij się, że wywołujesz `timephasedDataFromTaskDuration` przed podziałem.  
- **Segmenty o zerowym czasie trwania:** Sprawdź, czy każdy przedział podziału ma niezerowy czas trwania; w przeciwnym razie biblioteka go zignoruje.  
- **Wyjątki licencyjne:** Uruchamianie bez ważnej licencji może dodać znak wodny do eksportowanych plików.

## Najczęściej zadawane pytania
### Czy mogę podzielić zadania o różnych czasach trwania?
Tak, możesz dostosować czas trwania każdej części do wymagań swojego projektu.

### Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami Javy?
Aspose.Tasks for Java został zaprojektowany tak, aby działał płynnie z Java 8 i nowszymi, zapewniając szeroką kompatybilność.

### Czy mogę używać Aspose.Tasks for Java za darmo?
Aspose.Tasks for Java oferuje darmową wersję próbną, pozwalającą przetestować funkcje przed zakupem.

### Jak mogę uzyskać wsparcie dla Aspose.Tasks for Java?
Odwiedź [forum wsparcia Aspose.Tasks for Java](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc i połączyć się ze społecznością.

### Czy potrzebuję tymczasowej licencji dla Aspose.Tasks for Java?
Możesz uzyskać tymczasową licencję pod [tym linkiem](https://purchase.aspose.com/temporary-license/) w celu testów i oceny.

---

**Ostatnia aktualizacja:** 2026-02-26  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}