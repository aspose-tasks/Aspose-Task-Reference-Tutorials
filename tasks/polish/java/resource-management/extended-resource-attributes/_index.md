---
date: 2026-01-13
description: Dowiedz się, jak utworzyć niestandardowy atrybut, wczytać plik Microsoft
  Project, ustawić wartość numeryczną w Javie oraz zapisać projekt jako XML przy użyciu
  Aspose.Tasks dla Javy.
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak utworzyć niestandardowy atrybut w MS Project przy użyciu Aspose.Tasks
url: /pl/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć niestandardowy atrybut w MS Project przy użyciu Aspose.Tasks

## Introduction
W tym samouczku **dowiesz się, jak utworzyć niestandardowy atrybut** dla zasobów w pliku Microsoft Project przy użyciu Aspose.Tasks for Java. Przeprowadzimy Cię przez ładowanie pliku Microsoft Project, definiowanie nowego atrybutu numerycznego, przypisywanie wartości oraz ostateczne zapisanie projektu jako XML. Po zakończeniu będziesz mieć jasny, praktyczny przykład, który możesz dostosować do własnych rozwiązań zarządzania projektami.

## Quick Answers
- **Co oznacza „custom attribute”?**  
  Pole definiowane przez użytkownika, które przechowuje dodatkowe informacje (np. Wiek, Poziom umiejętności) dla zasobu lub zadania.  
- **Która biblioteka to obsługuje?**  
  Aspose.Tasks for Java udostępnia płynne API do tworzenia i zarządzania niestandardowymi atrybutami.  
- **Czy potrzebna jest licencja?**  
  Tymczasowa darmowa licencja wystarczy do oceny; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę ustawiać wartości liczbowe?**  
  Tak – użyj `setNumericValue` z obiektem `BigDecimal` (np. `30.5345`).  
- **Jak projekt jest zapisywany?**  
  Zmieniony plik może być zapisany jako XML przy użyciu `SaveFileFormat.Xml`.

## What is a Custom Attribute?
**Custom attribute** (zwany także atrybutem rozszerzonym) to dodatkowa kolumna, którą możesz dodać do zasobów lub zadań w Microsoft Project. Umożliwia przechowywanie danych, które nie są objęte wbudowanymi polami, takich jak wiek pracownika, poziom certyfikacji czy dowolna metryka specyficzna dla firmy.

## Why Create a Custom Attribute in MS Project?
- **Tailor project data** do potrzeb Twojej organizacji.  
- **Enable advanced reporting** poprzez przechowywanie wartości, które później można zapytać.  
- **Maintain consistency** w wielu projektach, programowo stosując tę samą definicję atrybutu.

## Prerequisites
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Environment** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java** – pobierz najnowszą wersję z [here](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA lub dowolne środowisko kompatybilne z Javą.  

## Przewodnik krok po kroku

### Import Packages
Importuj najpierw klasy Aspose.Tasks, których będziesz potrzebować. Zapewniają one podstawową funkcjonalność obsługi projektów, zasobów i atrybutów rozszerzonych.

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

### Krok 1: Define Data Directory
Ustaw folder, w którym znajduje się źródłowy plik projektu oraz miejsce, w którym zostanie zapisany wynik.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Load Microsoft Project File
Utwórz instancję `Project`, ładując istniejący plik. To **load Microsoft project file** krok, który daje pełny dostęp do jego zawartości.

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### Krok 3: Define the Custom Attribute
Zdefiniujemy nowy atrybut numeryczny o nazwie **Age**. API sprawdza, czy definicja już istnieje; jeśli nie, tworzy ją.

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### Krok 4: Set Numeric Value in Java
Utwórz instancję atrybutu dla konkretnego zasobu i przypisz wartość numeryczną przy użyciu `setNumericValue`. To demonstracja **set numeric value java** w praktyce.

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### Krok 5: Add Resource and Attach the Custom Attribute
Dodaj nowy zasób o nazwie **R1** i dołącz do niego wcześniej utworzony niestandardowy atrybut.

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### Krok 6: Save Project as XML
Na koniec zachowaj zmiany, zapisując projekt. To **save project as xml** krok, który generuje czystą reprezentację XML zaktualizowanego pliku.

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### Krok 7: Display Result
Wydrukuj przyjazne potwierdzenie, abyś wiedział, że proces zakończył się bez błędów.

```java
System.out.println("Process completed Successfully");
```

Postępując zgodnie z tymi krokami, pomyślnie **utworzyłeś niestandardowy atrybut**, załadowałeś plik Microsoft Project, ustawiłeś wartość numeryczną przy użyciu Javy i zapisałeś projekt jako XML.

## Typowe pułapki i wskazówki
- **Attribute ID conflicts:** Zawsze sprawdzaj `getById` przed utworzeniem nowej definicji, aby uniknąć duplikatów ID.  
- **Precision handling:** `BigDecimal` zachowuje precyzję dziesiętną; unikaj używania `float` lub `double` dla dokładnych wartości.  
- **File paths:** Używaj ścieżek bezwzględnych lub skonfiguruj katalog roboczy IDE, aby zapobiec `FileNotFoundException`.  

## Najczęściej zadawane pytania

**Q: Czy mogę tworzyć niestandardowe atrybuty także dla zadań, jak i zasobów?**  
A: Tak – użyj `ExtendedAttributeTask` zamiast `ExtendedAttributeResource` przy definiowaniu atrybutu.

**Q: Czy istnieje możliwość dodania wielu niestandardowych atrybutów jednocześnie?**  
A: Oczywiście. Utwórz osobne obiekty `ExtendedAttributeDefinition` dla każdego atrybutu i dołącz je do wybranych zasobów lub zadań.

**Q: W jakich formatach mogę zapisać projekt?**  
A: Aspose.Tasks obsługuje XML, MPP oraz kilka innych formatów, takich jak PDF i HTML. W tym przykładzie użyliśmy `SaveFileFormat.Xml`.

**Q: Czy potrzebuję licencji Aspose.Tasks do wersji deweloperskich?**  
A: Tymczasowa licencja wystarczy do oceny. W środowiskach produkcyjnych wymagana jest pełna licencja.

**Q: Jak później odczytać wartości niestandardowych atrybutów?**  
A: Użyj `resource.getExtendedAttributes()` aby przeiterować dołączone atrybuty i pobrać ich wartości metodami `getNumericValue()` lub `getTextValue()`.

## Podsumowanie
Tworzenie **custom attribute** w Microsoft Project przy użyciu Aspose.Tasks for Java jest proste, gdy zrozumiesz przepływ pracy: załaduj projekt, zdefiniuj atrybut, ustaw jego wartość, dołącz go do zasobu i zapisz plik. Takie podejście umożliwia programowe rozszerzanie modeli danych projektu, co pozwala na bogatsze raportowanie i lepszą integrację z procesami biznesowymi.

---

**Last Updated:** 2026-01-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}