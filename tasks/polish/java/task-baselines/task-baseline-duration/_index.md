---
date: 2026-01-23
description: Dowiedz się, jak ustawić czas trwania baseline i utworzyć instancję projektu
  przy użyciu Aspose.Tasks dla Javy. Ten przewodnik krok po kroku pomaga efektywnie
  zarządzać baseline'ami zadań.
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Jak ustawić czas trwania linii bazowej w Aspose.Tasks dla Javy
url: /pl/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić czas trwania baseline w Aspose.Tasks dla Javy

## Wprowadzenie
Ustawienie baseline to podstawowy krok, który pozwala śledzić postęp projektu w stosunku do pierwotnego planu. W tym samouczku dowiesz się, **jak ustawić baseline** czasu trwania zadań w Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy oraz zobaczysz, dlaczego wczesne ustanowienie baseline może zaoszczędzić Ci czasu i problemów w przyszłości.

## Szybkie odpowiedzi
- **Co oznacza „set baseline”?** Rejestruje oryginalne daty rozpoczęcia, zakończenia i czas trwania zadania, aby móc porównać przyszłe zmiany.  
- **Która klasa Aspose.Tasks tworzy projekt?** Klasa `Project` – dowiesz się także, jak **create project instance** prawidłowo.  
- **Czy potrzebna jest licencja do uruchomienia kodu?** Darmowa licencja ewaluacyjna wystarczy do testów; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę pobrać interim baselines?** Tak, Aspose.Tasks umożliwia zapytania o interim baselines oraz ich stałe koszty.  
- **Jakiej wersji Javy potrzebuję?** Zalecana jest Java 8 lub nowsza.

## Co to jest baseline zadania i dlaczego je ustawiać?
Baseline zadania przechowuje zaplanowany harmonogram (datę rozpoczęcia, datę zakończenia i czas trwania) w określonym momencie. Ustawiając baseline, tworzysz punkt odniesienia, który ułatwia wykrywanie odchyleń w harmonogramie, przekroczeń kosztów oraz nadmiernego przydziału zasobów w miarę rozwoju projektu.

## Dlaczego warto używać Aspose.Tasks do zarządzania baseline?
- **Pełna kompatybilność z .mpp** – odczyt i zapis natywnych plików Microsoft Project bez potrzeby instalacji Office.  
- **Bogate API** – programowy dostęp do danych baseline, interim baselines oraz informacji czasowo‑fazowych.  
- **Cross‑platform** – działa na Windows, Linux i macOS z dowolnym standardowym JDK.

## Wymagania wstępne
1. **Środowisko programistyczne Java** – zainstalowany i skonfigurowany JDK 8+.  
2. **Aspose.Tasks for Java** – pobierz bibliotekę z [tutaj](https://releases.aspose.com/tasks/java/).  
3. **IDE lub narzędzie budujące** – Maven, Gradle lub dowolne IDE, którego używasz.

## Import pakietów
Najpierw zaimportuj niezbędne klasy do swojego projektu Java:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Krok 1: Utwórz instancję projektu
Utworzenie instancji projektu jest podstawą wszelkich dalszych operacji. Ten krok pokazuje, jak **create project instance** przy użyciu Aspose.Tasks:

```java
Project project = new Project();
```

## Krok 2: Utwórz baseline zadania
Dodaj nowe zadanie do korzenia projektu i ustaw jego baseline. To zapisuje pierwotny harmonogram zadania:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Krok 3: Wyświetl informacje o baseline zadania
Pobierz właśnie utworzony baseline i wydrukuj jego kluczowe właściwości. Dzięki temu możesz zweryfikować, czy baseline został ustawiony prawidłowo:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Krok 4: Sprawdź interim baseline i stały koszt
Jeśli pracujesz z interim baselines, możesz sprawdzić, czy bieżący baseline jest interim oraz jaki ma powiązany stały koszt:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Krok 5: Wydrukuj dane czasowo‑fazowe
Dane czasowo‑fazowe pokazują, jak baseline jest rozłożony w czasie. Przejdź pętlą po kolekcji, aby przejrzeć każdy wpis:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

Postępując zgodnie z tymi krokami, możesz **how to set baseline** duration dla dowolnego zadania i pobrać szczegółowe informacje o baseline przy użyciu Aspose.Tasks for Java.

## Typowe problemy i rozwiązania
- **Baseline nie pojawia się w MS Project:** Upewnij się, że wywołałeś `project.setBaseline(BaselineType.Baseline)` **po** dodaniu zadania.  
- **NullPointerException przy `getBaselines()`:** Sprawdź, czy zadanie zostało dodane do projektu przed ustawieniem baseline.  
- **Niezgodność jednostek czasu:** Użyj `TimeUnitType`, aby prawidłowo sformatować czas trwania, szczególnie przy niestandardowych kalendarzach.

## FAQ
### Co to jest baseline zadania w MS Project?
Baseline zadania w MS Project to migawka początkowego planowanego harmonogramu, obejmująca datę rozpoczęcia, datę zakończenia i czas trwania.

### Dlaczego zarządzanie baseline zadania jest ważne?
Zarządzanie baseline zadania umożliwia porównanie planowanego harmonogramu z rzeczywistym postępem projektu, co ułatwia lepsze śledzenie i podejmowanie decyzji.

### Czy mogę modyfikować baseline zadania po jego ustawieniu?
Tak, możesz modyfikować baseline zadania w MS Project, aby odzwierciedlić zmiany w planie projektu. Ważne jest jednak dokumentowanie wszelkich odchyleń od pierwotnego baseline.

### Czy Aspose.Tasks obsługuje inne funkcje zarządzania projektami?
Tak, Aspose.Tasks oferuje szeroki zakres funkcji do zarządzania projektami, w tym harmonogramowanie zadań, przydział zasobów i generowanie wykresów Gantta.

### Gdzie mogę uzyskać wsparcie dla Aspose.Tasks?
Wsparcie dla Aspose.Tasks znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i wymieniać się doświadczeniami z innymi użytkownikami.

## Dodatkowe często zadawane pytania
**Q: Czy muszę wywoływać `setBaseline` dla każdego zadania osobno?**  
A: Nie. Wywołanie `project.setBaseline(BaselineType.Baseline)` zapisuje baseline dla wszystkich zadań w projekcie jednocześnie.

**Q: Jak ustawić interim baseline dla konkretnego zadania?**  
A: Użyj `project.setBaseline(BaselineType.Baseline1)` (lub Baseline2‑Baseline10) po zaktualizowaniu harmonogramu zadania.

**Q: Czy można wyeksportować dane baseline do CSV?**  
A: Tak. Przejdź pętlą po `task.getBaselines()` i zapisz wybrane pola do pliku CSV przy użyciu standardowego I/O Javy.

**Q: Czy mogę odczytać istniejący plik .mpp, który już zawiera baseline?**  
A: Oczywiście. Załaduj plik za pomocą `new Project("myproject.mpp")`, a następnie uzyskaj dostęp do baseline każdego zadania, jak pokazano powyżej.

**Q: Czy Aspose.Tasks obsługuje pliki wieloprojektowe?**  
A: Aspose.Tasks działa z pojedynczymi plikami .mpp. W scenariuszach wieloprojektowych projekty należy łączyć programowo.

---

**Ostatnia aktualizacja:** 2026-01-23  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}