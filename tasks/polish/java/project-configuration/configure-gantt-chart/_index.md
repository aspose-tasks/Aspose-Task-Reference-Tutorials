---
date: 2026-02-13
description: Dowiedz się, jak utworzyć nową aktywność, ustawić katalog danych i zapisać
  projekt jako MPP w Aspose.Tasks Java. Ten przewodnik krok po kroku obejmuje także
  dostosowywanie pól tabeli.
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak utworzyć nową aktywność i ustawić katalog danych Aspose.Tasks
url: /pl/java/project-configuration/configure-gantt-chart/
weight: 10
---

 project as MPP** while **customizing table fields** in a Gantt chart view using Aspose.Tasks for Java. These steps give you full control over how project data is displayed, making your Gantt charts more informative and tailored to your stakeholders’ needs."

Last Updated line: keep date.

Tested With line: keep.

Author line: keep.

Now produce final content with shortcodes and placeholders unchanged.

Let's craft final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć nową aktywność i ustawić katalog danych Aspose.Tasks

## Introduction
W tym samouczku dowiesz się, **jak ustawić katalog danych**, **jak utworzyć nową aktywność**, oraz **jak zapisać projekt jako MPP**, konfigurować widok wykresu Gantta w projektach Aspose.Tasks przy użyciu Javy. Aspose.Tasks to solidne API Java, które pozwala programowo manipulować plikami Microsoft Project. Po zakończeniu tego przewodnika będziesz w stanie **dostosować pola tabeli**, zmienić katalog danych i wizualizować projekt dokładnie tak, jak tego potrzebujesz.

## Quick Answers
- **Jaki jest pierwszy krok?** Ustaw ścieżkę katalogu danych, w którym znajdują się pliki projektu.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (do pobrania ze strony oficjalnej).  
- **Czy mogę dodać własne atrybuty?** Tak – możesz definiować rozszerzone atrybuty i wyświetlać je na wykresie Gantta.  
- **Czy potrzebuję licencji do testowania?** Tymczasowa licencja jest dostępna do celów ewaluacyjnych.  
- **Które IDE działa najlepiej?** Każde IDE Java (IntelliJ IDEA, Eclipse, NetBeans) będzie działać.

## What is “set data directory” and why does it matter?
Ustawienie katalogu danych informuje Aspose.Tasks, gdzie ma odczytywać i zapisywać pliki projektu. Bez poprawnej ścieżki API nie może zlokalizować Twoich plików `.mpp`, co prowadzi do błędów FileNotFound. Zdefiniowanie tego katalogu na początku kodu sprawia, że dalszy przepływ pracy jest czysty i powtarzalny.

## Why customize table fields in a Gantt chart?
Niestandardowe pola tabeli pozwalają wyświetlać dodatkowe informacje — takie jak własne atrybuty, dane zasobów czy notatki specyficzne dla projektu — bezpośrednio w widoku Gantta. Dzięki temu wykres jest bardziej informacyjny dla interesariuszy i zmniejsza potrzebę przełączania się między wieloma raportami.

## How to create new activity?
Utworzenie nowej aktywności (zadania) jest jedną z podstawowych operacji przy budowaniu lub aktualizacji harmonogramu projektu. Dodając zadania programowo, możesz automatyzować generowanie złożonych planów projektowych, integrować dane z innych systemów lub stosować masowe zmiany bez ręcznej edycji.

## Prerequisites
Before you begin, make sure you have:

1. **Java Development Kit (JDK)** – dowolna aktualna wersja (8+).  
2. **Aspose.Tasks Library** – pobierz ją z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą, którego preferujesz.

## Import Packages
First, import the Aspose.Tasks namespace so you can work with its classes:

```java
import com.aspose.tasks.*;
```

## Step‑by‑Step Guide

### Step 1: Set Up Data Directory
Define the folder that contains your project files. This is the **set data directory** step that the tutorial focuses on.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path to the folder where `project.mpp` is stored.

### Step 2: Load Project File
Create a `Project` instance by loading an existing Microsoft Project file.

```java
Project project = new Project(dataDir + "project.mpp");
```

### Step 3: Add New Activity
Insert a new task (activity) into the root of the project. This demonstrates **how to create new activity** programmatically.

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### Step 4: Define Custom Attribute
Create a custom attribute definition that you can later attach to tasks.

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### Step 5: Add Custom Attribute to Task
Assign the newly defined attribute to the task you created.

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### Step 6: Customize Table – **customize table fields**
Add the custom attribute as a column in the Gantt chart table, specifying width, title, and alignment.

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

### Step 7: Save Project
Persist the changes to a new file that can be opened in Microsoft Project. This step **saves the project as MPP**.

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## Common Issues and Solutions
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **FileNotFoundException** podczas ładowania projektu | Ścieżka **set data directory** jest niepoprawna lub brakuje końcowego ukośnika. | Zweryfikuj, że `dataDir` wskazuje dokładny folder i zawiera odpowiedni separator plików (`/` lub `\\`). |
| Atrybut niestandardowy nie jest widoczny w widoku Gantta | Pole tabeli zostało dodane pod niewłaściwym indeksem lub szerokość kolumny jest zbyt mała. | Upewnij się, że `table.getTableFields().add(3, attrField);` używa prawidłowego indeksu i dostosuj `setWidth` w razie potrzeby. |
| LicenseException przy zapisie | Brak ważnej licencji zastosowanej do użytku produkcyjnego. | Zastosuj tymczasową lub stałą licencję przed wywołaniem `project.save()`. |

## Frequently Asked Questions

**Q: Czy mogę używać Aspose.Tasks w innych językach programowania?**  
A: Tak, Aspose.Tasks jest dostępny dla wielu języków programowania, w tym .NET, Java i C++.

**Q: Czy dostępna jest darmowa wersja próbna Aspose.Tasks?**  
A: Tak, możesz pobrać darmową wersję próbną z [here](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć wsparcie dla Aspose.Tasks?**  
A: Wsparcie i pytania możesz kierować na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

**Q: Jak mogę zakupić licencję na Aspose.Tasks?**  
A: Licencję możesz zakupić pod adresem [here](https://purchase.aspose.com/buy).

**Q: Czy potrzebuję tymczasowej licencji do celów testowych?**  
A: Tak, tymczasową licencję możesz uzyskać pod adresem [here](https://purchase.aspose.com/temporary-license/).

## Conclusion
Nauczyłeś się teraz, jak **ustawić katalog danych**, **utworzyć nową aktywność**, zdefiniować i dołączyć własny atrybut oraz **zapisać projekt jako MPP**, jednocześnie **dostosowując pola tabeli** w widoku wykresu Gantta przy użyciu Aspose.Tasks dla Javy. Te kroki dają pełną kontrolę nad tym, jak wyświetlane są dane projektu, czyniąc Twoje wykresy Gantta bardziej informacyjnymi i dopasowanymi do potrzeb interesariuszy.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Tasks Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}