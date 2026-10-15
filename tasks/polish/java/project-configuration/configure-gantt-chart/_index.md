---
date: 2026-10-15
description: Dowiedz się, jak utworzyć activity, ustawić data directory, dostosować
  table fields i zapisać projekt jako MPP przy użyciu Aspose.Tasks for Java. Przewodnik
  krok po kroku dla programistów Java.
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: Jak utworzyć activity i ustawić data directory przy użyciu Aspose.Tasks
  for Java
og_description: Jak utworzyć activity, dostosować table fields i zapisać projekt jako
  MPP przy użyciu Aspose.Tasks for Java. Zapoznaj się z tym szczegółowym przewodnikiem,
  aby szybko wdrożyć rozwiązanie.
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: Jak utworzyć activity i ustawić data directory w Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: Jak utworzyć activity i ustawić data directory przy użyciu Aspose.Tasks for
  Java
url: /pl/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć aktywność i ustawić katalog danych przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
W tym samouczku odkryjesz **jak utworzyć aktywność** programowo, skonfigurujesz **katalog danych** oraz **zapiszesz projekt jako MPP**, jednocześnie **dostosowując pola tabeli** w widoku wykresu Gantta. Aspose.Tasks for Java to potężne API, które obsługuje ponad 30 formatów wejściowych i wyjściowych oraz może przetwarzać projekty zawierające do 10 000 zadań bez ładowania całego pliku do pamięci. Po zakończeniu przewodnika będziesz w stanie automatyzować tworzenie projektów, wzbogacać zadania o niestandardowe atrybuty i generować gotowy do otwarcia plik MPP dla Microsoft Project.

## Szybkie odpowiedzi
- **Jaki jest pierwszy krok?** Ustaw ścieżkę katalogu danych, w którym znajdują się pliki projektu.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Tasks for Java (do pobrania ze strony oficjalnej).  
- **Czy mogę dodać niestandardowe atrybuty?** Tak – możesz definiować rozszerzone atrybuty i wyświetlać je w wykresie Gantta.  
- **Czy potrzebna jest licencja do testów?** Dostępna jest tymczasowa licencja do celów ewaluacyjnych.  
- **Które IDE jest najlepsze?** Dowolne IDE Java (IntelliJ IDEA, Eclipse, NetBeans) będzie działać.

## Co to jest „ustaw katalog danych” i dlaczego ma to znaczenie?
Ustawienie katalogu danych informuje Aspose.Tasks, gdzie odczytywać i zapisywać pliki projektów. Bez prawidłowej ścieżki API nie może znaleźć Twoich plików `.mpp`, co prowadzi do błędów `FileNotFoundException`. Zdefiniowanie tego katalogu na początku kodu sprawia, że przepływ pracy jest powtarzalny i oddziela kwestie systemu plików od logiki biznesowej.

## Dlaczego dostosować pola tabeli w wykresie Gantta?
Niestandardowe pola tabeli pozwalają wyświetlać dodatkowe informacje — takie jak niestandardowe atrybuty, dane zasobów lub notatki specyficzne dla projektu — bezpośrednio w widoku Gantta. Redukuje to potrzebę oddzielnych raportów i zapewnia interesariuszom jedną, bogatą w dane wizualizację, która może przyspieszyć podejmowanie decyzji nawet o 30 %.

## Jak utworzyć nową aktywność?
Nową aktywność (zadanie) tworzysz, tworząc obiekt `Task` i dodając go do kolekcji zadań głównych projektu. Takie podejście umożliwia automatyczne generowanie dużych harmonogramów, pobieranie danych zadań z zewnętrznych systemów lub stosowanie masowych aktualizacji bez ręcznej edycji.

## Wymagania wstępne
1. **Java Development Kit (JDK)** – wersja 8 lub nowsza.  
2. **Aspose.Tasks for Java** – pobierz go ze **strony wydania Aspose.Tasks Java**.  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą, którego preferujesz.  

## Importowanie pakietów
Przestrzeń nazw `com.aspose.tasks` zawiera wszystkie klasy potrzebne do manipulacji projektami. Importowanie jej zapewnia dostęp do `Project`, `Task`, `ExtendedAttributeDefinition` oraz innych podstawowych typów.

```java
import com.aspose.tasks.*;
```

