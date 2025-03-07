---
title: Zapisz jako plik CSV, tekst i szablon w Aspose.Tasks
linktitle: Zapisz jako plik CSV, tekst i szablon w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zapisywać pliki Microsoft Project w formatach CSV, tekstowych i szablonach przy użyciu Aspose.Tasks dla Java.
weight: 16
url: /pl/java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz jako plik CSV, tekst i szablon w Aspose.Tasks

## Wstęp
tym samouczku omówimy, jak zapisywać pliki projektu w różnych formatach, takich jak CSV, tekst i szablon, za pomocą Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom pracę z plikami Microsoft Project bez konieczności instalowania Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Biblioteka Aspose.Tasks dla Java pobrana i skonfigurowana w projekcie Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość języka programowania Java.

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do pliku Java:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Zapisz projekt jako plik CSV
Podzielmy kroki, aby zapisać projekt jako plik CSV:
### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Zapisz jako CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Zapisz projekt jako tekst
Oto jak zapisać projekt jako tekst:
### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Zapisz jako tekst
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Zapisz projekt jako szablon
Zapisanie projektu jako szablonu obejmuje następujące kroki:
### Krok 1: Załaduj projekt
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Krok 2: Ustaw opcje szablonu
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Krok 3: Zapisz jako szablon
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Wniosek
tym samouczku nauczyliśmy się, jak zapisywać pliki Microsoft Project jako CSV, tekst i szablon za pomocą Aspose.Tasks dla Java. Dzięki tym prostym krokom możesz efektywnie zarządzać plikami projektu w różnych formatach, zwiększając swoją produktywność jako programisty Java.
## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje złożone pliki projektów?
Odp.: Absolutnie! Aspose.Tasks for Java może z łatwością obsługiwać projekty o różnym stopniu złożoności, zapewniając kompleksową obsługę formatów plików Microsoft Project.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Tasks dla Java od[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks dla Java?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub zapytań dotyczących Aspose.Tasks for Java.
### P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Java?
 Odpowiedź: Tak, możesz kupić tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/), co pozwala ocenić pełny potencjał biblioteki.
### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi systemami operacyjnymi?
Odp.: Tak, Aspose.Tasks for Java jest kompatybilny z różnymi systemami operacyjnymi, w tym Windows, macOS i Linux.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
