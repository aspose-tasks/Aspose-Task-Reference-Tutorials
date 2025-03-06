---
title: Obsługa funkcji oceny w formułach Aspose.Tasks
linktitle: Obsługa funkcji oceny w formułach Aspose.Tasks
second_title: Aspose.Tasks API Java
description: Dowiedz się, jak wspierać ocenę funkcji MS Project w formułach Aspose.Tasks przy użyciu języka Java. Zwiększ swoją produktywność dzięki Aspose.Tasks.
type: docs
weight: 10
url: /pl/java/formulas/evaluation-functions/
---

## Wstęp
Aspose.Tasks dla Java to potężna biblioteka, która umożliwia programistom programowe manipulowanie plikami Microsoft Project. Jedną z jego kluczowych funkcji jest możliwość obsługi ewaluacji funkcji MS Project w ramach formuł Aspose.Tasks. Ta funkcja umożliwia użytkownikom wykonywanie złożonych obliczeń i analiz bezpośrednio w aplikacjach Java.
## Warunki wstępne
Zanim zaczniesz integrować funkcje MS Project z formułami Aspose.Tasks, upewnij się, że posiadasz następujące elementy:
1. Środowisko programistyczne Java: Upewnij się, że w systemie zainstalowana jest Java wraz ze zgodnym środowiskiem IDE do programowania w języku Java, takim jak IntelliJ IDEA lub Eclipse.
2.  Biblioteka Aspose.Tasks for Java: Pobierz i dołącz bibliotekę Aspose.Tasks for Java do swojego projektu Java. Można go pobrać z[Strona pobierania Aspose.Tasks dla Java](https://releases.aspose.com/tasks/java/).
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojej klasy Java, aby móc korzystać z funkcjonalności Aspose.Tasks:
```java
import com.aspose.tasks.*;
```

## Krok 1: Utwórz nowy obiekt projektu
 Najpierw utwórz nowy`Project`obiekt do pracy:
```java
Project project = new Project();
```
Spowoduje to inicjowanie nowego pustego projektu.
## Krok 2: Zdefiniuj rozszerzony atrybut zadań
Następnie zdefiniuj rozszerzony atrybut dla zadań. Ten atrybut będzie przechowywać niestandardowe dane powiązane z zadaniami:
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
 Tutaj tworzymy rozszerzony atrybut typu`Number` z nazwą „Sine” dla zadań.
## Krok 3: Dodaj atrybut rozszerzony do projektu
Dodaj rozszerzoną definicję atrybutu do listy rozszerzonych atrybutów projektu:
```java
project.getExtendedAttributes().add(attr);
```
Spowoduje to dodanie atrybutu niestandardowego do projektu.
## Krok 4: Utwórz nowe zadanie
Utwórzmy teraz nowe zadanie w projekcie:
```java
Task task = project.getRootTask().getChildren().add("Task");
```
Spowoduje to dodanie do projektu nowego zadania o nazwie „Zadanie”.
## Krok 5: Powiąż atrybut rozszerzony z zadaniem
Powiąż utworzony wcześniej rozszerzony atrybut z zadaniem:
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
Spowoduje to powiązanie rozszerzonego atrybutu „Sine” z zadaniem.

## Wniosek
Podsumowując, integracja funkcji MS Project z formułami Aspose.Tasks w Javie jest prostym procesem. Wykonując podane kroki, możesz efektywnie wykorzystać potężne możliwości Aspose.Tasks dla Java do programowego manipulowania i analizowania plików Microsoft Project.
## Często zadawane pytania
### P: Czy Aspose.Tasks for Java obsługuje złożone formuły MS Project?
O: Tak, Aspose.Tasks for Java obsługuje ocenę szerokiego zakresu funkcji MS Project, umożliwiając wykonywanie złożonych obliczeń w aplikacjach Java.
### P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami plików Microsoft Project?
O: Tak, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.
### P: Czy mogę wypróbować Aspose.Tasks dla Java przed zakupem?
 O: Tak, możesz pobrać bezpłatną wersję próbną Aspose.Tasks dla Java ze strony internetowej[Tutaj](https://purchase.aspose.com/buy).
### P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Java?
Odp.: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks[Tutaj](https://forum.aspose.com/c/tasks/15).
### P: Czy dostępna jest tymczasowa licencja na Aspose.Tasks dla Java?
 Odp.: Tak, możesz uzyskać tymczasową licencję do celów testowych ze strony internetowej Aspose[Tutaj](https://purchase.aspose.com/temporary-license/).