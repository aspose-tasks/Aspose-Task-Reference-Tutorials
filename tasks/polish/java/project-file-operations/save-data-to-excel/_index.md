---
title: Zapisz dane projektu MS w programie Excel w Aspose.Tasks
linktitle: Zapisz dane w programie Excel w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zapisywać dane Microsoft Project w plikach Excel przy użyciu Aspose.Tasks dla Java. Łatwa integracja dla programistów Java.
weight: 19
url: /pl/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz dane projektu MS w programie Excel w Aspose.Tasks

## Wstęp
Aspose.Tasks dla Java to potężna biblioteka, która umożliwia programistom programową pracę z plikami Microsoft Project. W tym samouczku przeprowadzimy Cię krok po kroku przez proces zapisywania danych z pliku projektu do pliku Excel.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Możesz pobrać i zainstalować najnowszą wersję JDK ze strony internetowej Oracle.
2.  Biblioteka Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z witryny[link do pobrania](https://releases.aspose.com/tasks/java/) i dołącz go do swojego projektu Java.

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego kodu Java, aby móc pracować z Aspose.Tasks.
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Podzielmy podany przykład na kilka kroków:
## Krok 1: Zdefiniuj ścieżkę katalogu danych
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"`ze ścieżką do katalogu danych, w którym znajduje się plik projektu.
## Krok 2: Załaduj plik projektu
```java
Project project = new Project(dataDir + "project5.mpp");
```
Ta linia kodu ładuje plik projektu o nazwie „project5.mpp” z określonego katalogu danych.
## Krok 3: Zapisz projekt jako XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
 Tutaj`save` metoda służy do zapisania załadowanego pliku projektu jako pliku Excel o nazwie „project1.xlsx” w tym samym katalogu danych. Określamy`SaveFileFormat.Xlsx` parametr, aby zapisać go w formacie XLSX.

## Wniosek
W tym samouczku nauczyliśmy się, jak zapisywać dane z pliku Microsoft Project do pliku Excel przy użyciu Aspose.Tasks dla Java. Wykonując podane kroki, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami Java.
## Często zadawane pytania
### Czy mogę używać Aspose.Tasks dla Java do programowego manipulowania danymi projektu?
Tak, Aspose.Tasks dla Java zapewnia rozbudowane funkcje do manipulowania danymi projektu, w tym do odczytywania, zapisywania i modyfikowania plików projektu.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks dla Java ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Tasks dla Java?
Możesz znaleźć dokumentację Aspose.Tasks dla Java[Tutaj](https://reference.aspose.com/tasks/java/).
### Jak mogę uzyskać pomoc w przypadku jakichkolwiek problemów lub zapytań związanych z Aspose.Tasks dla Java?
 Możesz uzyskać pomoc, odwiedzając forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Java?
 Tak, możesz kupić tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
