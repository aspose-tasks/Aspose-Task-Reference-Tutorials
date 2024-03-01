---
title: Napisz podsumowanie projektu MPP w Aspose.Tasks
linktitle: Napisz podsumowanie projektu MPP w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak pisać podsumowania projektów MPP w Javie przy użyciu Aspose.Tasks. Bezproblemowo ustawiaj i pobieraj informacje o projekcie.
type: docs
weight: 27
url: /pl/java/project-file-operations/write-mpp-project-summary/
---
## Wstęp
W tym samouczku dowiemy się, jak używać Aspose.Tasks dla Java do pisania podsumowań projektów MPP. Aspose.Tasks to potężna biblioteka Java do pracy z plikami Microsoft Project. Wykonując kroki opisane poniżej, będziesz mógł ustawić i pobrać różne informacje podsumowujące o projekcie korzystającym z tej biblioteki.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Aspose.Tasks dla Java: Pobierz i zainstaluj bibliotekę Aspose.Tasks dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Zintegrowane środowisko programistyczne (IDE): wybierz preferowane środowisko IDE do programowania w języku Java, takie jak IntelliJ IDEA, Eclipse lub NetBeans.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do swojej klasy Java:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Krok 1: Skonfiguruj projekt i zdefiniuj informacje podsumowujące
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Data Directory";
//Zainicjuj nowy obiekt projektu ze ścieżką do pliku projektu
Project project = new Project(dataDir + "project.mpp");
// Ustaw podsumowanie informacji o projekcie
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Ustaw datę utworzenia projektu
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Ustaw słowa kluczowe dla projektu
project.set(Prj.KEYWORDS, "MPP Aspose");
// Ustaw ostatnią wydrukowaną datę projektu
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Krok 2: Zapisz informacje podsumowujące projekt
```java
// Zapisz projekt ponownie w formacie MPP
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Wyświetl komunikat o powodzeniu
System.out.println("Process completed Successfully");
```
## Krok 3: Przeczytaj informacje podsumowujące projekt
```java
// Czytanie informacji podsumowujących projekt
project = new Project(dataDir + "MppAspose.xml");
// Autor druku projektu
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Wydrukuj ostatniego autora projektu
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Wydrukuj numer wersji projektu
System.out.println("Revision: " + project.get(Prj.REVISION));
// Wydrukuj słowa kluczowe projektu
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Wydrukuj komentarze do projektu
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Wydrukuj datę utworzenia projektu
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Wydrukuj słowa kluczowe projektu (ponownie)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Wydrukuj ostatnią wydrukowaną datę projektu
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Wniosek
tym samouczku omówiliśmy, jak pisać podsumowania projektów MPP przy użyciu Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie ustawiać i pobierać różne informacje podsumowujące o plikach projektu. Aspose.Tasks upraszcza proces pracy z plikami Microsoft Project w aplikacjach Java, oferując solidną funkcjonalność i łatwość użycia.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?
O: Tak, Aspose.Tasks for Java można bezproblemowo zintegrować z innymi bibliotekami Java, aby zwiększyć możliwości zarządzania projektami.
### P: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Jak często jest aktualizowany Aspose.Tasks dla Java?
Odp.: Aspose.Tasks for Java jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami plików Java i Microsoft Project.
### P: Czy mogę bardziej dostosować informacje podsumowujące projekt?
O: Oczywiście, Aspose.Tasks dla Java zapewnia szerokie możliwości dostosowywania informacji podsumowujących projekt zgodnie z Twoimi konkretnymi wymaganiami.
### P: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).