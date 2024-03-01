---
title: Oblicz krytyczną ścieżkę projektu MS w Aspose.Tasks
linktitle: Oblicz ścieżkę krytyczną w projektach Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak obliczyć ścieżkę krytyczną w MS Project przy użyciu Aspose.Tasks dla Java. Zawiera wskazówki krok po kroku dotyczące skutecznego zarządzania projektem.
type: docs
weight: 10
url: /pl/java/project-management/critical-path/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces obliczania ścieżki krytycznej w MS Project przy użyciu Aspose.Tasks dla Java. Ścieżka krytyczna jest niezbędna w zarządzaniu projektami, ponieważ pomaga określić kolejność zadań, które należy wykonać na czas, aby ogólny harmonogram projektu nie uległ opóźnieniom.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Biblioteka Aspose.Tasks dla Java pobrana i dodana do Twojego projektu. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojej klasy Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Skonfiguruj katalog danych
Zdefiniuj ścieżkę do katalogu danych, w którym znajduje się plik MS Project.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Załaduj plik projektu MS
Załaduj plik MS Project przy użyciu biblioteki Aspose.Tasks.
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## Krok 3: Ustaw tryb obliczeń
Ustaw tryb obliczeń na automatyczny, aby umożliwić obliczenie ścieżki krytycznej.
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## Krok 4: Dodaj zadania
Dodaj zadania do swojego projektu. W tym przykładzie dodajemy trzy podzadania.
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## Krok 5: Utwórz łącza do zadań
Utwórz łącza do zadań, aby zdefiniować zależności między zadaniami.
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## Krok 6: Wyświetl ścieżkę krytyczną
Pobierz i wyświetl ścieżkę krytyczną projektu.
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## Krok 7: Wyświetl wynik
Wyświetl komunikat informujący o pomyślnym zakończeniu procesu.
```java
System.out.println("Process completed Successfully");
```

## Wniosek
Obliczanie ścieżki krytycznej w MS Project za pomocą Aspose.Tasks dla Java jest kluczowe dla efektywnego zarządzania projektami. Wykonując kroki opisane w tym samouczku, możesz dokładnie określić sekwencję zadań krytycznych dla osi czasu projektu.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks dla Java z dowolną wersją plików MS Project?
O: Tak, Aspose.Tasks for Java obsługuje różne wersje plików MS Project, w tym pliki .mpp z MS Project 2003 do MS Project 2019.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla Java?
 O: Pomoc znajdziesz na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Java?
 Odpowiedź: Tak, możesz kupić tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).
### P: Jak mogę kupić Aspose.Tasks dla Java?
 O: Możesz kupić Aspose.Tasks dla Java na stronie internetowej[Tutaj](https://purchase.aspose.com/buy).