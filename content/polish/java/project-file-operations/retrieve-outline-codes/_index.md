---
title: Pobierz kody konspektu projektu MS w Aspose.Tasks
linktitle: Pobierz kody konspektu w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak programowo pobierać kody konspektu programu Microsoft Project przy użyciu Aspose.Tasks dla języka Java. Zwiększ swoje możliwości zarządzania projektami.
type: docs
weight: 15
url: /pl/java/project-file-operations/retrieve-outline-codes/
---
## Wstęp
tym samouczku nauczymy się pobierać kody konspektu programu Microsoft Project za pomocą Aspose.Tasks dla Java. Kody konspektu w programie MS Project zapewniają ustrukturyzowany sposób kategoryzowania i organizowania zadań, zasobów i przydziałów projektu. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom programowe manipulowanie plikami Microsoft Project i zarządzanie nimi.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
### 1. Środowisko programistyczne Java
Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK). Możesz pobrać i zainstalować JDK ze strony internetowej Oracle.
### 2. Biblioteka Aspose.Tasks
 Pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu Java. Bibliotekę można pobrać ze strony[Aspose.Tasks dla strony pobierania Java](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety z Aspose.Tasks do swojego kodu Java:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Podzielmy teraz podany przykładowy kod na kilka kroków:
## Krok 1: Załaduj projekt
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
 W tym kroku ładujemy plik Microsoft Project do pliku`Project` obiekt przy użyciu podanej nazwy pliku.
## Krok 2: Pobierz kody konspektu
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
Wykonujemy iterację przez każdą definicję kodu konspektu w projekcie.
## Krok 3: Uzyskaj dostęp do właściwości kodu konspektu
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
Pobieramy i drukujemy różne właściwości definicji kodu konspektu, takie jak alias, identyfikator pola i nazwa pola.
## Krok 4: Sprawdź niestandardowy kod przedsiębiorstwa
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
Sprawdzamy, czy kod konspektu jest kodem niestandardowym przedsiębiorstwa i odpowiednio drukujemy wynik.
## Krok 5: Wyświetl maski kodu konspektu
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
Wykonujemy iterację po każdej masce powiązanej z kodem konspektu i drukujemy jej poziom i wartość maski.
## Krok 6: Wyświetl wartości kodu konspektu
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
Wykonujemy iterację po każdej wartości kodu konspektu i drukujemy jej opis, identyfikator wartości, wartość i typ.
## Wniosek
W tym samouczku nauczyliśmy się, jak pobierać kody konspektu MS Project za pomocą Aspose.Tasks dla Java. Wykonując podane kroki, możesz efektywnie uzyskiwać dostęp do kodów konspektu i manipulować nimi w aplikacjach Java, umożliwiając zaawansowane możliwości zarządzania projektami.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Tasks dla Java do modyfikowania kodów konspektu w pliku projektu?
O: Tak, Aspose.Tasks dla Java udostępnia interfejsy API umożliwiające programową modyfikację kodów konspektu w plikach MS Project.
### P2: Czy dostępna jest wersja próbna Aspose.Tasks dla Java?
 O: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks dla Java ze strony[Witryna Aspose.Tasks](https://releases.aspose.com/).
### P3: Jak mogę uzyskać pomoc techniczną dla Aspose.Tasks dla Java?
 Odp.: Możesz uzyskać pomoc techniczną, odwiedzając witrynę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) i zamieszczanie tam swoich zapytań.
### P4: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Java?
 O: Tak, możesz kupić tymczasową licencję na Aspose.Tasks dla Java w witrynie[strona zakupu](https://purchase.aspose.com/temporary-license/).
### P5: Gdzie mogę znaleźć pełną dokumentację Aspose.Tasks dla Java?
 Odp.: Możesz odwołać się do[dokumentacja](https://reference.aspose.com/tasks/java/) aby uzyskać szczegółowe informacje na temat korzystania z Aspose.Tasks dla Java.