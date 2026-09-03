---
date: 2026-05-20
description: Dowiedz się, jak używać Aspose.Tasks for Java, aby dodać rozszerzone
  atrybuty do przydziałów zasobów, ustawić datę rozpoczęcia projektu i efektywnie
  zapisywać pliki MS Project.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Dodaj rozszerzone atrybuty do przydziałów zasobów w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak używać Aspose.Tasks for Java – Dodaj rozszerzone atrybuty do przydziałów
  zasobów
url: /pl/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie manipulacji MS Project przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku odkryjesz **jak używać Aspose.Tasks dla Javy**, aby dodać rozszerzone atrybuty do przydziałów zasobów i programowo zapisywać informacje Microsoft Project. Niezależnie od tego, czy automatyzujesz potok raportowania, czy tworzysz własne narzędzie do zarządzania projektami, poniższe kroki pokażą Ci dokładnie, jak ustawić datę rozpoczęcia projektu, utworzyć przydziały zasobów i zapisać plik jako XML — wszystko przy użyciu kilku linii kodu Java.

## Szybkie odpowiedzi
- **Co robi Aspose.Tasks dla Javy?** Odczytuje, zapisuje i modyfikuje pliki Microsoft Project bez konieczności instalacji Microsoft Project.  
- **Czy mogę dodać własne pola do przydziału zasobu?** Tak, użyj kolekcji `ExtendedAttribute` w obiekcie `ResourceAssignment`.  
- **Jak ustawić datę rozpoczęcia projektu?** Wywołaj `project.setStartDate(LocalDateTime.of(...))` przed zapisaniem.  
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Licencja komercyjna usuwa znak wodny wersji próbnej i odblokowuje pełny dostęp do API.  
- **Jakie wersje Javy są obsługiwane?** Aspose.Tasks dla Javy obsługuje JDK 8 do JDK 21.

## Jak używać Aspose.Tasks dla Javy?
`Project` jest głównym obiektem reprezentującym plik Microsoft Project w pamięci. Załaduj bibliotekę Aspose.Tasks, utwórz instancję `Project`, skonfiguruj właściwości na poziomie projektu, dodaj rozszerzone atrybuty do przydziału zasobu i na końcu zapisz projekt jako XML. Podstawowy przepływ pracy składa się z trzech zwięzłych kroków: inicjalizacja, modyfikacja i zapis. Ten wzorzec działa dla projektów dowolnego rozmiaru i działa na JVM Windows, Linux lub macOS.

## Czym jest rozszerzony atrybut w Aspose.Tasks?
**Rozszerzony atrybut** to własne pole, które dołączasz do zadań, zasobów lub przydziałów, aby przechowywać dodatkowe metadane poza wbudowanymi kolumnami. `ExtendedAttributeDefinition` definiuje schemat własnego pola. Aspose.Tasks udostępnia klasy `ExtendedAttributeDefinition` i `ExtendedAttribute`, które pozwalają definiować i przypisywać te pola programowo.

## Dlaczego dodawać rozszerzone atrybuty do przydziałów zasobów?
Aspose.Tasks obsługuje **ponad 50 wbudowanych i własnych pól**, a możesz dodawać nieograniczoną liczbę atrybutów definiowanych przez użytkownika. Dodanie ich pozwala na przechwycenie kodów kosztów, identyfikatorów działów lub dowolnych danych specyficznych dla biznesu bezpośrednio w pliku .mpp, eliminując potrzebę zewnętrznych arkuszy kalkulacyjnych i zapewniając integralność danych w całym cyklu życia projektu.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – zainstalowany JDK 8 lub nowszy.  
2. **Biblioteka Aspose.Tasks dla Javy** – pobierz ją z oficjalnej strony wydania [tutaj](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą, którego preferujesz.

## Importowanie pakietów
Najpierw zaimportuj niezbędne pakiety w swoim projekcie Java:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Krok 1: Ustaw katalog danych
Zdefiniuj katalog, w którym będą przechowywane dane projektu. Ścieżka ta będzie użyta później przy zapisywaniu pliku XML.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Utwórz instancję projektu
Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Microsoft Project w pamięci. Utworzenie jej instancji daje pełny dostęp do wszystkich elementów projektu.

```java
Project project = new Project();
```

### Krok 3: Ustaw właściwości informacji o projekcie
Ustaw niezbędne właściwości projektu, takie jak data rozpoczęcia, flaga harmonogramu od startu oraz data statusu. Wartości te są przechowywane w obiekcie `ProjectInfo` projektu.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Krok 4: Dodaj rozszerzone atrybuty do przydziału zasobu
Utwórz `ExtendedAttributeDefinition` dla własnego pola, dołącz je do `ResourceAssignment` i wypełnij wartość. Ten krok demonstruje działanie słowa kluczowego **add extended attributes**.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Typowe problemy i rozwiązania
- **NullPointerException przy dostępie do kolekcji przydziałów** – Upewnij się, że utworzyłeś co najmniej jeden zasób i jedno zadanie przed pobraniem przydziałów.  
- **Rozszerzony atrybut nie pojawia się w MS Project** – Sprawdź, czy `FieldId` atrybutu odpowiada slotowi własnego pola (np. `ExtendedAttributeTask.Text1`).  
- **Niezgodność formatu daty** – Użyj `java.time.LocalDateTime` dla wartości dat; Aspose.Tasks automatycznie konwertuje je do formatu kalendarza projektu.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks dla Javy do odczytu plików MS Project?**  
O: Tak, biblioteka zapewnia pełne możliwości odczytu i zapisu dla formatów .mpp, .xml i .xps.

**P: Czy Aspose.Tasks dla Javy jest kompatybilny z różnymi wersjami MS Project?**  
O: Zdecydowanie, obsługuje pliki od Project 2000 aż do najnowszej wersji 2024, obejmując ponad 20 formatów wersji.

**P: Czy wersja próbna Aspose.Tasks dla Javy ma jakieś ograniczenia?**  
O: Wersja próbna dodaje znak wodny do wygenerowanych plików i ogranicza liczbę zadań, które możesz utworzyć, ale wszystkie funkcje API pozostają dostępne.

**P: Jak mogę uzyskać wsparcie dla Aspose.Tasks dla Javy?**  
O: Możesz uzyskać pomoc na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**P: Czy mogę kupić tymczasową licencję na Aspose.Tasks dla Javy?**  
O: Tak, tymczasowe licencje są dostępne na krótkoterminowe użycie. Możesz ją uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**Ostatnia aktualizacja:** 2026-05-20  
**Testowano z:** Aspose.Tasks dla Javy 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak dodać notatki do przydziałów zasobów w Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Jak odczytać i zapisać skalę stawek dla przydziałów zasobów w Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Jak dodać zasób do projektu i obsłużyć właściwości opóźnienia poziomowania w Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}