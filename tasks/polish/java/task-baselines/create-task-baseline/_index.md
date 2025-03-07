---
title: Utwórz linię bazową zadań MS Project w Aspose.Tasks
linktitle: Tworzenie planu bazowego zadań w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak utworzyć linię bazową zadań Microsoft Project w Javie przy użyciu Aspose.Tasks, potężnej biblioteki do łatwego zarządzania danymi projektu.
weight: 11
url: /pl/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz linię bazową zadań MS Project w Aspose.Tasks

## Wstęp
tym samouczku zagłębimy się w proces tworzenia linii bazowej zadań Microsoft Project przy użyciu Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project. Dzięki Aspose.Tasks możesz bez wysiłku manipulować danymi projektu, w tym zadaniami, zasobami i kalendarzami, aby usprawnić zadania związane z zarządzaniem projektami.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Aspose.Tasks for Java wymaga zainstalowania pakietu JDK w systemie. Możesz pobrać i zainstalować JDK ze strony internetowej Oracle.
2.  Biblioteka Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z witryny[link do pobrania](https://releases.aspose.com/tasks/java/) pod warunkiem, że.

## Importuj pakiety
Aby rozpocząć pracę z Aspose.Tasks w swoim projekcie Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## Krok 1: Utwórz obiekt projektu
```java
Project project = new Project();
```
 Najpierw utwórz nowy`Project` obiekt. Ten obiekt reprezentuje plik Microsoft Project, z którym będziesz pracować.
## Krok 2: Dodaj zadanie do projektu
```java
Task task = project.getRootTask().getChildren().add("Task");
```
 Używając`getRootTask()` uzyskaj dostęp do zadania głównego projektu, a następnie dodaj do niego nowe zadanie za pomocą metody`add()` metoda. Podaj nazwę zadania w nawiasach.
## Krok 3: Ustaw linię bazową dla określonych zadań
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
Aby ustawić punkt odniesienia dla konkretnych zadań, utwórz listę zadań (`myList` w tym przypadku) i wypełnij go zadaniami, dla których chcesz ustawić linię bazową. Następnie skorzystaj z`setBaseline()` metodę, określając typ bazowy i listę zadań.
## Krok 4: Ustaw linię bazową dla całego projektu
```java
project.setBaseline(BaselineType.Baseline);
```
 Alternatywnie możesz ustawić punkt odniesienia dla całego projektu, po prostu wywołując metodę`setBaseline()` metodę z określonym typem linii bazowej.

## Wniosek
W tym samouczku omówiliśmy, jak utworzyć linię bazową zadań programu Microsoft Project przy użyciu Aspose.Tasks dla języka Java. Wykonując czynności opisane powyżej, możesz efektywnie zarządzać danymi projektu i z łatwością usprawniać zadania związane z zarządzaniem projektami.
## Często zadawane pytania
### Czy mogę używać Aspose.Tasks dla Java bez zainstalowanego programu Microsoft Project?
Tak, Aspose.Tasks for Java umożliwia pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project w systemie.
### Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami Microsoft Project?
Tak, Aspose.Tasks for Java obsługuje różne wersje Microsoft Project, zapewniając kompatybilność w różnych środowiskach.
### Czy mogę manipulować zasobami projektu za pomocą Aspose.Tasks dla Java?
Absolutnie Aspose.Tasks dla Java zapewnia solidne funkcje do manipulowania zasobami projektu, w tym dodawania, aktualizowania i usuwania zasobów w razie potrzeby.
### Czy Aspose.Tasks for Java obsługuje ustawianie zależności zadań?
Tak, możesz bez wysiłku ustawić zależności zadań za pomocą Aspose.Tasks dla Java, umożliwiając ustalenie sekwencji zadań w projekcie.
### Czy dostępna jest pomoc techniczna dla Aspose.Tasks dla Java?
 Tak, możesz uzyskać dostęp do pomocy technicznej dla Aspose.Tasks dla Java poprzez[forum wsparcia](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i zwracać się o pomoc do społeczności oraz personelu pomocniczego Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
