---
date: 2026-07-19
description: Dowiedz się, jak dodać niestandardowe typy pól w Aspose.Tasks dla .NET,
  korzystając z kodu step‑by‑step, wymagań wstępnych i FAQ.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Niestandardowe typy pól w Aspose.Tasks
og_description: Dowiedz się, jak dodać niestandardowe typy pól w Aspose.Tasks dla
  .NET. Postępuj zgodnie z tym step‑by‑step przewodnikiem, aby efektywnie tworzyć,
  definiować i używać extended attributes.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Jak dodać niestandardowe typy pól w Aspose.Tasks dla .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Jak dodać niestandardowe typy pól w Aspose.Tasks dla .NET
url: /pl/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać własne typy pól w Aspose.Tasks

## Wprowadzenie

W tym samouczku odkryjesz **jak dodać własne pola** do pliku Microsoft Project przy użyciu Aspose.Tasks dla .NET. Własne pola pozwalają przechowywać dodatkowe informacje — takie jak oceny ryzyka, kody działów lub własne notatki — bezpośrednio na zadaniach, zasobach lub samym projekcie. Przejdziemy przez cały proces, od przygotowania środowiska po definiowanie, dodawanie i weryfikację własnego pola tekstowego.

## Szybkie odpowiedzi
- **Czym jest własne pole?** Kolumna definiowana przez użytkownika, która może przechowywać tekst, liczby, daty lub flagi w zadaniach/zasobach.  
- **Która klasa definiuje własne pole?** `ExtendedAttributeDefinition`.  
- **Czy mogę dodać własne pole do istniejącego projektu?** Tak — załaduj projekt, utwórz definicję, a następnie dodaj ją do kolekcji.  
- **Czy potrzebna jest licencja na Aspose.Tasks?** Licencja jest wymagana w środowisku produkcyjnym; darmowa wersja próbna działa do oceny.  
- **Obsługiwane wersje .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co oznacza „jak dodać własne pole” w Aspose.Tasks?

**Jak dodać własne pole** odnosi się do procesu tworzenia `ExtendedAttributeDefinition` i dołączania go do kolekcji `ExtendedAttributes` projektu. Umożliwia to przechowywanie dodatkowych metadanych, które nie są częścią standardowego schematu Project. Może być używane dla zadań, zasobów lub samego projektu, pozwalając na rejestrowanie informacji takich jak poziomy ryzyka, kody działów lub własne notatki, które nie są dostępne w domyślnych polach.

## Dlaczego używać własnych pól w zarządzaniu projektami?

Aspose.Tasks obsługuje **ponad 50 wbudowanych typów rozszerzonych atrybutów** i pozwala definiować **dowolną liczbę własnych pól** bez znaczącego wpływu na rozmiar pliku. Korzystając z własnych pól możesz:  
Te pola pojawiają się jako dodatkowe kolumny w Microsoft Project i mogą być odwoływane w formułach, raportach i filtrach. Są przechowywane w pliku projektu i podróżują wraz z nim, zapewniając, że wszelkie narzędzia downstream zachowają niestandardowe dane.

## Wymagania wstępne

### 1. Zainstalowany Visual Studio
Upewnij się, że Visual Studio (2019 lub nowszy) jest zainstalowane na Twoim komputerze. Możesz pobrać je ze strony Microsoft.

### 2. Aspose.Tasks dla .NET
Dodaj pakiet NuGet Aspose.Tasks do swojego projektu. Pobierz najnowszą wersję [tutaj](https://releases.aspose.com/tasks/net/).

### 3. Podstawowa znajomość C#
Powinieneś być zaznajomiony ze składnią C#, klasami i strukturą projektu .NET.

## Importowanie przestrzeni nazw

Klasy `Project`, `ExtendedAttributeDefinition` oraz powiązane wyliczenia znajdują się w przestrzeni nazw `Aspose.Tasks`. Zaimportuj ją na początku swojego pliku:

Przestrzeń nazw `Aspose.Tasks` dostarcza wszystkie podstawowe typy do obsługi plików Microsoft Project.

```csharp

```

## Jak dodać własne pole do projektu?

Załaduj istniejący projekt, utwórz definicję własnego pola i dodaj ją do kolekcji rozszerzonych atrybutów projektu — wszystko w trzech zwięzłych krokach. Ten wzorzec działa dla zadań, zasobów i samego projektu oraz zapewnia, że własne pole zostanie zachowane po zapisaniu pliku.

### Krok 1: Utwórz obiekt Project
`Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Project w pamięci. Utworzenie go ładuje plik i daje dostęp do zadań, zasobów oraz rozszerzonych atrybutów.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Krok 2: Zdefiniuj własne pole
`ExtendedAttributeDefinition` opisuje nową kolumnę. W tym przykładzie tworzymy własne pole typu **Text** dla zadań i nadajemy mu alias „MyText”. Wartość wyliczeniowa `ExtendedAttributeTask.Text1` informuje Aspose.Tasks, gdzie przechowywać wartość.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Krok 3: Dodaj definicję własnego pola do projektu
Kolekcja `ExtendedAttributes` projektu przechowuje wszystkie definicje własnych pól. Dodanie definicji udostępnia ją dla każdego zadania w projekcie.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Typowe problemy i rozwiązania
- **Pole nie pojawia się w interfejsie MS Project** – Upewnij się, że ustawiłeś właściwość `Alias`; MS Project wyświetla alias jako nagłówek kolumny.  
- **Zapisywanie powoduje wyjątek** – Sprawdź, czy plik projektu nie jest tylko do odczytu i czy masz ważną licencję.  
- **Wartości własnych pól znikają po ponownym załadowaniu** – Upewnij się, że wywołujesz `project.Save("output.mpp")` po przypisaniu wartości do zadań.

## Często zadawane pytania

**Q: Czy mogę używać Aspose.Tasks z innymi frameworkami .NET?**  
A: Tak, Aspose.Tasks działa z .NET Framework, .NET Core oraz .NET 5/6/7.

**Q: Czy Aspose.Tasks jest odpowiedni dla aplikacji na poziomie przedsiębiorstwa?**  
A: Zdecydowanie. Obsługuje przetwarzanie projektów z **do 10 000 zadań** i może działać w wielowątkowych środowiskach serwerowych.

**Q: Czy Aspose.Tasks obsługuje wiele formatów plików projektów?**  
A: Tak — Aspose.Tasks odczytuje i zapisuje formaty MPP, XML, HTML i CSV, obejmując **wszystkie główne wersje Microsoft Project**.

**Q: Czy mogę manipulować danymi zasobów przy użyciu Aspose.Tasks?**  
A: Tak, możesz dodawać, aktualizować i usuwać zasoby, a także przypisywać do nich własne pola.

**Q: Czy istnieje forum społecznościowe dla użytkowników Aspose.Tasks?**  
A: Tak, możesz odwiedzić [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby interagować z innymi użytkownikami i uzyskać wsparcie od zespołu Aspose.

---

**Ostatnia aktualizacja:** 2026-07-19  
**Testowano z:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Mistrzowskie definicje rozszerzonych atrybutów MS Project w Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipulowanie rozszerzonymi atrybutami MS Project przy użyciu Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Integracja Field Helper MS Project w Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}