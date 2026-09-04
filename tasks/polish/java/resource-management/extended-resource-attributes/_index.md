---
date: 2026-06-10
description: Dowiedz się, jak utworzyć rozszerzony atrybut w Javie, wczytać plik Microsoft
  Project, ustawić wartości numeryczne i zapisać projekt jako XML przy użyciu Aspose.Tasks
  for Java.
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: Obsługa rozszerzonych atrybutów zasobów w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak utworzyć rozszerzony atrybut w Javie przy użyciu Aspose.Tasks
url: /pl/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć rozszerzony atrybut w Javie z Aspose.Tasks

## Wprowadzenie
W tym praktycznym przewodniku **utworzysz rozszerzony atrybut w Javie** dla pliku Microsoft Project przy użyciu Aspose.Tasks. Przejdziemy przez ładowanie istniejącego projektu, definiowanie nowego atrybutu numerycznego, przypisanie wartości do zasobu oraz ostateczne zapisanie zmian jako plik XML. Po zakończeniu będziesz mieć wielokrotnego użytku wzorzec kodu, który można wstawić do dowolnego rozwiązania do zarządzania projektami opartego na Javie.

## Szybkie odpowiedzi
- **Co to jest rozszerzony atrybut?**  
  Pole definiowane przez użytkownika (np. Wiek, Poziom umiejętności), które przechowuje dodatkowe dane dla zasobów lub zadań.  
- **Które API go tworzy?**  
  Aspose.Tasks for Java udostępnia klasę `ExtendedAttributeDefinition` do definiowania i zarządzania niestandardowymi atrybutami.  
- **Czy potrzebna jest licencja?**  
  Tymczasowa licencja ewaluacyjna działa w trakcie rozwoju; pełna licencja jest wymagana przy wdrożeniach produkcyjnych.  
- **Czy mogę przechowywać liczby?**  
  Tak – użyj `setNumericValue(BigDecimal)`, aby przypisać precyzyjne wartości dziesiętne.  
- **Jak zachować zmiany?**  
  Wywołaj `project.save("output.xml", SaveFileFormat.Xml)`, aby zapisać zaktualizowany projekt w formacie XML.

## Czym jest niestandardowy atrybut?
**Niestandardowy atrybut** (znany również jako rozszerzony atrybut) to dodatkowa kolumna, którą możesz dodać do zasobów lub zadań w Microsoft Project. Umożliwia przechwytywanie danych, które nie są objęte wbudowanymi polami, takich jak wiek pracownika, poziom certyfikacji lub dowolna metryka specyficzna dla firmy.

## Dlaczego tworzyć rozszerzony atrybut w Javie?
Tworzenie rozszerzonego atrybutu w Javie pozwala programowo wzbogacić dane projektu, zapewniając spójność między plikami i umożliwiając automatyczne raportowanie. Definiując atrybut raz, możesz zastosować go do dowolnej liczby zasobów lub zadań bez ręcznego wprowadzania, oszczędzając czas i redukując błędy.

- **Dostosuj dane do swojej organizacji** – przechowuj dowolną metrykę, która ma znaczenie, bez ręcznych obejść w Excelu.  
- **Umożliw bogatsze raportowanie** – zapytaj o niestandardowe pole później w dashboardach lub analizach.  
- **Utrzymaj spójność** – programowo zastosuj tę samą definicję w dziesiątkach projektów, eliminując błędy ludzkie.  
- **Testowane pod kątem wydajności** – Aspose.Tasks przetwarza projekty z aż do 10 000 zadań i 5 000 zasobów bez ładowania całego pliku do pamięci, zgodnie z benchmarkami produktu.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszą wersję z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA lub dowolne środowisko programistyczne kompatybilne z Javą.  

## Jak utworzyć rozszerzony atrybut w Javie?
Załaduj swój projekt, zdefiniuj atrybut, przypisz go do zasobu i zapisz plik – wszystko w kilku prostych krokach. Poniższe sekcje dzielą każdy krok na krótkie wyjaśnienie, po którym znajduje się placeholder, w którym znajduje się Twój rzeczywisty kod.

