---
title: Opanowanie liczenia skali czasu projektu MS w Aspose.Tasks
linktitle: Ustaw licznik skali czasu w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak efektywnie zarządzać skalą czasu w MS Project przy użyciu Aspose.Tasks dla Java. Bez wysiłku optymalizuj wizualizację projektu i zarządzanie nim.
type: docs
weight: 22
url: /pl/java/project-file-operations/set-time-scale-count/
---
## Wstęp
Zarządzanie skalą czasową w MS Project może znacząco wpłynąć na wizualizację i zarządzanie projektem. Dzięki Aspose.Tasks for Java, potężnemu API do programowej obsługi zadań związanych z zarządzaniem projektami, możesz efektywnie manipulować licznikiem skali czasu, aby dostosować widoki projektu do swoich konkretnych potrzeb.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz przygotowane następujące elementy:
1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK).
2.  Aspose.Tasks for Java Library: Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java. Możesz to dostać od[Tutaj](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość programowania w języku Java: Znajomość języka programowania Java będzie korzystna.

## Importuj pakiety
Zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Krok 1: Ustaw katalog danych
Zdefiniuj ścieżkę do katalogu danych, w którym będą przechowywane pliki projektu:
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` ze ścieżką do katalogu danych.
## Krok 2: Utwórz instancję projektu
 Utwórz instancję nowego`Project` obiekt:
```java
Project project = new Project();
```
Spowoduje to utworzenie nowego obiektu projektu.
## Krok 3: Skonfiguruj widok wykresu Gantta
 Stwórz`GanttChartView` obiekt do konfiguracji widoku wykresu Gantta:
```java
GanttChartView view = new GanttChartView();
```
## Krok 4: Ustaw licznik skali czasu dla dolnej warstwy
Ustaw widoczność liczby i znaczników dla dolnej warstwy skali czasu:
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
Określa liczbę interwałów i wyświetlanie znaczników najniższego poziomu.
## Krok 5: Ustaw licznik skali czasu dla warstwy środkowej
Podobnie skonfiguruj środkową warstwę skali czasu:
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## Krok 6: Dodaj widok do projektu
Dodaj skonfigurowany widok do projektu:
```java
project.getViews().add(view);
```
Spowoduje to dodanie dostosowanego widoku do projektu.
## Krok 7: Dodaj dane testowe do projektu
Dodaj trochę danych testowych do projektu w celu demonstracji:
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
Spowoduje to utworzenie dwóch zadań o określonym czasie trwania.
## Krok 8: Zapisz projekt jako plik PDF
Zapisz projekt jako plik PDF:
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
Spowoduje to zapisanie projektu z zastosowanymi konfiguracjami do pliku PDF.

## Wniosek
Efektywne zarządzanie skalą czasu w MS Project za pomocą Aspose.Tasks dla Java umożliwia dostosowywanie widoków projektu w celu lepszej wizualizacji i zarządzania.
## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje duże pliki projektów?
O: Tak, Aspose.Tasks for Java jest w stanie wydajnie obsługiwać duże pliki projektów.
### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi środowiskami IDE Java?
O: Tak, Aspose.Tasks for Java bezproblemowo współpracuje z popularnymi zintegrowanymi środowiskami programistycznymi Java (IDE), takimi jak Eclipse i IntelliJ IDEA.
### P: Czy mogę dostosować wygląd wykresów Gantta za pomocą Aspose.Tasks dla Java?
O: Oczywiście, Aspose.Tasks dla Java zapewnia szerokie możliwości dostosowywania wyglądu wykresów Gantta zgodnie z Twoimi wymaganiami.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
 O: Możesz znaleźć wsparcie i pomoc na forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).