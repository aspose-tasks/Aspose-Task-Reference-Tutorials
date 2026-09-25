---
date: 2026-09-25
description: Dowiedz się, jak pobierać currency codes z plików MS Project przy użyciu
  Aspose.Tasks dla Java – szybki sposób na uzyskanie currency code, którego potrzebują
  programiści Java.
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Zarządzaj Currency Codes w Aspose.Tasks
og_description: Pobierz currency code Java z plików MS Project przy użyciu Aspose.Tasks.
  Ten przewodnik pokazuje, jak odczytać projekt, wyodrębnić ISO currency identifier
  i zastosować go w aplikacjach Java.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Pobierz currency code Java z MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Pobierz currency code Java z MS Project przy użyciu Aspose.Tasks
url: /pl/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pobieranie kodu waluty java z MS Project przy użyciu Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się **how to retrieve currency code java** z pliku MS Project przy użyciu biblioteki Aspose.Tasks Java API. Niezależnie od tego, czy potrzebujesz generować wielowalutowe raporty finansowe, konsolidować projekty w różnych regionach, czy po prostu wyświetlać prawidłowy symbol waluty w systemie downstream, poniższe kroki przeprowadzą Cię od konfiguracji środowiska po jednowierszowe wywołanie zwracające identyfikator waluty ISO. Po zakończeniu przewodnika będziesz swobodnie ładować dowolny obsługiwany format pliku Project i wyodrębniać trzy‑literowy kod waluty, taki jak `USD`, `EUR` lub `GBP`.

## Szybkie odpowiedzi
- **Co robi API?** It reads MS Project files and exposes properties such as the currency code.  
- **Jakiego języka użyto?** Java, via the Aspose.Tasks for Java library.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę pobrać kod w jednej linii?** Tak—`prj.get(Prj.CURRENCY_CODE)` returns the currency code string instantly.  
- **Czy jest kompatybilny ze wszystkimi wersjami Project?** Aspose.Tasks supports more than 20 input formats, including legacy MPP, XML, and XER files.

## Co to jest odczyt pliku MS Project?
Odczyt pliku MS Project oznacza programowe otwieranie pliku *.mpp* (lub innego obsługiwanego formatu, takiego jak XML lub XER) i dostęp do jego wewnętrznych struktur danych. Struktury te obejmują zadania, zasoby, kalendarze, tabele kosztów i ustawienia finansowe. Analizując plik, możesz wyodrębnić informacje bez uruchamiania Microsoft Project, co umożliwia automatyczne raportowanie, migrację i przepływy integracyjne.

## Dlaczego używać Aspose.Tasks do odczytu plików MS Project?
Aspose.Tasks oferuje czyste rozwiązanie w Java, które eliminuje potrzebę interfejsu COM lub lokalnej instalacji Microsoft Project. Obsługuje ponad 20 formatów plików, może obsłużyć projekty z tysiącami zadań przy zużyciu pamięci poniżej 100 MB i zapewnia bogaty model obiektowy. Bezpośredni dostęp do stałych takich jak `Prj.CURRENCY_CODE` pozwala natychmiast i niezawodnie pobrać informacje o walucie.

## Wymagania wstępne
Zanim przejdziemy do kodu, upewnij się, że masz następujące:

### Zainstalowany Java Development Kit (JDK)
Wymagany jest aktualny JDK (11 lub nowszy). Pobierz go z oficjalnej strony Oracle: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Biblioteka Aspose.Tasks for Java
Pobierz najnowsze pliki binarne Aspose.Tasks for Java i dodaj je do classpath swojego projektu. Pełna dokumentacja i linki do pobrania są dostępne [here](https://reference.aspose.com/tasks/java/).

## Importowanie pakietów
Klasa `Project` i stałe `Prj` znajdują się w przestrzeni nazw `com.aspose.tasks`. Zaimportuj je na początku swojego pliku źródłowego Java:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Przewodnik krok po kroku

### Krok 1: ustaw katalog danych
Zdefiniuj folder zawierający plik *.mpp*. Dostosuj ścieżkę do swojego środowiska, aby środowisko uruchomieniowe mogło znaleźć plik projektu.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: załaduj plik projektu
Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik MS Project w pamięci. Utworzenie instancji odczytuje plik i buduje model w pamięci, który możesz przeszukiwać.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Krok 3: pobierz kod waluty
Stała `Prj.CURRENCY_CODE` określa właściwość przechowującą identyfikator waluty ISO. Wywołanie `prj.get(Prj.CURRENCY_CODE)` zwraca trzy‑literowy kod w jednej operacji.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
Wynik będzie trzy‑literowym kodem ISO waluty (np. `USD`, `EUR`, `GBP`), który jest skonfigurowany w projekcie.

### Krok 4: jak pobrać kod waluty w Javie (dodatkowy kontekst)
Załaduj swój projekt, wywołaj `prj.get(Prj.CURRENCY_CODE)` i zapisz wynik w zmiennej typu `String`. Następnie możesz przekazać tę wartość do dowolnej usługi finansowej, silnika raportowania lub komponentu UI, który wymaga identyfikatora waluty.

### Krok 5: (opcjonalnie) użyj kodu waluty
Typowe scenariusze downstream obejmują:
- **Generowanie raportów** – przedrostek kodu do kolumn kosztów (`USD 1,200`).  
- **Integracja API** – wyślij kod ISO do bramek płatności, które wymagają parametru waluty.  
- **Konsolidacja danych** – grupuj wiele projektów według waluty w analizie na poziomie portfela.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **Brak wyniku** | Plik projektu nie definiuje waluty (domyślnie jest pusta). | Ustaw walutę w Microsoft Project lub przypisz ją za pomocą `prj.set(Prj.CURRENCY_CODE, "USD");` przed odczytem. |
| **Plik nie znaleziony** | Nieprawidłowa ścieżka `dataDir`. | Sprawdź ścieżkę i upewnij się, że nazwa pliku jest dokładnie zgodna, w tym wielkość liter. |
| **Nieobsługiwana wersja pliku** | Bardzo stary lub uszkodzony plik *.mpp*. | Uaktualnij do najnowszej wersji Aspose.Tasks lub najpierw skonwertuj plik do nowszego formatu w Microsoft Project. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks radzi sobie ze złożonymi strukturami projektów?**  
A: Tak, API odczytuje hierarchie zadań wielopoziomowe, pule zasobów, pola niestandardowe i kalendarze bez ograniczeń.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?**  
A: Zdecydowanie. Obsługuje MPP, XML, XER i inne formaty od Project 98 po najnowsze wydania Office.

**Q: Czy Aspose.Tasks zapewnia dokumentację i wsparcie?**  
A: Kompleksowa dokumentacja API, przykłady kodu oraz dedykowane wsparcie techniczne są dostępne na stronie Aspose.

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Oferowana jest darmowa wersja próbna, abyś mógł ocenić wszystkie funkcje, w tym wyodrębnianie kodu waluty.

**Q: Gdzie mogę uzyskać tymczasową licencję do oceny?**  
A: Tymczasowe licencje są dostępne na [website](https://purchase.aspose.com/temporary-license/).

---

**Ostatnia aktualizacja:** 2026-09-25  
**Testowano z:** Aspose.Tasks for Java (latest version)  
**Autor:** Aspose

## Powiązane samouczki

- [Właściwości projektu Java – Odczyt metadanych z Aspose.Tasks](/tasks/java/project-properties/)
- [Jak odczytać informacje o projekcie z Microsoft Project przy użyciu Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Pobieranie kodów konspektu MS Project w Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}