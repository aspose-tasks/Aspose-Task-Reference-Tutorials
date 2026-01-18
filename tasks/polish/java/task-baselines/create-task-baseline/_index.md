---
date: 2026-01-18
description: Dowiedz się, jak utworzyć listę zadań w Javie i dodać zadanie do Microsoft
  Project, ustawiając bazę odniesienia bez użycia MS Project przy użyciu Aspose.Tasks.
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Utwórz listę zadań w Javie – bazę projektu MS Project przy użyciu Aspose.Tasks
url: /pl/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz listę zadań Java – baza linii czasu MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku **utworzysz listę zadań Java** generując bazę linii czasu zadania Microsoft Project przy użyciu Aspose.Tasks dla Javy. Aspose.Tasks pozwala pracować z plikami Project bez zainstalowanego Microsoft Project, dzięki czemu możesz **dodać zadanie do Microsoft Project**, manipulować zasobami i nawet **ustawić bazę linii czasu bez MS Project** — wszystko z czystego kodu Java.

## Szybkie odpowiedzi
- **Co robi Aspose.Tasks?** Udostępnia API Java do tworzenia, odczytywania i edytowania plików Microsoft Project bez MS Project.  
- **Czy muszę mieć zainstalowany Microsoft Project?** Nie, Aspose.Tasks działa niezależnie.  
- **Jaka wersja Javy jest wymagana?** JDK 8 lub wyższa.  
- **Czy mogę ustawić bazę linii czasu dla pojedynczego zadania?** Tak, użyj `setBaseline` z listą zadań.  
- **Czy wymagana jest licencja do produkcji?** Tak, licencja komercyjna usuwa ograniczenia wersji próbnej.

## Czym jest baza linii czasu zadania?
Baza linii czasu zadania zapisuje pierwotne planowane wartości rozpoczęcia, zakończenia i pracy dla zadania. Służy jako punkt odniesienia do porównania rzeczywistego postępu z pierwotnym planem.

## Dlaczego używać Aspose.Tasks do tworzenia listy zadań Java?
- **Brak zależności od MS Project** – idealne do automatyzacji po stronie serwera.  
- **Pełna kontrola** nad zadaniami, zasobami i kalendarzami za pomocą kodu Java.  
- **Kompatybilność między wersjami** z plikami Project 2007‑2024.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – zainstaluj JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz bibliotekę z [download link](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Aby rozpocząć pracę z Aspose.Tasks w swoim projekcie Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: Utwórz obiekt Project
```java
Project project = new Project();
```
Tutaj tworzymy nowy obiekt `Project` – reprezentuje on plik MS Project, który będzie zawierał naszą listę zadań.

## Krok 2: Dodaj zadanie do projektu
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Używając `getRootTask()` uzyskujemy dostęp do korzenia hierarchii projektu i **dodajemy zadanie do Microsoft Project**. Ciąg znaków `"Task"` jest nazwą zadania; możesz go zamienić na dowolny opis, którego potrzebujesz.

## Krok 3: Ustaw bazę linii czasu dla wybranych zadań
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Aby **ustawić bazę linii czasu bez MS Project**, utwórz listę zadań, które chcesz uwzględnić w bazie (tutaj `myList`) i przekaż ją do `setBaseline`. Wypełnij `myList` zadaniami, które dodałeś, jeśli potrzebujesz tylko wybranej bazy.

## Krok 4: Ustaw bazę linii czasu dla całego projektu
```java
project.setBaseline(BaselineType.Baseline);
```
Jeśli wolisz ustawić bazę dla całego projektu jednym wywołaniem, po prostu wywołaj `setBaseline` z żądanym `BaselineType`.

## Jak dodać zadanie do Microsoft Project przy użyciu Aspose.Tasks
Poza pojedynczym zadaniem pokazanym powyżej, możesz dodać wiele zadań, pod‑zadań i przydzielić zasoby. Każde wywołanie `add()` zwraca obiekt `Task`, który możesz dalej konfigurować (czas trwania, data rozpoczęcia itp.).

## Jak ustawić bazę linii czasu bez MS Project
Aspose.Tasks umożliwia tworzenie bazy linii czasu w pełni za pomocą kodu. Możesz ustawiać różne typy baz (Baseline, Baseline1‑Baseline10) zmieniając enum `BaselineType`, co pozwala śledzić wiele wersji baz bez konieczności otwierania MS Project.

## Typowe problemy i rozwiązania
- **Baza nie pojawia się:** Upewnij się, że wywołujesz `project.save("output.mpp")` po ustawieniu bazy (krok zapisu pominięty tutaj dla zwięzłości).  
- **Lista zadań jest pusta:** Sprawdź, czy dodajesz zadania do właściwego rodzica (`getRootTask()` lub pod‑zadania).  
- **Błędy niezgodności wersji:** Użyj najnowszego pliku JAR Aspose.Tasks, aby zapewnić kompatybilność z nowszymi formatami .mpp.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks dla Javy bez zainstalowanego Microsoft Project?**  
A: Tak, Aspose.Tasks działa niezależnie i nie wymaga Microsoft Project na maszynie hosta.

**Q: Czy Aspose.Tasks dla Javy jest kompatybilny z różnymi wersjami Microsoft Project?**  
A: Zdecydowanie. Biblioteka obsługuje pliki Project od 2007 do najnowszych wydań z 2024 roku.

**Q: Czy mogę manipulować zasobami projektu przy użyciu Aspose.Tasks dla Javy?**  
A: Tak, możesz programowo dodawać, aktualizować i usuwać zasoby, tak jak zadania.

**Q: Czy Aspose.Tasks dla Javy obsługuje ustawianie zależności zadań?**  
A: Tak, możesz definiować zależności poprzednik‑następca używając klasy `TaskLink`.

**Q: Czy dostępne jest wsparcie techniczne dla Aspose.Tasks dla Javy?**  
A: Tak, możesz uzyskać pomoc na [forum wsparcia](https://forum.aspose.com/c/tasks/15), gdzie pracownicy Aspose i społeczność odpowiadają na pytania.

## Podsumowanie
Postępując zgodnie z tymi krokami, nauczyłeś się jak **utworzyć listę zadań Java**, **dodać zadanie do Microsoft Project** oraz **ustawić bazę linii czasu bez MS Project** przy użyciu Aspose.Tasks. To podejście usprawnia automatyzację projektów, eliminuje potrzebę instalacji desktopowej wersji Project i daje pełną programistyczną kontrolę nad danymi projektu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-18  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose