---
date: 2026-10-05
description: Dowiedz się, jak utworzyć projekt testowy i obliczyć liczbę dni pomiędzy
  datami przy użyciu Aspose.Tasks for Java, dodać pole niestandardowe i efektywnie
  manipulować plikami MPP.
keywords:
- create test project
- calculate days between dates
- define extended attribute
- set deadline Aspose.Tasks
- manipulate mpp file
lastmod: 2026-10-05
linktitle: Praca z formułami w Aspose.Tasks
og_description: Utwórz projekt testowy i oblicz liczbę dni pomiędzy datami przy użyciu
  Aspose.Tasks for Java. Ten przewodnik pokazuje, jak dodać pole niestandardowe, ustawić
  terminy zadań i zapisać projekt jako plik MPP.
og_image_alt: 'Aspose.Tasks Java tutorial: create test project and calculate date
  differences'
og_title: Utwórz projekt testowy i oblicz liczbę dni pomiędzy datami
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  headline: Create test project and calculate days between dates
  type: TechArticle
- description: Learn how to create test project and calculate days between dates using
    Aspose.Tasks for Java, add a custom field, and manipulate MPP files efficiently.
  name: Create test project and calculate days between dates
  steps:
  - name: Create a test project with a custom field
    text: We begin by **creating a test project** and adding a custom field that will
      later hold our formula result. > *Pro tip:* `CreateTestProjectWithCustomField()`
      is a helper method that builds a minimal schedule and registers an extended
      attribute ready for formula assignment.
  - name: Define an extended attribute (add custom field)
    text: Next, we **define an extended attribute** – essentially the custom field
      – and give it a friendly alias. This is where we **add custom field** logic.
      - **Alias** makes the field readable in Project. - **Formula** calculates the
      number of days between a task’s *Finish* date and its *Deadline* – the c
  - name: Set deadline for a task (add deadline task & set task deadline)
    text: Now we **add deadline task** data by setting the *Deadline* property on
      a specific task. - The `Calendar` instance defines the exact deadline moment.
      - `set(Tsk.DEADLINE, …)` **sets task deadline** for the chosen task.
  - name: Save the project (manipulate Microsoft Project file)
    text: Finally, we **manipulate Microsoft Project** by persisting the changes to
      an MPP file. You can open `SaveFile.mpp` in Microsoft Project to see the custom
      field, formula result, and deadline reflected in the schedule.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks provides APIs for .NET, Java, and other platforms, allowing
      you to manipulate Microsoft Project files in the language of your choice.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely. Download a fully functional trial from the [Aspose.Tasks download
      page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks?
  - answer: The official docs are hosted at [Aspose.Tasks Java API Reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to
      ask questions and share experiences with the community.
    question: How can I get support for Aspose.Tasks?
  - answer: A temporary license is available for short‑term testing; you can request
      one from the [temporary license request page](https://purchase.aspose.com/temporary-license/).
    question: Do I need a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- custom fields
- date calculations
title: Utwórz projekt testowy i oblicz liczbę dni pomiędzy datami
url: /pl/java/formulas/work-with-formulas/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz projekt testowy i oblicz dni między datami

W tym samouczku **utworzysz projekt testowy** i **obliczysz liczbę dni między datami**, dodając pole niestandardowe, definiując atrybut rozszerzony i stosując formułę Microsoft Project przy użyciu biblioteki Aspose.Tasks dla Javy. Niezależnie od tego, czy musisz generować harmonogramy, obliczać terminy, czy automatyzować raportowanie, Aspose.Tasks pozwala programowo manipulować danymi projektu bez instalacji aplikacji desktopowej, obsługując ponad 50 formatów wejścia i wyjścia oraz przetwarzając pliki wielostronicowe w trybie oszczędzającym pamięć.

## Szybkie odpowiedzi
- **Co obejmuje samouczek?** Pokazuje, jak utworzyć projekt testowy, zdefiniować atrybut rozszerzony, ustawić termin zadania oraz użyć formuły do obliczenia dni między datami.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (najnowsza wersja).  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Jakie IDE mogę używać?** Dowolne IDE Java (IntelliJ IDEA, Eclipse, VS Code) obsługujące JDK 8+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut na skopiowanie kodu i uruchomienie.

## Czym jest „obliczanie dni między datami” w Aspose.Tasks?
W Aspose.Tasks formuła to ciąg znaków, który może odwoływać się do pól zadania i wykonywać obliczenia. `[Deadline] - [Finish]` to składnia formuły używana przez Aspose.Tasks do zwrócenia różnicy liczbowej w dniach między dwoma polami daty. Wynik jest przechowywany jako wartość numeryczna reprezentująca pełne dni, którą możesz wyświetlić w polu niestandardowym lub wykorzystać w dalszych obliczeniach.

## Dlaczego używać Aspose.Tasks do obliczania dni między datami?
Aspose.Tasks zapewnia **pełne pokrycie API** dla każdej właściwości Projektu, Zadania i Zasobu, działa na Windows, Linux i macOS oraz **nie wymaga instalacji Microsoft Project ani Office**. Silnik może przetworzyć projekty z **500+ zadaniami** w mniej niż sekundę na typowym serwerze, co czyni go idealnym dla potoków CI, kontenerów Docker i przetwarzania wsadowego o dużej skali.

## Jak ustawić termin (deadline) dla zadania
`java.util.Calendar` to klasa Javy reprezentująca konkretny moment w czasie. Ustawiasz termin, przypisując wartość `java.util.Calendar` do pola `Tsk.DEADLINE` zadania. Po utworzeniu instancji Calendar, ustaw jej rok, miesiąc i dzień na żądany termin, a następnie wywołaj `task.set(Tsk.DEADLINE, calendar);`. Termin jest przechowywany w pliku projektu i może być używany w formułach, takich jak `[Deadline] - [Finish]`.

## Jak zdefiniować atrybut rozszerzony
Atrybut rozszerzony to pole niestandardowe przechowujące wynik twojej formuły. Tworzysz go raz, nadajesz przyjazny alias i dołączasz wyrażenie `[Deadline] - [Finish]`, aby każde zadanie mogło automatycznie obliczyć interwał. Utwórz go, tworząc instancję `ExtendedAttribute`, ustawiając Alias, przypisując formułę i dodając go do kolekcji projektu.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

- **Java Development Kit (JDK) 8+** – pobierz ze strony Oracle lub użyj OpenJDK.  
- **Aspose.Tasks for Java** – pobierz najnowszy JAR ze [strona pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/) i dodaj go do classpath projektu lub zależności Maven/Gradle.

## Importowanie pakietów
Najpierw zaimportuj potrzebne klasy:

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## Przewodnik krok po kroku

### Krok 1: Utwórz projekt testowy z polem niestandardowym
Zaczynamy od **utworzenia projektu testowego** i dodania pola niestandardowego, które później będzie przechowywać wynik formuły.

```java
Project project = CreateTestProjectWithCustomField();
```

> *Wskazówka:* `CreateTestProjectWithCustomField()` to metoda pomocnicza, która buduje minimalny harmonogram i rejestruje atrybut rozszerzony gotowy do przypisania formuły.

### Krok 2: Zdefiniuj atrybut rozszerzony (dodaj pole niestandardowe)
Następnie **definiujemy atrybut rozszerzony** – właściwie pole niestandardowe – i nadajemy mu przyjazny alias. To miejsce, w którym **dodajemy logikę pola niestandardowego**.

```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```

- **Alias** sprawia, że pole jest czytelne w Project.  
- **Formuła** oblicza liczbę dni pomiędzy datą *Finish* (zakończenia) zadania a jego *Deadline* (terminem) – sedno *obliczania dni między datami*.

### Krok 3: Ustaw termin dla zadania (dodaj zadanie z terminem i ustaw termin zadania)
Teraz **dodajemy dane zadania z terminem**, ustawiając właściwość *Deadline* dla konkretnego zadania.

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```

- Instancja `Calendar` definiuje dokładny moment terminu.  
- `set(Tsk.DEADLINE, …)` **ustawia termin zadania** dla wybranego zadania.

### Krok 4: Zapisz projekt (manipuluj plikiem Microsoft Project)
Na koniec **manipulujemy plikiem Microsoft Project**, zapisując zmiany do pliku MPP.

```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```

Możesz otworzyć `SaveFile.mpp` w Microsoft Project, aby zobaczyć pole niestandardowe, wynik formuły i termin odzwierciedlone w harmonogramie.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Formuła nie jest obliczana** | Upewnij się, że ciąg `Formula` atrybutu używa poprawnych nazw pól (np. `[Deadline]`, `[Finish]`). |
| **Zadanie nie zostało znalezione** | Sprawdź, czy identyfikator zadania (`1` w przykładzie) istnieje; użyj `project.getRootTask().getChildren().size()` do debugowania. |
| **Wyjątek licencyjny** | Zastosuj ważną licencję Aspose.Tasks przed wywołaniem jakichkolwiek metod API (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks z innymi językami programowania?**  
A: Tak, Aspose.Tasks udostępnia API dla .NET, Javy i innych platform, umożliwiając manipulację plikami Microsoft Project w wybranym języku.

**Q: Czy dostępna jest bezpłatna wersja próbna Aspose.Tasks?**  
A: Oczywiście. Pobierz w pełni funkcjonalną wersję próbną ze [strona pobierania Aspose.Tasks](https://releases.aspose.com/).

**Q: Gdzie mogę znaleźć szczegółową dokumentację Aspose.Tasks?**  
A: Oficjalna dokumentacja jest dostępna pod adresem [Referencja API Aspose.Tasks Java](https://reference.aspose.com/tasks/java/).

**Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks?**  
A: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby zadawać pytania i dzielić się doświadczeniami z społecznością.

**Q: Czy potrzebuję tymczasowej licencji do oceny?**  
A: Tymczasowa licencja jest dostępna dla krótkoterminowych testów; możesz ją zamówić na [strona żądania tymczasowej licencji](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-10-05  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć plik MPP – Utwórz i zapisz pusty projekt w formacie MPP przy użyciu Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)
- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Javy](/tasks/java/project-properties/write-project-info/)
- [Jak utworzyć atrybut rozszerzony w Javie z Aspose.Tasks](/tasks/java/resource-management/extended-resource-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}