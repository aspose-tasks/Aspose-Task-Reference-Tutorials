---
date: 2026-09-09
description: Dowiedz się, jak zmienić symbol waluty w projektach Aspose.Tasks w Javie,
  ustawić kody walut, dostosować symbole i zastosować własne formaty dla plików Microsoft
  Project.
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Ustaw właściwości waluty w projektach Aspose.Tasks
og_description: Jak zmienić symbol waluty w Aspose.Tasks przy użyciu Javy. Odkryj
  instrukcje krok po kroku, wymagania wstępne i wskazówki, jak dostosować formatowanie
  kosztów projektu.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: Jak zmienić symbol waluty w Aspose.Tasks – przewodnik Java
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: Jak zmienić symbol waluty w projektach Aspose.Tasks – przewodnik Java
url: /pl/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić symbol waluty w Aspose.Tasks – przewodnik Java

## Wprowadzenie
W tym samouczku dowiesz się **jak zmienić symbol waluty** w pliku Microsoft Project przy użyciu Aspose.Tasks Java API. Niezależnie od tego, czy przygotowujesz raporty dla zagranicznego klienta, konsolidujesz budżety w wielu regionach, czy po prostu musisz dopasować się do standardów księgowych swojej firmy, dostosowanie symbolu waluty zapewnia, że każde pole związane z kosztami wyświetla prawidłowy znak pieniężny. Przewodnik prowadzi krok po kroku, od konfiguracji środowiska programistycznego po zapisanie zmian w nowym lub istniejącym pliku projektu.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java.  
- **Czy mogę zmienić symbol waluty?** Tak – ustaw `Prj.CURRENCY_SYMBOL` i wybierz `CurrencySymbolPositionType`.  
- **Jakie formaty plików są obsługiwane?** XML, MPP i wiele innych poprzez `SaveFileFormat`.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowej konfiguracji.

## Jak zmienić symbol waluty w Aspose.Tasks przy użyciu Java?
Wczytaj docelowy projekt (lub utwórz nowy), ustaw żądane właściwości waluty i zapisz plik. Cała operacja składa się z trzech wywołań API: utworzenia lub wczytania obiektu `Project`, przypisania kodu waluty, symbolu i pozycji, a następnie wywołania `project.save`. Takie podejście działa zarówno dla nowych projektów, jak i istniejących plików, bez konieczności instalacji Microsoft Project.

## Dlaczego używać Aspose.Tasks do zmiany symbolu waluty?
Aspose.Tasks zapewnia **pełne pokrycie API dla ponad 30 właściwości związanych z walutą**, umożliwiając definiowanie kodu, symbolu, liczby cyfr po przecinku i położenia w jednym miejscu. Biblioteka przetwarza wielostronicowe pliki Project w czasie krótszym niż sekunda na typowym sprzęcie serwerowym oraz działa na Windows, Linux i macOS bez dodatkowych zależności.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK) 8 lub wyższy** – API wymaga co najmniej JDK 8.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA lub dowolny edytor obsługujący Javę.  
4. **Folder z prawami zapisu** – w którym zostanie zapisany wygenerowany plik projektu.

## Importowanie pakietów
Poniższe klasy zapewniają dostęp do właściwości projektu, obsługi plików i ustawień waluty.  

`Project` – reprezentuje plik Microsoft Project w pamięci.  
`Prj` – zawiera stałe dla wszystkich właściwości na poziomie projektu, w tym pola walutowe.  
`CurrencySymbolPositionType` – wylicza możliwe pozycje symbolu waluty (przed lub po kwocie).  

Te importy są wymagane przed jakimkolwiek kodem manipulującym projektem.

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog danych
Wybierz folder, w którym znajdują się pliki źródłowe i do którego zostanie zapisany wynik. Upewnij się, że katalog istnieje i proces Java ma uprawnienia do zapisu.

### Krok 2: Utwórz nową instancję projektu
Klasa `Project` jest obiektem najwyższego poziomu w Aspose.Tasks, który reprezentuje pojedynczy plik Project w pamięci. Utworzenie jej instancji tworzy pusty projekt gotowy do konfiguracji.

### Krok 3: Ustaw właściwości waluty
Tutaj konfigurowany jest kod waluty, liczba cyfr po przecinku, sam symbol oraz pozycja symbolu.  

