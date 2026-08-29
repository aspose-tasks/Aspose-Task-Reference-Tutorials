---
date: 2026-08-29
description: Dowiedz się, jak dodać zadanie do projektu w Javie, utworzyć listę zadań
  i ustawić baseline bez Microsoft Project, korzystając z Aspose.Tasks.
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: Tworzenie baseline zadania w Aspose.Tasks
og_description: Dowiedz się, jak dodać zadanie do projektu w Javie i ustawić baseline
  przy użyciu Aspose.Tasks. Ten przewodnik pokazuje kod krok po kroku, bez potrzeby
  Microsoft Project.
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: Jak dodać zadanie do projektu w Javie i ustawić baseline
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: Jak dodać zadanie do projektu w Javie i ustawić baseline
url: /pl/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać zadanie do projektu w Javie i ustawić baseline

## Wprowadzenie
W tym samouczku **dodasz zadanie do projektu** programowo, wygenerujesz baseline zadania w Microsoft Project i zapiszesz plik — wszystko bez otwierania Microsoft Project. Aspose.Tasks for Java zapewnia czysto‑Java API, które działa na każdej platformie, co czyni je idealnym dla zautomatyzowanych potoków budowania, usług raportowania lub dowolnego rozwiązania po stronie serwera, które musi manipulować plikami .mpp.

## Szybkie odpowiedzi
- **Do czego służy Aspose.Tasks?** Zapewnia Java API do tworzenia, odczytywania i edytowania plików Microsoft Project bez wymogu posiadania Microsoft Project.  
- **Czy muszę mieć zainstalowany Microsoft Project?** Nie, biblioteka działa całkowicie niezależnie.  
- **Jakiej wersji Java wymaga?** JDK 8 lub nowszy.  
- **Czy mogę ustawić baseline dla pojedynczego zadania?** Tak – wywołaj `setBaseline` na liście zawierającej tylko wybrane zadania.  
- **Czy potrzebna jest licencja do produkcji?** Tak, licencja komercyjna usuwa ograniczenia wersji próbnej i odblokowuje wszystkie funkcje.

## Czym jest baseline zadania?
Baseline zadania rejestruje pierwotnie zaplanowaną datę rozpoczęcia, datę zakończenia oraz nakład pracy dla zadania w momencie pierwszego zapisania harmonogramu. Ten migawkowy zapis służy jako punkt odniesienia, umożliwiając kierownikom projektów porównanie rzeczywistego postępu i kosztów z pierwotnym planem oraz obliczenie odchyleń w analizie wydajności.

