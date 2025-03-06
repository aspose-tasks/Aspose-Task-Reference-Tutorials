---
title: Skonfiguruj widok wykresu Gantta w projektach Aspose.Tasks
linktitle: Skonfiguruj widok wykresu Gantta w projektach Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak skonfigurować widok wykresu projektu Gantt MS Project w Aspose.Tasks przy użyciu języka Java. Dostosuj projekt i wizualizuj go na wykresie Gantta krok po kroku.
weight: 10
url: /pl/java/project-configuration/configure-gantt-chart/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skonfiguruj widok wykresu Gantta w projektach Aspose.Tasks

## Wstęp
W tym samouczku dowiesz się, jak skonfigurować widok wykresu Gantta MS Project w projektach Aspose.Tasks przy użyciu języka Java. Aspose.Tasks to potężny interfejs API Java, który umożliwia programową pracę z plikami Microsoft Project. Wykonując poniższe kroki, będziesz mógł dostosować widok wykresu Gantta do wymagań swojego projektu.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java.
2.  Biblioteka Aspose.Tasks: Pobierz i zainstaluj bibliotekę Aspose.Tasks. Można go pobrać z[Tutaj](https://releases.aspose.com/tasks/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz wybrane IDE. W tym samouczku wykorzystano IntelliJ IDEA, ale możesz użyć dowolnego IDE, z którym czujesz się komfortowo.
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do pracy z Aspose.Tasks w swoim projekcie Java. Dodaj następujące instrukcje importu do pliku Java:
```java
import com.aspose.tasks.*;
```
Podzielmy teraz proces konfigurowania widoku wykresu projektu Gantt MS Project na instrukcje krok po kroku:
## Krok 1: Skonfiguruj katalog danych
```java
String dataDir = "Your Data Directory";
```
 Zastępować`"Your Data Directory"` ze ścieżką do katalogu danych projektu.
## Krok 2: Załaduj plik projektu
```java
Project project = new Project(dataDir + "project.mpp");
```
Załaduj plik projektu (`project.mpp` w tym przykładzie) za pomocą`Project` klasa z Aspose.Tasks.
## Krok 3: Dodaj nową aktywność
```java
Task task = project.getRootTask().getChildren().add("New Activity");
```
 Utwórz nowe zadanie w swoim projekcie za pomocą pliku`Task` class i dodaj ją do elementów podrzędnych zadania głównego.
## Krok 4: Zdefiniuj atrybut niestandardowy
```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```
 Zdefiniuj nowy atrybut niestandardowy za pomocą`ExtendedAttributeDefinition`class i dodaj ją do rozszerzonych atrybutów projektu.
## Krok 5: Dodaj niestandardowy atrybut do zadania
```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```
 Dodaj atrybut niestandardowy do utworzonego zadania za pomocą`createExtendedAttribute` metoda.
## Krok 6: Dostosuj tabelę
```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```
Dostosuj tabelę, dodając pole atrybutu tekstowego o określonej szerokości, tytule i wyrównaniu.
## Krok 7: Zapisz projekt
```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```
Zapisz projekt ze skonfigurowanym widokiem wykresu projektu Gantt MS. Powstały plik można otworzyć w programie Microsoft Project 2010.
## Wniosek
Gratulacje! Pomyślnie skonfigurowałeś widok wykresu projektu Gantt MS w projektach Aspose.Tasks przy użyciu języka Java. Możesz teraz dostosować atrybuty projektu i wizualizować je na wykresie Gantta zgodnie z potrzebami projektu.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Tasks z innymi językami programowania?
Odp.: Tak, Aspose.Tasks jest dostępny dla wielu języków programowania, w tym .NET, Java i C++.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?
 Odp.: Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### P: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?
O: Możesz znaleźć wsparcie i zadawać pytania na stronie[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).
### P: Jak mogę kupić licencję na Aspose.Tasks?
 Odpowiedź: Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy).
### P: Czy potrzebuję tymczasowej licencji do celów testowych?
 Odpowiedź: Tak, możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