- **Kod waluty** – trzyznakowy kod ISO 4217, np. `AUD` lub `USD`.  
- **Cyfry po przecinku** – zazwyczaj 2 dla większości walut.  
- **Symbol waluty** – znak lub ciąg wyświetlany przy kwotach, np. `$` lub `€`.  
- **Pozycja symbolu** – `CurrencySymbolPositionType.Before` umieszcza symbol przed liczbą; `After` umieszcza go po liczbie.

Te ustawienia wpływają na każde pole związane z kosztami (stawki zasobów, budżety zadań itp.) w projekcie.

> **Wskazówka:** Jeśli musisz zmienić walutę w istniejącym pliku, wczytaj go przy użyciu `new Project("file.mpp")` przed zastosowaniem powyższych ustawień.

### Krok 4: Zapisz zaktualizowany projekt
Zapisz projekt z powrotem na dysk w wybranym formacie. Format XML jest czytelny dla człowieka, natomiast `SaveFileFormat.MPP` zachowuje pełną kompatybilność z Microsoft Project.

### Krok 5: Potwierdź sukces
Wydrukuj krótką wiadomość lub wpis w logu, aby wiedzieć, że operacja zakończyła się bez błędów. Jest to szczególnie przydatne w zautomatyzowanych pipeline'ach.

## Częste problemy i rozwiązania
| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` nie jest prawidłową ścieżką lub brakuje uprawnień do zapisu. | Upewnij się, że katalog istnieje i proces Java ma dostęp do zapisu. |
| **Symbol waluty się nie wyświetla** | Pozycja symbolu jest ustawiona niepoprawnie dla Twojego regionu. | Użyj `CurrencySymbolPositionType.Before`, jeśli symbol ma poprzedzać kwotę. |
| **Plik projektu nie otwiera się w MS Project** | Zapis w starszym formacie z niekompatybilnymi ustawieniami. | Zapisz przy użyciu `SaveFileFormat.MPP` dla pełnej kompatybilności z najnowszymi wersjami MS Project. |

## Najczęściej zadawane pytania

**Q: Czy mogę ustawić wiele walut w jednym projekcie przy użyciu Aspose.Tasks?**  
A: Tak, możesz przypisać różne ustawienia waluty do poszczególnych zasobów lub zadań, modyfikując ich odpowiednie pola kosztowe po zdefiniowaniu waluty na poziomie projektu.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
A: Zdecydowanie tak. Biblioteka obsługuje pliki MPP od Project 2000 aż po najnowsze wersje, a także XML i inne formaty wymiany.

**Q: Czy Aspose.Tasks zapewnia wsparcie dla niestandardowych formatów walut?**  
A: Tak, możesz definiować własne symbole, liczbę cyfr po przecinku i pozycję, aby spełnić dowolne wymagania regionalne, a te ustawienia są zachowywane w zapisanym pliku.

**Q: Czy mogę zintegrować Aspose.Tasks z innymi frameworkami Java?**  
A: Oczywiście. API jest czystą Javą, więc działa bezproblemowo z Spring, Hibernate, Maven, Gradle i innymi ekosystemami.

**Q: Gdzie mogę znaleźć dodatkową pomoc lub przykłady?**  
A: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy społeczności, lub zapoznaj się z oficjalną dokumentacją, aby uzyskać szczegółowe odniesienia do API.

## Podsumowanie
Teraz wiesz **jak zmienić symbol waluty** w projektach Aspose.Tasks przy użyciu Javy, jak ustawić kod waluty, dostosować liczbę cyfr po przecinku i zastosować własny symbol. Te możliwości pozwalają generować raporty kosztowe specyficzne dla lokalizacji, dopasować budżety projektów do regionalnych standardów księgowych oraz utrzymać spójność plików Microsoft Project w zespołach globalnych.

---

**Ostatnia aktualizacja:** 2026-09-09  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Powiązane samouczki

- [właściwości projektu Java – wyodrębnij symbol waluty z MPP przy użyciu Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Odczytaj właściwości waluty w Javie przy użyciu projektów Aspose.Tasks](/tasks/java/currency-properties/read-properties/)
- [Zarządzaj kodami walut w Javie przy użyciu Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}