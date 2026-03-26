---
date: 2025-12-21
description: Dowiedz się, jak dostosować widoki wykresu Gantta, zarządzać wizualizacją
  projektu i zapisywać projekt jako PDF przy użyciu Aspose.Tasks for Java. Łatwo dostosuj
  liczbę jednostek skali czasu.
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Dostosuj wykres Gantta – opanowanie liczenia skali czasu w MS Project w Aspose.Tasks
url: /pl/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostosuj wykres Gantta – Opanowanie liczby skali czasu w MS Project w Aspose.Tasks

## Wprowadzenie
Jeśli potrzebujesz **dostosować wykres Gantta** w Microsoft Project, kontrola liczby skali czasu jest kluczową techniką. Dzięki Aspose.Tasks for Java możesz programowo ustawić dolny i środkowy poziom skali czasu, precyzyjnie dostroić widoczność znaczników oraz **zapisać projekt jako PDF**, aby udostępnić go interesariuszom. Ten samouczek przeprowadzi Cię przez cały proces – od konfiguracji środowiska po wygenerowanie eleganckiego PDF‑a odzwierciedlającego Twoje spersonalizowane widoki Gantta.

## Szybkie odpowiedzi
- **Co oznacza „dostosować wykres Gantta”?** Dostosowanie poziomów skali czasu, kolorów i układu do potrzeb raportowania.  
- **Która metoda API ustawia liczbę dolnego poziomu?** `view.getBottomTimescaleTier().setCount(int)`.  
- **Czy mogę wygenerować PDF bezpośrednio z projektu?** Tak – użyj `project.save(..., SaveFileFormat.Pdf)`.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest licencja komercyjna; dostępna jest wersja próbna.  
- **Jaką wersję Javy obsługuje biblioteka?** Java 8 lub nowsza współpracuje z najnowszą wersją Aspose.Tasks.

## Co oznacza „dostosowanie wykresu Gantta” w Aspose.Tasks?
Dostosowanie wykresu Gantta oznacza programowe modyfikowanie jego elementów wizualnych – takich jak interwały skali czasu, znaczniki oraz paski zadań – tak, aby wykres odpowiadał Twojemu **zarządzaniu wizualizacją projektu**. Zmieniając liczbę skali czasu, kontrolujesz, ile dni, tygodni lub miesięcy reprezentuje każdy segment, co czyni wykres czytelniejszym dla różnych odbiorców.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Środowisko programistyczne Java** – zainstalowany JDK 8 lub nowszy.  
2. **Bibliotekę Aspose.Tasks for Java** – pobierz ją z [tutaj](https://releases.aspose.com/tasks/java/).  
3. **Podstawową znajomość Javy** – znajomość składni i koncepcji obiektowych.

## Importowanie pakietów
Zaimportuj niezbędne klasy do swojego projektu Java:

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
Zdefiniuj, skąd będą odczytywane i gdzie będą zapisywane pliki projektu:

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` absolutną ścieżką na swoim komputerze.

### Krok 2: Utwórz nową instancję projektu
Zainicjuj nowy obiekt `Project`, który będzie przechowywał wszystkie zadania i ustawienia widoku:

```java
Project project = new Project();
```

### Krok 3: Skonfiguruj widok wykresu Gantta
Utwórz obiekt `GanttChartView` – to tutaj **generujesz kod Java widoku Gantta**, aby kontrolować wygląd wykresu:

```java
GanttChartView view = new GanttChartView();
```

### Krok 4: Ustaw liczbę skali czasu dla dolnego poziomu
Dostosuj dolny poziom, aby wyświetlał dwa interwały i ukryj znaczniki:

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Krok 5: Ustaw liczbę skali czasu dla środkowego poziomu
Zastosuj tę samą konfigurację do środkowego poziomu:

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Krok 6: Dodaj dostosowany widok do projektu
Dołącz skonfigurowany widok do instancji `Project`:

```java
project.getViews().add(view);
```

### Krok 7: Dodaj przykładowe zadania (dane testowe)
Utwórz kilka zadań o określonych czasach trwania, aby zilustrować spersonalizowany wykres Gantta:

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Krok 8: Zapisz projekt jako PDF
Na koniec wyeksportuj projekt – wraz z **dostosowanym wykresem Gantta** – do pliku PDF:

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

Wygenerowany PDF pokazuje, jak dolny i środkowy poziom skali czasu zostały **spersonalizowane**, zapewniając interesariuszom przejrzysty, drukowalny widok harmonogramu.

## Typowe problemy i rozwiązywanie
- **PDF jest pusty** – Upewnij się, że ścieżka `dataDir` kończy się separatorem plików (`/` lub `\`) i że katalog istnieje.  
- **Znaczniki wciąż się wyświetlają** – Sprawdź, czy metoda `setShowTicks(false)` została wywołana dla obu poziomów.  
- **Czas trwania nie został zastosowany** – Potwierdź, że przy tworzeniu czasów używasz `TimeUnitType.Hour` (lub odpowiedniej jednostki).

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for Java radzi sobie z dużymi plikami projektów?**  
O: Tak, biblioteka jest zoptymalizowana pod kątem wysokowydajnego przetwarzania rozbudowanych danych projektowych.

**P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi IDE Javy?**  
O: Absolutnie – działa bezproblemowo w Eclipse, IntelliJ IDEA, NetBeans i innych popularnych środowiskach.

**P: Czy mogę dostosować wygląd wykresu Gantta poza ustawieniami skali czasu?**  
O: Tak, Aspose.Tasks oferuje rozbudowane opcje stylizacji, takie jak kolory pasków, czcionki i linie siatki.

**P: Czy dostępna jest wersja próbna Aspose.Tasks for Java?**  
O: Tak, możesz uzyskać wersję próbną za darmo z [tutaj](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
O: Wsparcie i pomoc znajdziesz na forum Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**P: Jak programowo zmienić kolor tła wykresu Gantta?**  
O: Użyj metody `view.getGanttChartProperties().setBackgroundColor(Color)` po zaimportowaniu `java.awt.Color`.

## Podsumowanie
Korzystając z powyższych kroków, nauczyłeś się **dostosowywać poziomy skali czasu wykresu Gantta**, ulepszać **wizualizację projektu** oraz **zapisywać projekt jako PDF** przy użyciu Aspose.Tasks for Java. To podejście daje pełną kontrolę nad wyjściem wizualnym, ułatwiając udostępnianie przejrzystych, profesjonalnych harmonogramów Twojemu zespołowi lub klientom.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}