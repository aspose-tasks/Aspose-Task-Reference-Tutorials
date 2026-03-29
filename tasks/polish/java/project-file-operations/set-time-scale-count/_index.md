---
date: 2026-03-29
description: Dowiedz się, jak tworzyć pliki PDF projektów, dostosowując liczbę jednostek
  skali czasu wykresu Gantta przy użyciu Aspose.Tasks for Java. Ten przewodnik pokazuje
  krok po kroku, jak wyeksportować wykres Gantta do PDF z pełną kontrolą.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Utwórz PDF projektu – Dostosuj skalę czasu wykresu Gantta
url: /pl/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz PDF projektu – Dostosuj skalę czasu wykresu Gantta

## Wprowadzenie
Jeśli potrzebujesz **utworzyć PDF projektu** pliki, które odzwierciedlają idealnie dopasowany wykres Gantta, kluczem jest kontrolowanie liczby jednostek skali czasu. Dzięki Aspose.Tasks for Java możesz programowo ustawić dolne i środkowe poziomy skali czasu, ukryć znaczniki podziałki, a następnie **zapisz projekt jako PDF** w celu łatwej dystrybucji. W tym samouczku przeprowadzimy Cię przez wszystko, czego potrzebujesz — od konfiguracji środowiska programistycznego po wygenerowanie dopracowanego PDF, który prezentuje Twój dostosowany widok Gantta.

## Szybkie odpowiedzi
- **Co oznacza „dostosowanie wykresu Gantta”?** Dostosowywanie poziomów skali czasu, kolorów i układu, aby odpowiadały Twoim potrzebom raportowania.  
- **Która metoda API ustawia liczbę jednostek dolnego poziomu?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Czy mogę wygenerować PDF bezpośrednio z projektu?** Tak — użyj `project.save(..., SaveFileFormat.Pdf)`.  
- **Czy potrzebuję licencji do użytku produkcyjnego?** Wymagana jest licencja komercyjna; dostępna jest wersja próbna.  
- **Która wersja Java jest obsługiwana?** Java 8 lub nowsza działa z najnowszą biblioteką Aspose.Tasks.

## Co oznacza „dostosowanie wykresu Gantta” w Aspose.Tasks?
Dostosowywanie wykresu Gantta oznacza programowe zmienianie jego elementów wizualnych — takich jak interwały skali czasu, znaczniki podziałki i paski zadań — tak aby wykres odpowiadał temu, jak chcesz **zarządzać wizualizacją projektu**. Zmieniając liczbę jednostek skali czasu, kontrolujesz ile dni, tygodni lub miesięcy reprezentuje każdy segment, co sprawia, że wykres jest czytelniejszy dla różnych odbiorców.

## Dlaczego tworzyć PDF projektu z dostosowanym wykresem Gantta?
- **Wyjście gotowe dla interesariuszy:** PDF jest uniwersalnie wyświetlany, zapewniając, że każdy widzi ten sam układ harmonogramu.  
- **Przyjazny do druku:** Precyzyjna kontrola nad poziomami skali czasu zapobiega zatłoczonym lub niejasnym wydrukom.  
- **Automatyzacja:** Zintegruj generowanie PDF z potokami CI lub usługami raportowania, aby osiągnąć zero ręcznego wysiłku.  

## Wymagania wstępne
1. **Java Development Environment** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java Library** – pobierz ją z [here](https://releases.aspose.com/tasks/java/).  
3. **Basic Java Knowledge** – znajomość składni Java i koncepcji programowania obiektowego.

## Importowanie pakietów
Import the necessary classes into your Java project:

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog danych
Define where your project files will be read from and written to:

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine.

### Krok 2: Utwórz nową instancję projektu
Instantiate a fresh `Project` object that will hold all tasks and view settings:

```java
Project project = new Project();
```

### Krok 3: Skonfiguruj widok wykresu Gantta
Create a `GanttChartView` object—this is where you’ll **generować widok Gantta w Javie** code to control the chart appearance:

```java
GanttChartView view = new GanttChartView();
```

### Krok 4: Ustaw liczbę jednostek skali czasu dla dolnego poziomu
Adjust the bottom tier to show two intervals and hide the tick marks:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Krok 5: Ustaw liczbę jednostek skali czasu dla środkowego poziomu
Apply the same configuration to the middle tier:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Krok 6: Dodaj dostosowany widok do projektu
Attach the view you just configured to the `Project` instance:

```java
project.getViews().add(view);
```

### Krok 7: Dodaj przykładowe zadania (dane testowe)
Create a couple of tasks with specific durations to illustrate the customized Gantt chart:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Krok 8: Zapisz projekt jako PDF
Finally, export the project—including your **dostosowany wykres Gantta**—to a PDF file:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

The resulting PDF demonstrates how the bottom and middle time‑scale tiers have been **customized**, giving stakeholders a clear, printable view of the schedule.

## Typowe problemy i rozwiązywanie
- **PDF is blank** – Ensure the `dataDir` path ends with a file separator (`/` or `\`) and that the directory exists.  
- **Ticks still appear** – Verify that `setShowTicks(false)` is called on both tiers.  
- **Duration not applied** – Confirm you are using `TimeUnitType.Hour` (or the appropriate unit) when creating durations.

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for Java radzi sobie z dużymi plikami projektów?**  
A: Tak, biblioteka jest zoptymalizowana pod kątem wysokowydajnego przetwarzania rozbudowanych danych projektowych.

**Q: Czy Aspose.Tasks for Java jest kompatybilny z różnymi środowiskami IDE Java?**  
A: Absolutnie – działa bezproblemowo z Eclipse, IntelliJ IDEA, NetBeans i innymi popularnymi IDE.

**Q: Czy mogę dostosować wygląd wykresów Gantta poza ustawieniami skali czasu?**  
A: Tak, Aspose.Tasks oferuje rozbudowane opcje stylizacji, takie jak kolory pasków, czcionki i linie siatki.

**Q: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
A: Tak, możesz uzyskać darmową wersję próbną z [here](https://releases.aspose.com/).

**Q: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Wsparcie i pomoc znajdziesz na forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

**Q: Jak programowo zmienić kolor tła wykresu Gantta?**  
A: Użyj metody `view.getGanttChartProperties().setBackgroundColor(Color)` po zaimportowaniu `java.awt.Color`.

## Zakończenie
By following these steps you’ve learned how to **create project PDF** files with a fully customized Gantt chart time‑scale, improve **project visualization**, and **save project as PDF** using Aspose.Tasks for Java. This approach gives you full control over the visual output, making it easier to share clear, professional schedules with your team or clients.

---

**Ostatnia aktualizacja:** 2026-03-29  
**Testowano z:** Aspose.Tasks for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}