---
date: 2026-09-30
description: Dowiedz się, jak utworzyć rozszerzony atrybut zadania przy użyciu Aspose.Tasks
  dla Java, wiodącej biblioteki do zarządzania projektami w języku Java, umożliwiającej
  dodawanie niestandardowych pól zadania.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Jak utworzyć rozszerzony atrybut zadania przy użyciu Aspose.Tasks Java
og_description: Dowiedz się, jak utworzyć rozszerzony atrybut zadania przy użyciu
  Aspose.Tasks dla Java, wiodącej biblioteki do zarządzania projektami w języku Java,
  umożliwiającej dodawanie niestandardowych pól zadania.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Jak utworzyć rozszerzony atrybut zadania przy użyciu Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Jak utworzyć rozszerzony atrybut zadania przy użyciu Aspose.Tasks Java
url: /pl/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć rozszerzony atrybut zadania przy użyciu Aspose.Tasks Java

## Wprowadzenie
W tym samouczku dowiesz się, jak **utworzyć rozszerzony atrybut zadania** w pliku Microsoft Project przy użyciu Aspose.Tasks dla Javy. Dodawanie pól niestandardowych pozwala przechwycić dane specyficzne dla projektu, które nie są objęte wbudowanymi kolumnami, dając bardziej szczegółową kontrolę nad raportowaniem i planowaniem zasobów. Po zakończeniu przewodnika będziesz w stanie dodać atrybuty tekstowe, z włączonym wyszukiwaniem oraz atrybuty czasu trwania do dowolnego zadania.

## Szybkie odpowiedzi
- **Co oznacza „rozszerzony atrybut”?** To pole niestandardowe, które definiujesz i dołączasz do zadań, zasobów lub przydziałów.  
- **Która biblioteka dodaje tę funkcję?** Aspose.Tasks for Java, biblioteka do zarządzania projektami w Javie.  
- **Czy potrzebuję licencji, aby wypróbować?** Tak – darmowa 30‑dniowa wersja próbna jest dostępna na stronie Aspose.  
- **Czy mogę dodać wartości wyszukiwania?** Oczywiście; możesz podać listę dozwolonych wartości dla pól tekstowych lub czasu trwania.  
- **Czy API jest kompatybilne z Java 8 i nowszymi?** Tak, obsługuje Java 8+ i działa na wszystkich głównych systemach operacyjnych.

## Co to jest rozszerzony atrybut zadania?
Rozszerzony atrybut zadania to kolumna definiowana przez użytkownika, która przechowuje dodatkowe informacje dla każdego zadania w pliku Project. Działa jak wbudowane pole, ale może przechowywać dowolny typ danych, którego potrzebujesz, taki jak tekst, liczby, daty lub czasy trwania.

## Dlaczego warto używać Aspose.Tasks dla Javy?
Aspose.Tasks obsługuje **ponad 50 formatów plików** i może przetwarzać projekty z **ponad 10 000 zadaniami** bez konieczności instalacji Microsoft Project. Biblioteka działa w pełni offline, zapewniając prywatność danych i deterministyczną wydajność dla rozwiązań na skalę przedsiębiorstwa.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

