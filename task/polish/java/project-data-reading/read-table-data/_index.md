---
title: Odczytaj dane tabeli z pliku w Aspose.Tasks
linktitle: Odczytaj dane tabeli z pliku w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Odblokuj moc Aspose.Tasks dla Java. Z tego obszernego samouczka dowiesz się, jak wyodrębniać dane z tabeli z plików.
type: docs
weight: 17
url: /pl/java/project-data-reading/read-table-data/
---
## Wstęp
tym samouczku przyjrzymy się, jak odczytać dane tabeli z pliku za pomocą Aspose.Tasks dla Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom programową pracę z dokumentami Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK. Można go pobrać i zainstalować ze strony internetowej Oracle.
2.  Plik JAR Aspose.Tasks for Java: Pobierz bibliotekę Aspose.Tasks for Java z witryny[link do pobrania](https://releases.aspose.com/tasks/java/) i dołącz go do swojego projektu Java.

## Importuj pakiety
Zaimportuj niezbędne pakiety do pracy z Aspose.Tasks w swoim projekcie Java:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## Krok 1: Skonfiguruj katalog danych
Zdefiniuj ścieżkę do katalogu, w którym znajduje się plik projektu:
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` z rzeczywistą ścieżką do katalogu danych.
## Krok 2: Załaduj plik projektu
Załaduj plik projektu za pomocą Aspose.Tasks:
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
 Pamiętaj o wymianie`"Project2003.mpp"` z nazwą pliku projektu.
## Krok 3: Pobierz informacje o tabeli
Pobierz tabelę z projektu i wykonaj iterację po jej polach:
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
Ten fragment kodu pobiera informacje o polach tabeli, takie jak szerokość, tytuł i wyrównanie.

## Wniosek
tym samouczku nauczyliśmy się czytać dane tabeli z pliku za pomocą Aspose.Tasks dla Java. Wykonując poniższe kroki, możesz efektywnie wyodrębniać dane z dokumentów Microsoft Project i manipulować nimi w aplikacjach Java.
## Często zadawane pytania
### P: Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?
Odp.: Aspose.Tasks obsługuje różne wersje Microsoft Project, w tym Project 2003, 2007, 2010, 2013 i 2016.
### P: Czy mogę zmodyfikować dane tabeli i zapisać je z powrotem w pliku projektu?
O: Tak, możesz użyć Aspose.Tasks do programowej modyfikacji danych tabeli i zapisania zmian w oryginalnym pliku projektu.
### P: Czy Aspose.Tasks wymaga osobnej licencji do użytku komercyjnego?
 Odp.: Tak, musisz kupić licencję na Aspose.Tasks, jeśli zamierzasz używać go w środowisku komercyjnym. Licencję można uzyskać od firmy[strona zakupu](https://purchase.aspose.com/buy).
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks z[strona z wydaniami](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć pomoc i wsparcie dla Aspose.Tasks?
 O: Możesz odwiedzić[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15)za pomoc i wsparcie ze strony społeczności i zespołu Aspose.