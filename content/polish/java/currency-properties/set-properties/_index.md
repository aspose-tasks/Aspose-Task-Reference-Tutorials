---
title: Ustaw właściwości waluty w projektach Aspose.Tasks
linktitle: Ustaw właściwości waluty w projektach Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak ustawić właściwości waluty w projektach Aspose.Tasks przy użyciu języka Java. Bez wysiłku manipuluj plikami Microsoft Project.
type: docs
weight: 11
url: /pl/java/currency-properties/set-properties/
---
## Wstęp
W tym samouczku przyjrzymy się, jak ustawić właściwości waluty w projektach Aspose.Tasks przy użyciu języka Java. Aspose.Tasks to potężna biblioteka Java, która umożliwia programistom programowe manipulowanie plikami Microsoft Project.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Tasks for Java Library: Pobierz i zainstaluj bibliotekę Aspose.Tasks for Java z pliku[link do pobrania](https://releases.aspose.com/tasks/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko IDE, takie jak Eclipse lub IntelliJ IDEA.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do pracy z Aspose.Tasks w Javie.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## Krok 1: Ustaw katalog danych
Ustaw katalog danych, w którym znajdują się pliki projektu.
```java
String dataDir = "Your Data Directory";
```
## Krok 2: Utwórz instancję projektu
Utwórz nową instancję projektu za pomocą Aspose.Tasks.
```java
Project project = new Project();
```
## Krok 3: Ustaw właściwości waluty
Teraz ustawmy właściwości waluty projektu.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Krok 4: Zapisz projekt
Zapisz projekt ze zaktualizowanymi właściwościami waluty.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Krok 5: Wyświetl komunikat o zakończeniu
Wyświetl komunikat informujący o pomyślnym zakończeniu procesu.
```java
System.out.println("Process completed Successfully");
```
Gratulacje! Pomyślnie ustawiłeś właściwości waluty w projekcie Aspose.Tasks przy użyciu języka Java.
## Wniosek
W tym samouczku nauczyliśmy się używać Aspose.Tasks dla Java do ustawiania właściwości waluty w plikach projektu. Dzięki Aspose.Tasks programiści mogą efektywnie manipulować danymi projektu, co czyni go cennym narzędziem w aplikacjach do zarządzania projektami.
## Często zadawane pytania
### Czy mogę ustawić wiele walut w jednym projekcie za pomocą Aspose.Tasks?
Tak, Aspose.Tasks umożliwia obsługę wielu walut w jednym pliku projektu.
### Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?
Tak, Aspose.Tasks obsługuje różne wersje plików Microsoft Project, zapewniając kompatybilność w różnych środowiskach.
### Czy Aspose.Tasks zapewnia obsługę niestandardowych formatów walut?
Absolutnie Aspose.Tasks oferuje elastyczność w definiowaniu niestandardowych formatów walut w celu spełnienia określonych wymagań projektu.
### Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami lub frameworkami Java?
Tak, Aspose.Tasks można bezproblemowo zintegrować z innymi bibliotekami i frameworkami Java, zwiększając jego funkcjonalność i wszechstronność.
### Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dla Aspose.Tasks?
 Aby uzyskać dodatkowe wsparcie, możesz odwiedzić stronę[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), gdzie możesz znaleźć przydatne zasoby i nawiązać kontakt ze społecznością.