## Dlaczego używać Aspose.Tasks do dodawania zadania do projektu w Javie?
Możesz tworzyć, modyfikować i ustawiać baseline zadania bez żadnej instalacji na komputerze, co umożliwia w pełni zautomatyzowane przepływy pracy. Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** i może obsługiwać projekty z **setkami zadań**, przy jednoczesnym utrzymaniu zużycia pamięci poniżej 200 MB, co czyni je idealnym dla usług w chmurze i potoków CI/CD.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – zainstaluj JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz bibliotekę z [download link](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Aby rozpocząć pracę z Aspose.Tasks w projekcie Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: utwórz obiekt projektu
Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje plik Microsoft Project w pamięci. Utworzenie jej instancji daje pusty projekt, który możesz wypełnić zadaniami, zasobami i kalendarzami.

```java
Project project = new Project();
```
Tutaj tworzymy nowy obiekt `Project` – reprezentuje on plik MS Project, który będzie zawierał naszą listę zadań.

## Krok 2: dodaj zadanie do projektu
Klasa `Task` reprezentuje pojedynczy element pracy w harmonogramie projektu. Każde `Task` może mieć własny czas trwania, datę rozpoczęcia i przydziały zasobów.

```java
Task task = project.getRootTask().getChildren().add("Task");
```
Używając `getRootTask()` uzyskujemy dostęp do korzenia hierarchii projektu i **dodajemy zadanie do Microsoft Project**. Ciąg znaków `"Task"` jest nazwą zadania; możesz go zamienić na dowolny opis, którego potrzebujesz.

## Krok 3: ustaw baseline dla wybranych zadań
`BaselineType` jest wyliczeniem definiującym, który slot baseline (Baseline, Baseline1 … Baseline10) ma zostać zapisany. Przekazując listę zadań, możesz ustawić baseline tylko dla wybranych elementów.

```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Aby **ustawić baseline bez MS Project**, utwórz listę zadań, które chcesz objąć baseline (tutaj `myList`) i przekaż ją do `setBaseline`. Wypełnij `myList` zadaniami, które dodałeś, jeśli potrzebujesz selektywnego baseline.

## Krok 4: ustaw baseline dla całego projektu
`setBaseline` zapisuje wybrane wartości baseline do każdego zadania w projekcie.  
Jeśli wolisz ustawić baseline całego projektu jednym wywołaniem, po prostu wywołaj `setBaseline` z żądanym `BaselineType`.

```java
project.setBaseline(BaselineType.Baseline);
```
To wywołanie zapisuje wybrane wartości baseline dla **każdego zadania** w projekcie, zapewniając pełną migawkę pierwotnego harmonogramu.

## Jak dodać zadanie do Microsoft Project przy użyciu Aspose.Tasks
`add()` tworzy nowe zadanie podrzędne pod określonym zadaniem nadrzędnym i zwraca nowo utworzony obiekt `Task`.  
Dodajesz zadanie, wywołując `add()` na obiekcie `Task` będącym rodzicem (zazwyczaj jest to zadanie główne). Metoda zwraca nową instancję `Task`, którą możesz dalej konfigurować — czas trwania, datę rozpoczęcia, zasoby lub pola niestandardowe — przed zapisaniem pliku projektu.

## Jak ustawić baseline bez MS Project
Aspose.Tasks umożliwia tworzenie baseline w pełni za pomocą kodu. Wybierz `BaselineType` (np. `BaselineType.Baseline`) i wywołaj `setBaseline`. Możesz powtórzyć to z `Baseline1`‑`Baseline10`, aby zachować wiele wersji baseline, wszystko bez otwierania Microsoft Project.

## Typowe problemy i rozwiązania
- **Baseline nie pojawia się:** Upewnij się, że wywołujesz `project.save("output.mpp")` po ustawieniu baseline (krok zapisu pominięty tutaj dla zwięzłości).  
- **Lista zadań jest pusta:** Sprawdź, czy dodajesz zadania do właściwego rodzica (`getRootTask()` lub podzadania).  
- **Błędy niezgodności wersji:** Użyj najnowszego pliku JAR Aspose.Tasks, aby zapewnić kompatybilność z nowszymi formatami .mpp.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks dla Javy bez zainstalowanego Microsoft Project?**  
A: Tak, Aspose.Tasks działa niezależnie i nie wymaga Microsoft Project na maszynie hosta.

**Q: Czy Aspose.Tasks dla Javy jest kompatybilny z różnymi wersjami Microsoft Project?**  
A: Zdecydowanie. Biblioteka obsługuje pliki Project od wersji 2007 aż po najnowsze wydania z 2024 roku.

**Q: Czy mogę manipulować zasobami projektu przy użyciu Aspose.Tasks dla Javy?**  
A: Tak, możesz dodawać, aktualizować i usuwać zasoby programowo, tak jak zadania.

**Q: Czy Aspose.Tasks dla Javy obsługuje ustawianie zależności zadań?**  
A: Tak, możesz definiować zależności poprzednik‑następnik przy użyciu klasy `TaskLink`.

**Q: Czy dostępne jest wsparcie techniczne dla Aspose.Tasks dla Javy?**  
A: Tak, pomoc można uzyskać poprzez [support forum](https://forum.aspose.com/c/tasks/15), gdzie personel Aspose i społeczność odpowiadają na pytania.

## Podsumowanie
Postępując zgodnie z tymi krokami, nauczyłeś się **dodawać zadanie do projektu** w Javie, tworzyć listę zadań i **ustawiać baseline bez MS Project** przy użyciu Aspose.Tasks. To podejście usprawnia automatyzację projektów, eliminuje potrzebę instalacji desktopowej wersji Project i daje pełną kontrolę programistyczną nad każdym aspektem harmonogramu.

---

**Ostatnia aktualizacja:** 2026-08-29  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć projekt aspose.tasks – Ustaw nowe atrybuty zadania](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [Jak ustawić czas trwania baseline w Aspose.Tasks dla Javy](/tasks/java/task-baselines/task-baseline-duration/)
- [Tworzenie zadań Aspose Java – Właściwości zadania](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}