### Przewodnik krok po kroku

#### Importowanie pakietów
`Project`, `ExtendedAttributeDefinition`, `ExtendedAttributeResource` oraz powiązane klasy znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku swojego pliku Java.

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### Krok 1: Zdefiniuj katalog danych
`Paths` jest klasą narzędziową, która udostępnia metody uzyskiwania ścieżki systemu plików w sposób niezależny od platformy.

```java
String dataDir = "Your Data Directory";
```

#### Krok 2: Załaduj plik Microsoft Project
`Project` reprezentuje plik Microsoft Project w pamięci, umożliwiając odczyt i zapis jego zawartości.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### Krok 3: Zdefiniuj niestandardowy atrybut
`ExtendedAttributeDefinition` definiuje schemat nowego niestandardowego pola, które może być przypisane do zasobów lub zadań.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### Krok 4: Ustaw wartość numeryczną w Javie
`ExtendedAttributeResource` przechowuje wartość niestandardowego atrybutu dla konkretnej instancji zasobu.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### Krok 5: Dodaj zasób i dołącz niestandardowy atrybut
`Resource` modeluje zasób projektu, taki jak osoba, sprzęt lub materiał.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### Krok 6: Zapisz projekt jako XML
`SaveFileFormat` wymienia obsługiwane formaty wyjściowe do zapisywania projektu, w tym XML.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### Krok 7: Wyświetl wynik
`System.out.println` wypisuje linię tekstu na standardowe wyjście konsoli.

```java
System.out.println("Process completed Successfully");
```

## Typowe pułapki i wskazówki
- **Konflikty identyfikatorów atrybutów:** Zawsze wywołuj `project.getExtendedAttributes().getById(id)` przed utworzeniem nowej definicji, aby zapobiec duplikatom identyfikatorów.  
- **Obsługa precyzji:** Preferuj `BigDecimal` zamiast `float`/`double` dla dokładnych wartości liczbowych; zapobiega to błędom zaokrągleń w raportowaniu.  
- **Niezawodność ścieżki pliku:** Użyj `Paths.get(...).toAbsolutePath()` lub skonfiguruj katalog roboczy IDE, aby wyeliminować `FileNotFoundException`.  

## Najczęściej zadawane pytania

**Q: Czy mogę tworzyć niestandardowe atrybuty zarówno dla zadań, jak i zasobów?**  
A: Tak – użyj `ExtendedAttributeTask` zamiast `ExtendedAttributeResource` przy definiowaniu schematu atrybutu.

**Q: Czy można dodać wiele niestandardowych atrybutów jednocześnie?**  
A: Oczywiście. Utwórz osobne obiekty `ExtendedAttributeDefinition` dla każdego atrybutu i dołącz je do wybranych zasobów lub zadań.

**Q: W jakich formatach mogę zapisać projekt?**  
A: Aspose.Tasks obsługuje XML, MPP, PDF, HTML i ponad 30 dodatkowych formatów. W tym przykładzie użyliśmy `SaveFileFormat.Xml`.

**Q: Czy potrzebuję licencji do wersji deweloperskich?**  
A: Tymczasowa licencja ewaluacyjna wystarcza do testów. Do wszelkich wdrożeń produkcyjnych wymagana jest pełna licencja komercyjna.

**Q: Jak później odczytać wartości niestandardowych atrybutów?**  
A: Wywołaj `resource.getExtendedAttributes()` i iteruj po kolekcji; pobierz przechowywaną wartość za pomocą `getNumericValue()` lub `getTextValue()`.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Powiązane samouczki

- [Jak utworzyć zasoby – zarządzanie zasobami z Aspose.Tasks dla Java](/tasks/java/resource-management/)
- [Utwórz niestandardowe pole Aspose – obsługa rozszerzonych atrybutów](/tasks/java/project-management/extended-attributes/)
- [Jak utworzyć projekt – ustaw nowe atrybuty zadań z Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}