- Podstawową wiedzę programistyczną w Javie.  
- Zainstalowaną bibliotekę Aspose.Tasks for Java. Możesz ją pobrać ze [strony internetowej](https://releases.aspose.com/tasks/java/).  
- Środowisko IDE Java (IntelliJ IDEA, Eclipse lub VS Code) skonfigurowane na Twoim komputerze.

## Importowanie pakietów
Instrukcje `import` dają dostęp do podstawowych klas, których będziesz potrzebować, takich jak `Project`, `ExtendedAttributeDefinition` i `ExtendedAttribute`.  

`Project` reprezentuje plik Microsoft Project i udostępnia metody do odczytu, modyfikacji i zapisu.  
`ExtendedAttributeDefinition` definiuje pole niestandardowe, które może być dołączone do zadań, zasobów lub przydziałów.  
`ExtendedAttribute` jest instancją definicji, która przechowuje rzeczywistą wartość dla konkretnego podmiotu.

## Jak dodać rozszerzony atrybut tekstowy do zadania?
Aby dodać rozszerzony atrybut tekstowy, najpierw wczytaj projekt, następnie utwórz definicję typu Text, dodaj ją do kolekcji projektu, utwórz zadanie, zainicjuj atrybut z definicji, ustaw jego wartość tekstową, dołącz go do zadania i na końcu zapisz projekt.

### 1. Ustaw ścieżkę katalogu dokumentu
Określ, gdzie znajdują się Twoje pliki źródłowe i wyjściowe.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Utwórz nowy projekt
Zainicjuj obiekt `Project`, opcjonalnie ładując istniejący plik .mpp.

```java
String dataDir = "Your Document Directory";
```

### 3. Utwórz definicję rozszerzonego atrybutu typu Text1
Zdefiniuj pole niestandardowe jako kolumnę tekstową o nazwie „Text1”.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Dodaj definicję do kolekcji rozszerzonych atrybutów projektu
Zarejestruj nową definicję, aby projekt ją rozpoznał.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Dodaj zadanie do projektu
Utwórz zadanie, które otrzyma pole niestandardowe.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Utwórz rozszerzony atrybut z definicji atrybutu
Wygeneruj instancję, którą możesz powiązać z konkretnym zadaniem.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Przypisz wartość do wygenerowanego rozszerzonego atrybutu
Ustaw rzeczywisty tekst, który chcesz przechować, np. „Design Review”.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Dodaj rozszerzony atrybut do zadania
Dołącz instancję atrybutu do kolekcji `ExtendedAttributes` zadania.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Zapisz projekt
Zapisz zaktualizowany projekt na dysku w wybranym formacie.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Jak dodać atrybut tekstowy z opcją wyszukiwania?
Podczas dodawania atrybutu tekstowego z wyszukiwaniem, postępujesz tak samo jak przy atrybucie tekstowym, ale przed dodaniem definicji wypełniasz jej kolekcję `LookupValues` dozwolonymi ciągami znaków. Wartości te pojawiają się jako lista rozwijana w Microsoft Project, zapewniając spójność danych.

## Jak dodać atrybut czasu trwania z opcją wyszukiwania?
Aby dodać atrybut czasu trwania z wyszukiwaniem, zamień typ `Text1` na `Duration2` przy tworzeniu definicji, a następnie wypełnij kolekcję `LookupValues` ciągami określającymi czas trwania, takimi jak „1 dzień”, „2 dni” itp. Po dodaniu definicji do projektu, utwórz instancję atrybutu, ustaw wartość czasu trwania, dołącz ją do zadania i zapisz plik.

## Typowe problemy i rozwiązywanie
- **Wartości wyszukiwania nie pojawiają się** – Upewnij się, że dodałeś każdy wpis wyszukiwania do kolekcji `LookupValues` *przed* wywołaniem `project.getExtendedAttributes().add(definition)`.  
- **Wartość atrybutu nie została zapisana** – Sprawdź, czy dodajesz instancję `ExtendedAttribute` do zadania *po* ustawieniu jej wartości.  
- **Rozmiar pliku rośnie nieoczekiwanie** – Pracując z bardzo dużymi projektami, rozważ wywołanie `project.setSaveOptions(new ProjectSaveOptions())`, aby włączyć zapisywanie przyrostowe.

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Tasks dla Javy z innymi bibliotekami Java?**  
O: Tak, Aspose.Tasks dla Javy integruje się płynnie z dowolnym ekosystemem Java, w tym Spring, Hibernate i Apache POI.

**P: Czy Aspose.Tasks dla Javy jest odpowiedni dla aplikacji zarządzania projektami na dużą skalę?**  
O: Absolutnie. Biblioteka została zaprojektowana do obsługi projektów z wieloma tysiącami zadań i wspiera strumieniowanie, aby utrzymać niskie zużycie pamięci.

**P: Czy istnieją kwestie licencyjne przy używaniu Aspose.Tasks dla Javy w projekcie komercyjnym?**  
O: Tak, potrzebna jest ważna licencja komercyjna. Szczegóły możesz sprawdzić na [stronie Aspose.Tasks](https://purchase.aspose.com/buy).

**P: Jak mogę uzyskać wsparcie lub pomoc w zakresie Aspose.Tasks dla Javy?**  
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy społeczności, lub otwórz zgłoszenie wsparcia poprzez swoje konto Aspose.

**P: Czy mogę wypróbować Aspose.Tasks dla Javy przed zakupem?**  
O: Tak, możesz uzyskać dostęp do darmowej wersji próbnej na stronie [darmowej wersji próbnej Aspose.Tasks](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2026-09-30  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Powiązane samouczki

- [Niestandardowe kolumny i rozszerzone atrybuty w zarządzaniu projektami Java](/tasks/java/project-management/extended-attributes/)
- [Odczyt rozszerzonych atrybutów zadań przy użyciu Aspose.Tasks dla Javy](/tasks/java/task-properties/extended-task-attributes/)
- [Jak utworzyć projekt aspose.tasks – Ustaw nowe atrybuty zadania](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}