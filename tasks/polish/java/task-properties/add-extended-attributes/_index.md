---
title: Dodaj rozszerzone atrybuty do zadań w Aspose.Tasks
linktitle: Dodaj rozszerzone atrybuty do zadań w Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Odkryj moc Aspose.Tasks Java w dostosowywaniu plików Microsoft Project z rozszerzonymi atrybutami. Bez wysiłku zwiększ swoje możliwości zarządzania projektami.
weight: 11
url: /pl/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj rozszerzone atrybuty do zadań w Aspose.Tasks

## Wstęp
Poprawa możliwości zarządzania projektami ma kluczowe znaczenie dla skutecznego śledzenia zadań i zarządzania zasobami. Aspose.Tasks dla Java zapewnia programistom Java potężne rozwiązanie do płynnego manipulowania plikami Microsoft Project. W tym samouczku omówimy, jak dodawać rozszerzone atrybuty do zadań za pomocą Aspose.Tasks dla Java, umożliwiając dostosowywanie i organizowanie danych projektu zgodnie z konkretnymi wymaganiami.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
-  Zainstalowana biblioteka Aspose.Tasks dla Java. Można go pobrać z[strona internetowa](https://releases.aspose.com/tasks/java/).
- Zintegrowane środowisko programistyczne Java (IDE) zainstalowane w systemie.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety, aby uzyskać dostęp do funkcjonalności Aspose.Tasks:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
Teraz podzielmy każdy przykład na wiele kroków:
## 1. Dodawanie atrybutu zwykłego tekstu
1. Ustaw ścieżkę katalogu dokumentu:
```java
String dataDir = "Your Document Directory";
```
2. Utwórz nowy projekt:
```java
Project project = new Project(dataDir + "project.mpp");
```
3. Utwórz rozszerzoną definicję atrybutu typu Text1:
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. Dodaj definicję do kolekcji Extended Attributes projektu:
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. Dodaj zadanie do projektu:
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. Utwórz rozszerzony atrybut na podstawie definicji atrybutu:
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. Przypisz wartość do wygenerowanego atrybutu rozszerzonego:
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. Dodaj atrybut rozszerzony do zadania:
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. Zapisz projekt:
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. Dodawanie atrybutu tekstowego z opcją wyszukiwania
Wykonaj te same kroki, co powyżej, zastępując Tekst1 Tekstem2 i dostosowując wartości wyszukiwania.
## 3. Dodawanie atrybutu czasu trwania z opcją wyszukiwania
Wykonaj te same kroki, co powyżej, zastępując Tekst1 czasem trwania2 i dostosowując wartości wyszukiwania.
## Wniosek
Postępując zgodnie z tym przewodnikiem krok po kroku, nauczyłeś się wykorzystywać Aspose.Tasks dla języka Java do dodawania rozszerzonych atrybutów do zadań w plikach programu Microsoft Project. To dostosowanie pozwala dostosować podejście do zarządzania projektami, zwiększając elastyczność i wydajność.
## Często Zadawane Pytania
### P: Czy mogę używać Aspose.Tasks for Java z innymi bibliotekami Java?
O: Tak, Aspose.Tasks for Java można bezproblemowo zintegrować z projektami Java i dobrze współpracuje z innymi bibliotekami Java.
### P: Czy Aspose.Tasks dla Java nadaje się do aplikacji do zarządzania projektami na dużą skalę?
O: Oczywiście, Aspose.Tasks dla Java jest przeznaczony do obsługi projektów o różnej wielkości, w tym aplikacji na dużą skalę.
### P: Czy istnieją jakieś uwagi licencyjne dotyczące używania Aspose.Tasks dla Java w projekcie komercyjnym?
 Odpowiedź: Tak, pamiętaj o zapoznaniu się z informacjami licencyjnymi podanymi na stronie[Witryna Aspose.Tasks](https://purchase.aspose.com/buy).
### P: Jak mogę uzyskać wsparcie lub pomoc dotyczącą Aspose.Tasks dla Java?
 O: Odwiedź[Forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) za wsparcie społeczności i dyskusje.
### P: Czy mogę wypróbować Aspose.Tasks dla Java przed zakupem?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
