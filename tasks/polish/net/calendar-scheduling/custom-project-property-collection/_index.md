---
date: 2026-10-15
description: Dowiedz się, jak dodać custom property i zarządzać custom project properties
  w Aspose.Tasks dla .NET, zwiększając kontrolę nad metadanymi projektu.
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Zarządzanie kolekcją Custom Project Property w Aspose.Tasks
og_description: Dodaj custom property do swoich plików projektów za pomocą Aspose.Tasks
  dla .NET. Ten przewodnik pokazuje, jak zarządzać custom properties, odczytywać je
  oraz efektywnie dodawać wartości boolean lub string.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Dodaj custom property przy użyciu Aspose.Tasks .NET API dla projektów
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: Jak dodać custom property w Aspose.Tasks dla .NET
url: /pl/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać własną właściwość w Aspose.Tasks dla .NET

## Wprowadzenie

Obsługa własnych właściwości pozwala przechowywać metadane specyficzne dla projektu, których nie obejmują wbudowane pola. W tym samouczku dowiesz się, jak **dodać własną właściwość**, odczytać ją oraz zarządzać całą kolekcją własnych właściwości przy użyciu Aspose.Tasks dla .NET. Na końcu będziesz mógł dostosować pliki projektu przy użyciu wartości Boolean, DateTime, Double i String, które spełniają zasady Twojego biznesu.

## Szybkie odpowiedzi
- **Czy mogę dodać własną właściwość Boolean?** Tak – użyj `CustomPropertyType.Boolean`.
- **Ile typów własnych właściwości jest obsługiwanych?** Cztery: Boolean, DateTime, Double, String.
- **Czy kolekcja własnych właściwości jest tylko do odczytu?** Może być tylko do odczytu, jeśli projekt jest wczytany z źródła tylko do odczytu.
- **Czy potrzebuję licencji, aby używać tej funkcji?** Licencja tymczasowa wystarcza do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.
- **Które wersje .NET są kompatybilne?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Czym jest własna właściwość?

Własna właściwość to definiowane przez użytkownika pole metadanych, które dołączasz do obiektu Project. Pozwala przechowywać dodatkowe informacje, takie jak „Poziom ryzyka”, „ID klienta” lub dowolna flaga Boolean, której nie obejmują standardowe pola MS‑Project.

## Dlaczego dodać własną właściwość w Aspose.Tasks?

Aspose.Tasks obsługuje **ponad 50 formatów wejściowych i wyjściowych** i może obsługiwać projekty z **do 10 000 zadaniami** bez wczytywania całego pliku do pamięci. Dodawanie własnych właściwości umożliwia osadzenie danych krytycznych dla biznesu bezpośrednio w pliku projektu, eliminując potrzebę zewnętrznych baz danych i zapewniając, że dane podróżują wraz z projektem.

## Wymagania wstępne

- Visual Studio (dowolna aktualna edycja) zainstalowany na Twoim komputerze.  
- Aspose.Tasks for .NET – pobierz go z [download link](https://releases.aspose.com/tasks/net/).  
- Podstawowa znajomość składni C# oraz struktury projektu .NET.

## Importuj przestrzenie nazw

Poniższe przestrzenie nazw zapewniają dostęp do podstawowego modelu projektu oraz interfejsów API własnych właściwości.

```csharp
using Aspose.Tasks;
using System;


```

## Jak dodać własną właściwość w Aspose.Tasks?

Aby dodać własną właściwość, najpierw wczytaj projekt, następnie utwórz obiekt `CustomProperty`, ustaw jego nazwę, typ i wartość, a na końcu dodaj go do kolekcji `CustomProperties` projektu. Ta operacja osadza metadane bezpośrednio w pliku projektu, a zmiany są zapisywane po wywołaniu `project.Save(...)`.  
`CustomProperty` reprezentuje pojedyncze pole definiowane przez użytkownika, dołączone do projektu.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Krok 1: zainicjalizuj projekt

`Project` jest główną klasą reprezentującą plik projektu w Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Krok 2: sprawdź gotowość kolekcji własnych właściwości

`CustomProperties` to kolekcja przechowująca wszystkie obiekty własnych właściwości dla projektu.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Krok 3: dodaj własne właściwości

Metoda `Add` wstawia nową własną właściwość do kolekcji projektu.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Krok 4: uzyskaj dostęp do własnych właściwości

Kolekcja `CustomProperties` implementuje IEnumerable, umożliwiając iterację po każdej `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Krok 5: pobierz wartość własnej właściwości

Metoda `Get` zwraca wartość własnej właściwości na podstawie jej nazwy.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Krok 6: iteruj po nazwach własnych właściwości

Właściwość `Names` zapewnia listę wszystkich nazw własnych właściwości w kolekcji.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Krok 7: usuń lub wyczyść własne właściwości

Metoda `Remove` usuwa określoną właściwość, natomiast `Clear` opróżnia całą kolekcję.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Typowe pułapki i rozwiązywanie problemów

- **Kolekcja tylko do odczytu** – Jeśli `project.CustomProperties.IsReadOnly` zwraca `true`, upewnij się, że plik źródłowy nie jest otwarty w trybie wyłącznego odczytu lub skopiuj go do lokalizacji z prawem zapisu przed edycją.  
- **Niezgodność typu** – Przypisanie wartości, która nie odpowiada zadeklarowanemu `CustomPropertyType`, powoduje wyrzucenie `ArgumentException`. Zawsze ustaw `Value` po określeniu właściwego `Type`.  
- **Zapisywanie zmian** – Po dodaniu lub usunięciu właściwości wywołaj `project.Save("output.mpp")`, aby zachować modyfikacje; w przeciwnym razie zmiany pozostaną tylko w pamięci.

## Najczęściej zadawane pytania

**Q: Czy mogę dodać własne właściwości dowolnego typu danych do mojego projektu przy użyciu Aspose.Tasks dla .NET?**  
A: Tak, możesz dodać własne właściwości obsługujące typy Boolean, DateTime, Double i String.

**Q: Czy można iterować po nazwach własnych właściwości w Aspose.Tasks dla .NET?**  
A: Oczywiście, możesz iterować po nazwach własnych właściwości używając właściwości `Names`.

**Q: Jak mogę usunąć określoną własną właściwość z mojego projektu?**  
A: Możesz usunąć własną właściwość po nazwie, używając metody `Remove`.

**Q: Czy Aspose.Tasks dla .NET zapewnia wsparcie dla licencji tymczasowych?**  
A: Tak, możesz uzyskać licencję tymczasową ze strony Aspose w celach oceny.

**Q: Gdzie mogę znaleźć wsparcie lub dalszą pomoc dotyczącą Aspose.Tasks dla .NET?**  
A: Możesz odwiedzić forum Aspose.Tasks [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy lub zapytań.

---

**Ostatnia aktualizacja:** 2026-10-15  
**Testowano z:** Aspose.Tasks 24.11 dla .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak odczytać wbudowane właściwości projektu przy użyciu Aspose.Tasks dla .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Zarządzaj kolekcją atrybutów MS Project w Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Typy własnych pól Aspose.Tasks – Kalendarz i harmonogramowanie](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}