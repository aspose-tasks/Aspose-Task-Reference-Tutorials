---
date: 2026-03-03
description: Dowiedz się, jak ponumerować ponownie WBS w Aspose.Tasks dla Javy, zarządzać
  podziałem pracy i efektywnie dostosowywać kody WBS, korzystając z przykładów krok
  po kroku.
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ponumerować ponownie WBS w Aspose.Tasks dla Javy
url: /pl/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ponumerować ponownie WBS w Aspose.Tasks dla Javy

## Wprowadzenie
Jeśli potrzebujesz **jak ponumerować ponownie WBS** w pliku Microsoft Project przy użyciu Aspose.Tasks dla Javy, jesteś we właściwym miejscu. Ten samouczek przeprowadzi Cię przez odczyt istniejących kodów WBS, ich dostosowywanie, a następnie ponowne numerowanie hierarchii, aby Twój projekt pozostał uporządkowany. Niezależnie od tego, czy porządkujesz starszy harmonogram, czy tworzysz nowy od podstaw, opanowanie tych kroków pomoże Ci **zarządzać strukturą podziału pracy** z pewnością.

## Szybkie odpowiedzi
- **Co robi ponowne numerowanie WBS?** Przelicza hierarchiczne numerowanie zadań, aby odzwierciedlić wszelkie zmiany strukturalne.  
- **Która klasa wykonuje ponowne numerowanie?** `Project.renumberWBSCode`.  
- **Czy potrzebuję licencji, aby uruchomić kod?** Wymagana jest ważna licencja Aspose.Tasks do użytku produkcyjnego.  
- **Czy mogę dostosować format WBS?** Tak — użyj `Task.set(Tsk.WBS, "...")`, aby przypisać dowolny ciąg znaków.  
- **Jakie są główne wymagania wstępne?** Java JDK, biblioteka Aspose.Tasks for Java oraz prawidłowy plik projektu (.mpp).

## Czym jest struktura podziału pracy (WBS)?
Struktura podziału pracy (WBS) jest hierarchiczną reprezentacją rezultatów i zadań projektu. Każde zadanie otrzymuje kod (np. 1.2.3), który odzwierciedla jego pozycję w hierarchii. Ponowne numerowanie staje się niezbędne, gdy zadania są dodawane, usuwane lub zmieniane kolejnością, zapewniając, że kody pozostają logiczne i łatwe do odczytania.

## Dlaczego zarządzać podziałem pracy i dostosowywać kody WBS?
- **Przejrzystość:** Czytelne kody WBS ułatwiają interesariuszom odnalezienie zadań.  
- **Raportowanie:** Wiele narzędzi raportujących opiera się na spójnym numerowaniu.  
- **Elastyczność:** Niestandardowe kody pozwalają dopasować strukturę projektu do wewnętrznych standardów.  

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące:

- Java Development Kit (JDK) zainstalowany na Twoim komputerze.  
- Biblioteka Aspose.Tasks for Java dodana do Twojego projektu. Możesz ją pobrać [tutaj](https://releases.aspose.com/tasks/java/).  

## Importowanie pakietów
Upewnij się, że importujesz niezbędne pakiety, aby rozpocząć projekt:

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## Odczyt kodów WBS
Najpierw odczytamy istniejące kody WBS, abyś mógł zobaczyć, z czym pracujesz.

### Krok 1: Załaduj projekt
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### Krok 2: Zbierz zadania
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### Krok 3: Analizuj i dostosuj
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

Powyższy fragment wypisuje bieżący WBS i poziom każdego zadania, a następnie demonstruje **dostosowanie kodów WBS** poprzez przypisanie nowego ciągu znaków.

## Ponowne numerowanie kodów WBS zadań
Teraz faktycznie ponumerujemy ponownie hierarchię WBS.

### Krok 1: Załaduj projekt (przykład ponownego numerowania)
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### Krok 2: Wybierz wszystkie zadania
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### Krok 3: Wyświetl początkowe kody WBS
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### Krok 4: Ponumeruj ponownie kody WBS
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### Krok 5: Wyświetl zaktualizowane kody WBS
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

Postępując zgodnie z tymi krokami, skutecznie **ponumerujesz ponownie WBS** dla dowolnego zestawu zadań w pliku projektu.

## Typowe problemy i rozwiązania
- **WBS nie zmienia się po wywołaniu `set`:** Upewnij się, że pracujesz z właściwą instancją zadania i że projekt jest zapisany po modyfikacjach.  
- **`renumberWBSCode` zgłasza wyjątek:** Sprawdź, czy lista identyfikatorów odpowiada liczbie zadań najwyższego poziomu; w przeciwnym razie metoda nie może prawidłowo przypisać nowych numerów.  
- **Brakujące wartości WBS:** Niektóre zadania mogą mieć `null` WBS, jeśli zostały zaimportowane z pliku, który nie definiował tego pola. Użyj wartości domyślnej przed wypisaniem.  

## Najczęściej zadawane pytania

**Q: Gdzie mogę znaleźć dokumentację Aspose.Tasks for Java?**  
A: Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/tasks/java/).

**Q: Jak mogę pobrać Aspose.Tasks for Java?**  
A: Możesz go pobrać [tutaj](https://releases.aspose.com/tasks/java/).

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz uzyskać darmową wersję próbną [tutaj](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy.

**Q: Czy mogę uzyskać tymczasową licencję na Aspose.Tasks for Java?**  
A: Tak, uzyskaj tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Czy mogę zmienić nazwę formatu WBS po ponownym numerowaniu?**  
A: Oczywiście. Po wywołaniu `renumberWBSCode` możesz przeiterować zadania i zastosować `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))`, aby dopasować je do swoich konwencji nazewnictwa.

**Q: Czy ponowne numerowanie wpływa na zależności zadań?**  
A: Nie. Metoda aktualizuje jedynie ciąg WBS; połączenia i ograniczenia zadań pozostają niezmienione.

---

**Ostatnia aktualizacja:** 2026-03-03  
**Testowano z:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}