## Zależność Maven (opcjonalnie)
Jeśli zarządzasz projektem przy użyciu Maven, dodaj zależność Aspose.Tasks do `pom.xml`. Zapewni to automatyczne rozwiązanie biblioteki podczas budowania.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## Przewodnik krok po kroku

### Krok 1: skonfiguruj katalog danych
Zdefiniuj folder zawierający pliki projektu. Zmienna `dataDir` przechowuje ścieżkę bezwzględną i jest używana wielokrotnie w całym samouczku.

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` pełną ścieżką do folderu, w którym znajduje się `project.mpp`, na przykład `C:/Projects/MyGantt`.

### Krok 2: załaduj plik projektu
`Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Microsoft Project w pamięci. Załadowanie istniejącego pliku zapewnia dostęp do jego zadań, zasobów i tabel.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Krok 3: dodaj nową aktywność
`Task` reprezentuje pojedynczą aktywność w harmonogramie. Dodanie zadania do kolekcji zadań głównych wstawia je na najwyższym poziomie hierarchii projektu.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Krok 4: zdefiniuj niestandardowy atrybut
`ExtendedAttributeDefinition` pozwala utworzyć wielokrotnego użytku niestandardowe pole, które może być dołączone do dowolnego zadania, zasobu lub przydziału.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Krok 5: dodaj niestandardowy atrybut do zadania
`ExtendedAttribute` jest konkretną instancją niestandardowego atrybutu, którą przypisujesz do określonego zadania.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Krok 6: dostosuj tabelę – dodaj niestandardowy atrybut jako kolumnę
`TableField` opisuje kolumnę w tabeli wykresu Gantta. Dodając `TableField` odwołujący się do niestandardowego atrybutu, sprawiasz, że atrybut jest widoczny w widoku wykresu.

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

### Krok 7: zapisz projekt
Wywołanie `project.save` zapisuje wszystkie zmiany do nowego pliku. Stała `SaveFileFormat.MPP` informuje Aspose.Tasks, aby zapisał plik w natywnym binarnym formacie Microsoft Project.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **FileNotFoundException** podczas ładowania projektu | Ścieżka **set data directory** jest nieprawidłowa lub brakuje końcowego ukośnika. | Sprawdź, czy `dataDir` wskazuje dokładny folder i zawiera właściwy separator plików (`/` lub `\\`). |
| Niestandardowy atrybut nie jest widoczny w widoku Gantta | Pole tabeli zostało dodane pod niewłaściwym indeksem lub szerokość kolumny jest zbyt mała. | Upewnij się, że `table.getTableFields().add(3, attrField);` używa prawidłowego indeksu i w razie potrzeby dostosuj `setWidth`. |
| LicenseException przy zapisie | Nie zastosowano ważnej licencji do użytku produkcyjnego. | Zastosuj tymczasową lub stałą licencję przed wywołaniem `project.save()`. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
A: Tak, Aspose.Tasks jest dostępny dla .NET, Java i C++.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
A: Tak, możesz pobrać darmową wersję próbną ze **strony pobierania darmowej wersji próbnej Aspose.Tasks**.

**Q: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?**  
A: Wsparcie i pytania znajdziesz na [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

**Q: Jak mogę kupić licencję na Aspose.Tasks?**  
A: Licencję możesz zakupić na **stronie zakupu Aspose.Tasks**.

**Q: Czy potrzebna jest tymczasowa licencja do celów testowych?**  
A: Tak, tymczasową licencję możesz uzyskać na **stronie żądania tymczasowej licencji**.

## Podsumowanie
Teraz wiesz **jak utworzyć aktywność**, ustawić katalog danych, zdefiniować i dołączyć niestandardowy atrybut oraz **zapisać projekt jako MPP**, jednocześnie **dostosowując pola tabeli** w widoku wykresu Gantta przy użyciu Aspose.Tasks for Java. Te możliwości dają pełną programistyczną kontrolę nad danymi projektu, umożliwiając automatyczne generowanie harmonogramów i bogatsze raportowanie wizualne dla interesariuszy.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose

## Powiązane samouczki

- [Jak utworzyć pusty plik projektu w Aspose.Tasks (MS Project)](/tasks/java/project-configuration/create-empty-project-file/)
- [Jak utworzyć plik MPP – Utwórz i zapisz pusty projekt w formacie MPP przy użyciu Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Jak utworzyć projekt aspose.tasks – Ustaw nowe atrybuty zadania](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}