---
title: Określ wersję projektu MS za pomocą Aspose.Tasks
linktitle: Określ wersję projektu za pomocą Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak programowo określić wersję plików MS Project za pomocą Aspose.Tasks dla Java. Przewodnik krok po kroku z przykładami kodu.
weight: 12
url: /pl/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Określ wersję projektu MS za pomocą Aspose.Tasks

## Wstęp
Ten samouczek poprowadzi Cię krok po kroku przez proces korzystania z Aspose.Tasks for Java w celu ustalenia wersji pliku MS Project. Aspose.Tasks to potężny interfejs API języka Java, który umożliwia programistom manipulowanie plikami programu Microsoft Project bez konieczności instalowania programu Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Plik JAR Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z pliku[strona internetowa](https://releases.aspose.com/tasks/java/) i dodaj go do swojego projektu Java.
3. Plik MS Project: Przygotuj plik MS Project (w formacie XML) do testów.

## Importuj pakiety
Zanim zagłębimy się w kod, zaimportujmy niezbędne pakiety:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Krok 1: Skonfiguruj projekt
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` ze ścieżką do katalogu zawierającego plik MS Project.
## Krok 2: Załaduj projekt
```java
Project project = new Project(dataDir + "input.xml");
```
 Zastępować`"input.xml"` z nazwą pliku MS Project.
## Krok 3: Określ wersję projektu
```java
//Wyświetl właściwość wersji projektu
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
Ten fragment kodu pobiera i drukuje wersję oraz datę ostatniego zapisania pliku MS Project.
## Krok 4: Wyświetl wynik
```java
//Wyświetl wynik konwersji.
System.out.println("Process completed Successfully");
```
Ta linia oznacza zakończenie procesu.

## Wniosek
W tym samouczku nauczyłeś się, jak określić wersję pliku MS Project za pomocą Aspose.Tasks dla Java. Postępując zgodnie z instrukcją krok po kroku, możesz efektywnie i bezproblemowo pracować z plikami MS Project w aplikacjach Java.

## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi językami programowania?
Odp.: Tak, Aspose.Tasks obsługuje wiele języków programowania, w tym .NET, Java i C++.
### P: Czy Aspose.Tasks nadaje się do projektów na dużą skalę?
O: Oczywiście, Aspose.Tasks został zaprojektowany tak, aby z łatwością obsługiwać projekty dowolnej wielkości.
### P: Czy mogę dostosować dane projektu za pomocą Aspose.Tasks?
O: Tak, możesz manipulować danymi projektu, modyfikować zadania, zasoby i wiele więcej, używając Aspose.Tasks.
### P: Czy Aspose.Tasks wymaga instalacji Microsoft Project?
O: Nie, Aspose.Tasks działa niezależnie i nie wymaga instalacji programu Microsoft Project.
### P: Czy dostępna jest pomoc techniczna dla Aspose.Tasks?
 Odp.: Tak, możesz uzyskać pomoc techniczną na forum Aspose.Tasks pod adresem[Tutaj](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
