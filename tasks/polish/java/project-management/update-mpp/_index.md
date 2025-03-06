---
title: Zaktualizuj plik MPP w Aspose.Tasks
linktitle: Zaktualizuj plik MPP w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak bezproblemowo aktualizować pliki MPP za pomocą Aspose.Tasks dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby efektywnie manipulować plikami projektu.
weight: 19
url: /pl/java/project-management/update-mpp/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zaktualizuj plik MPP w Aspose.Tasks

## Wstęp
W zarządzaniu projektami obsługa i aktualizacja plików projektowych jest zadaniem kluczowym. Aspose.Tasks dla Java zapewnia programistom Java potężne rozwiązanie do płynnego manipulowania plikami Microsoft Project. W tym samouczku zajmiemy się aktualizacją plików MPP za pomocą Aspose.Tasks dla Java.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że posiadasz następujące elementy:
1. Środowisko programistyczne Java: Upewnij się, że masz zainstalowaną Javę w swoim systemie.
2.  Aspose.Tasks dla Java: Pobierz i zainstaluj Aspose.Tasks dla Java z[strona pobierania](https://releases.aspose.com/tasks/java/).
3. Podstawowa znajomość języka Java: Konieczna jest znajomość języka programowania Java, aby postępować zgodnie z przykładami.

## Importuj pakiety
Po pierwsze, musisz zaimportować niezbędne pakiety do swojego projektu Java, aby efektywnie wykorzystać funkcjonalności Aspose.Tasks.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
Ta linia kodu importuje wszystkie niezbędne klasy i metody z biblioteki Aspose.Tasks, umożliwiając bezproblemową pracę z plikami Microsoft Project.

Teraz podzielmy proces aktualizacji pliku MPP przy użyciu Aspose.Tasks dla Java na łatwe do wykonania kroki.
## Krok 2: Zdefiniuj katalog danych
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` z rzeczywistą ścieżką, w której znajduje się plik MPP.
## Krok 3: Przeczytaj istniejący projekt
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
 Ten kod odczytuje istniejący plik projektu MPP o nazwie`SampleMSP2010.mpp` z określonego katalogu danych.
## Krok 4: Utwórz nowe zadanie
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
Tutaj dodajemy nowe zadanie o nazwie „Zadanie 1” do zadania głównego projektu.
## Krok 5: Ustaw daty rozpoczęcia i zakończenia
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
Te linie kodu ustawiają datę rozpoczęcia i datę zakończenia nowo utworzonego zadania.
## Krok 6: Zapisz projekt
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
 Na koniec ten krok zapisuje zaktualizowany projekt z nowo dodanym zadaniem do nowego pliku MPP o nazwie`AfterLinking.mpp`.

## Wniosek
tym samouczku omówiliśmy, jak aktualizować pliki MPP za pomocą Aspose.Tasks dla Java. Postępując zgodnie z przewodnikiem krok po kroku, możesz efektywnie manipulować plikami Microsoft Project w aplikacjach Java.
## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje złożone struktury projektów?
O: Tak, Aspose.Tasks dla Java zapewnia solidne funkcje umożliwiające efektywną obsługę złożonych struktur projektów.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks dla Java?
 O: Tak, możesz pobrać bezpłatną wersję próbną ze strony[strona internetowa](https://releases.aspose.com/).
### P: Czy Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project?
O: Oczywiście, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### P: Czy mogę uzyskać tymczasowe licencje na Aspose.Tasks dla Java?
 Odpowiedź: Tak, do celów testowych dostępne są licencje tymczasowe. Można je otrzymać od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
### P: Gdzie mogę szukać pomocy lub wsparcia dotyczącego Aspose.Tasks dla Java?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub pytań.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
