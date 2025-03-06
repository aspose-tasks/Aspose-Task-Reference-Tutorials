---
title: Formuły MS Project z Aspose.Tasks dla Java
linktitle: Pracuj z formułami w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak manipulować plikami MS Project w Javie przy użyciu biblioteki Aspose.Tasks. Z łatwością twórz, modyfikuj i obliczaj atrybuty.
weight: 11
url: /pl/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Formuły MS Project z Aspose.Tasks dla Java

## Wstęp
W tym samouczku zagłębimy się w pracę z formułami MS Project przy użyciu Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka, która umożliwia programistom programowe manipulowanie plikami Microsoft Project. Dzięki rozbudowanym funkcjom możesz łatwo tworzyć, czytać, modyfikować i konwertować pliki projektów w aplikacjach Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
### Środowisko programistyczne Java
Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK). Najnowszą wersję pakietu JDK można pobrać i zainstalować ze strony internetowej Oracle.
### Biblioteka Aspose.Tasks
Musisz dodać bibliotekę Aspose.Tasks do swojego projektu Java. Bibliotekę można pobrać ze strony[Strona pobierania Aspose.Tasks dla Java](https://releases.aspose.com/tasks/java/) i dołącz go do zależności swojego projektu.

## Importuj pakiety
Zanim zagłębisz się w przykłady, zaimportuj niezbędne pakiety do swojego kodu Java:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Podzielmy podany przykład na kilka kroków:
## Krok 1: Utwórz projekt testowy z polem niestandardowym
```java
Project project = CreateTestProjectWithCustomField();
```
 Najpierw utwórz projekt testowy z niestandardowym polem, używając metody`CreateTestProjectWithCustomField()` metoda. Ta metoda zwróci obiekt Project reprezentujący nowo utworzony projekt.
## Krok 2: Zdefiniuj rozszerzoną definicję atrybutu
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Pobierz rozszerzoną definicję atrybutu z projektu i ustaw jej alias i formułę. W tym przykładzie definiujemy atrybut służący do obliczenia liczby dni od daty zakończenia do ostatecznego terminu.
## Krok 3: Ustal termin wykonania zadania
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Utwórz obiekt Kalendarz i ustaw termin ostateczny. Następnie pobierz zadanie z projektu i określ jego termin realizacji za pomocą obiektu Kalendarz.
## Krok 4: Zapisz projekt
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Na koniec zapisz projekt w pliku o określonej nazwie i formacie. W tym przypadku zapisujemy go jako plik MPP.

## Wniosek
W tym samouczku nauczyliśmy się, jak pracować z formułami MS Project przy użyciu Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie programowo manipulować plikami projektu, dodając niestandardowe pola i obliczając atrybuty na podstawie formuł.

## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi językami programowania?
Odp.: Tak, Aspose.Tasks obsługuje różne języki programowania, w tym Java, .NET i inne.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks ze strony[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć dokumentację dla Aspose.Tasks?
 O: Możesz znaleźć dokumentację Aspose.Tasks[Tutaj](https://reference.aspose.com/tasks/java/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks?
 O: Aby uzyskać pomoc, możesz odwiedzić stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: Czy potrzebuję tymczasowej licencji na korzystanie z Aspose.Tasks?
Odp.: Jeśli potrzebujesz dodatkowych funkcji, możesz uzyskać licencję tymczasową od[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
