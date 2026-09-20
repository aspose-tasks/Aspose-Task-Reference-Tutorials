---
date: 2026-09-20
description: Dowiedz się, jak wyodrębnić symbol waluty mpp i zaktualizować właściwości
  projektu przy użyciu Aspose.Tasks dla Java. Zmieniaj i pobieraj symbol w zaledwie
  kilku linijkach kodu.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Wyodrębnij symbol waluty mpp przy użyciu Aspose.Tasks dla Java
og_description: Dowiedz się, jak wyodrębnić symbol waluty mpp i zaktualizować właściwości
  projektu przy użyciu Aspose.Tasks dla Java. Szybko, niezawodnie i gotowe do produkcji.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Jak wyodrębnić symbol waluty mpp przy użyciu Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Jak wyodrębnić symbol waluty mpp przy użyciu Aspose.Tasks Java
url: /pl/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie symbolu waluty mpp przy użyciu Aspose.Tasks dla Java

## Wprowadzenie
W tym samouczku nauczysz się, jak pracować z **java project properties** — konkretnie jak **extract currency symbol mpp** z pliku Microsoft Project (MPP) oraz jak **change currency symbol java** lub **retrieve currency symbol java** przy użyciu biblioteki Aspose.Tasks. Niezależnie od tego, czy tworzysz narzędzie do raportowania finansowego, integrujesz dane projektu z systemem ERP, czy po prostu potrzebujesz wyświetlać prawidłowy symbol waluty w interfejsie użytkownika, opanowanie tego małego, ale istotnego zadania sprawi, że Twoje aplikacje Java będą bardziej solidne i przyjazne dla użytkownika.

## Szybkie odpowiedzi
- **Co oznacza „extract currency symbol mpp”?** Oznacza to odczytanie symbolu waluty zapisanego w pliku MPP (Microsoft Project).  
- **Która biblioteka obsługuje to?** Aspose.Tasks for Java provides a simple API for the job.  
- **Czy potrzebuję licencji?** A free trial works for development; a commercial license is required for production.  
- **Jak długo to zajmuje?** With the code below, you can get the symbol in under a minute.  
- **Czy mogę również zmienić symbol?** Yes – you can set a new value using the same `Prj.CURRENCY_SYMBOL` property.

## Co to jest „extract currency symbol mpp”?
Pobieranie symbolu waluty z pliku MPP oznacza odczytanie jednego znaku, który Microsoft Project przechowuje w nagłówku pliku jako reprezentację jednostki pieniężnej projektu. Operacja ta pozwala wyświetlać prawidłowy symbol (np. $, €, £) w własnych aplikacjach bez konieczności twardego kodowania wartości.

## Dlaczego aktualizować symbol waluty w właściwościach projektu Java?
Aktualizacja symbolu waluty pozwala na bieżąco lokalizować raporty, faktury i pulpity. Przedsiębiorstwa realizujące projekty w wielu regionach mogą zmienić symbol w jednym kroku, unikając konieczności duplikowania całego pliku projektu. Aspose.Tasks może modyfikować tę właściwość w pamięci i zapisać plik ponownie, obsługując projekty zawierające do 2 000 zadań bez zauważalnego spadku wydajności.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Ważny plik **project.mpp** umieszczony w folderze, do którego możesz odwołać się w kodzie.

## Importowanie pakietów
Najpierw zaimportuj klasy, których będziemy potrzebować do pracy z plikami Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Krok 1: określenie katalogu danych
Powiedz aplikacji, gdzie znajduje się Twój plik *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Użyj `System.getProperty("user.dir")`, aby zbudować ścieżkę bezwzględną działającą na każdym komputerze.

## Krok 2: załadowanie pliku MS Project
`Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Microsoft Project w pamięci. Utworzenie tego obiektu ładuje strukturę pliku bez konieczności posiadania zainstalowanego Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Krok 3: pobranie (i opcjonalna zmiana) symbolu waluty
`Prj.CURRENCY_SYMBOL` jest kluczem właściwości przechowującym symbol waluty. Odczytanie go zwraca bieżący symbol; przypisanie nowego ciągu aktualizuje definicję waluty w projekcie.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Wywołanie `System.out.println` wypisuje symbol (np. `$`) na konsolę, potwierdzając, że pobieranie zakończyło się sukcesem.

## Typowe problemy i jak je rozwiązać
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | Nieprawidłowa ścieżka pliku lub plik nie został znaleziony | Zweryfikuj `dataDir` i nazwę pliku; użyj `new File(dataDir).exists()` do debugowania |
| Unexpected symbol (e.g., `?`) | Projekt utworzony z niestandardowym ustawieniem regionalnym | Upewnij się, że źródłowy plik MPP faktycznie definiuje symbol waluty; możesz ustawić go programowo, jak pokazano powyżej |
| License error | Używanie wersji próbnej bez ważnego pliku licencji | Załaduj licencję przy pomocy `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` przed utworzeniem obiektu `Project` |

## Najczęściej zadawane pytania

**Q: Czy mogę manipulować innymi atrybutami projektu oprócz symboli waluty przy użyciu Aspose.Tasks?**  
A: Tak, Aspose.Tasks pozwala edytować zadania, zasoby, przydziały, kalendarze i wiele innych właściwości projektu.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?**  
A: Zdecydowanie. Obsługuje formaty MPP, MPT i XML od Project 98 aż po najnowsze wersje.

**Q: Czy Aspose.Tasks oferuje dokumentację i wsparcie dla deweloperów?**  
A: Kompleksowa dokumentacja API, przykłady kodu oraz dedykowane forum wsparcia są dostępne na stronie Aspose.Tasks.

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak – w pełni funkcjonalną wersję próbną można pobrać ze [strony Aspose](https://purchase.aspose.com/buy).

**Q: Jak mogę uzyskać tymczasową licencję na Aspose.Tasks?**  
A: Tymczasowe licencje są dostępne na [stronie tymczasowych licencji Aspose](https://purchase.aspose.com/temporary-license/) w celu oceny.

**Last Updated:** 2026-09-20  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose

## Powiązane samouczki

- [Właściwości projektu Java – Odczyt metadanych z Aspose.Tasks](/tasks/java/project-properties/)
- [Jak pobrać walutę z MS Project przy użyciu Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks dla Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}