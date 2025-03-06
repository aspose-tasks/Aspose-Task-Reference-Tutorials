---
title: Przeczytaj właściwości waluty w projektach Aspose.Tasks
linktitle: Przeczytaj właściwości waluty w projektach Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak wyodrębnić informacje o walutach z plików MS Project przy użyciu Aspose.Tasks dla Java. Dostarczono przewodnik krok po kroku.
weight: 10
url: /pl/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przeczytaj właściwości waluty w projektach Aspose.Tasks

## Wstęp
tym samouczku dowiemy się, jak wykorzystać Aspose.Tasks dla Java do odczytu właściwości waluty z plików Microsoft Project. Aspose.Tasks to potężny interfejs API języka Java, który umożliwia programistom manipulowanie dokumentami programu Microsoft Project bez konieczności instalowania programu Microsoft Project. Wykonując czynności opisane poniżej, będziesz mógł bez wysiłku wyodrębnić informacje związane z walutą.
## Warunki wstępne
Przed kontynuowaniem tego samouczka upewnij się, że spełnione są następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie.
2.  Aspose.Tasks for Java JAR: Pobierz bibliotekę Aspose.Tasks for Java ze strony[Tutaj](https://releases.aspose.com/tasks/java/) i dołącz go do swojego projektu Java.
## Importuj pakiety
Rozpocznij od zaimportowania niezbędnych pakietów do klasy Java:
```java
import com.aspose.tasks.*;
```
## Krok 1: Skonfiguruj katalog projektu
Najpierw skonfiguruj katalog projektu, w którym znajduje się plik Microsoft Project. Możesz zdefiniować tę ścieżkę katalogu w następujący sposób:
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` z rzeczywistą ścieżką do katalogu projektu.
## Krok 2: Utwórz instancję czytnika projektu
 Utwórz instancję a`Project` obiekt, podając ścieżkę do pliku Microsoft Project:
```java
Project project = new Project(dataDir + "project.mpp");
```
 Pamiętaj o wymianie`"project.mpp"` z nazwą pliku MS Project.
## Krok 3: Wyświetl właściwości waluty
Pobierz i wyświetl właściwości waluty z pliku projektu:
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
Ten segment kodu pobiera informacje, takie jak kod waluty, cyfry, symbol i pozycja symbolu z pliku MS Project i drukuje je na konsoli.
## Krok 4: Zakończenie procesu
Na koniec wydrukuj komunikat informujący o pomyślnym zakończeniu procesu:
```java
System.out.println("Process completed Successfully");
```
## Wniosek
W tym samouczku omówiliśmy, jak czytać właściwości waluty z plików Microsoft Project za pomocą Aspose.Tasks dla Java. Wykonując opisane kroki, możesz bez wysiłku programowo wyodrębnić informacje dotyczące walut z plików projektu, umożliwiając bezproblemową integrację z aplikacjami Java.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks obsługuje różne wersje Microsoft Project, w tym pliki MPP wygenerowane przez MS Project 2003-2021.
### P: Czy mogę modyfikować właściwości waluty za pomocą Aspose.Tasks?
O: Tak, Aspose.Tasks umożliwia programowe odczytywanie i modyfikowanie właściwości walut w plikach MS Project.
### P: Czy Aspose.Tasks nadaje się do użytku komercyjnego?
 O: Tak, Aspose.Tasks to biblioteka komercyjna przeznaczona do użytku profesjonalnego. Możesz kupić licencję[Tutaj](https://purchase.aspose.com/buy).
### P: Czy Aspose.Tasks oferuje bezpłatną wersję próbną?
 Odp.: Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.Tasks z[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę szukać pomocy lub wsparcia dla Aspose.Tasks?
 O: Możesz odwiedzić forum Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub pytań.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
