---
title: Konwertuj MS Project na SVG w Javie
linktitle: Zapisz jako SVG w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak zapisywać pliki Microsoft Project jako SVG w Javie przy użyciu biblioteki Aspose.Tasks. Przewodnik krok po kroku z przykładami kodu.
weight: 18
url: /pl/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj MS Project na SVG w Javie

## Wstęp
Aspose.Tasks dla Java to potężna biblioteka do pracy z plikami zarządzania projektami, umożliwiająca programistom manipulowanie danymi projektu, wykonywanie różnych operacji i wydajne generowanie raportów. W tym samouczku dowiemy się, jak zapisać projekt w formacie SVG przy użyciu Aspose.Tasks dla Java. SVG (Scalable Vector Graphics) to szeroko stosowany format wyświetlania grafiki wektorowej w Internecie, zapewniający skalowalność i wysoką jakość renderowania.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
### Środowisko programistyczne Java
Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK). Możesz pobrać i zainstalować JDK ze strony internetowej Oracle.
### Aspose.Tasks dla biblioteki Java
 Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java ze strony internetowej. Link do pobrania można znaleźć w dostarczonej dokumentacji[Tutaj](https://releases.aspose.com/tasks/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego programu Java, aby móc pracować z funkcjonalnościami Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Podzielmy teraz podany przykład na kilka kroków:
## Krok 2: Zdefiniuj katalog danych
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"`ze ścieżką do katalogu, w którym znajduje się plik projektu.
## Krok 3: Załaduj plik projektu
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ten krok ładuje plik projektu o nazwie „HomeMovePlan.mpp” z określonego katalogu danych.
## Krok 4: Zapisz jako SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
Ten krok zapisuje załadowany projekt w formacie SVG pod nazwą „project5.svg” w określonym katalogu danych.

## Wniosek
W tym samouczku nauczyliśmy się, jak zapisać projekt w formacie SVG przy użyciu Aspose.Tasks dla Java. Postępując zgodnie z podanymi krokami, możesz efektywnie przekonwertować pliki projektu do formatu SVG, umożliwiając bezproblemową integrację z aplikacjami internetowymi lub narzędziami do wizualizacji.
## Często zadawane pytania
### Czy Aspose.Tasks for Java jest kompatybilny ze wszystkimi wersjami plików Microsoft Project?
Tak, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### Czy mogę dostosować wygląd wyjścia SVG?
Tak, możesz dostosować wygląd pliku wyjściowego SVG, dostosowując parametry, takie jak czcionki, kolory i konfiguracje układu.
### Czy Aspose.Tasks dla Java wymaga licencji do użytku komercyjnego?
 Tak, do komercyjnego wykorzystania Aspose.Tasks dla Java wymagana jest ważna licencja. Licencję można uzyskać ze strony internetowej[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy mogę wypróbować Aspose.Tasks dla Java przed zakupem?
 Tak, możesz poprosić o bezpłatną wersję próbną Aspose.Tasks dla Java ze strony internetowej[Tutaj](https://purchase.aspose.com/buy) ocenić jego cechy i możliwości.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Tasks dla Java?
 Możesz uzyskać pomoc dotyczącą Aspose.Tasks dla Java, odwiedzając forum[Tutaj](https://forum.aspose.com/c/tasks/15), gdzie możesz zadawać pytania i kontaktować się ze społecznością.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
