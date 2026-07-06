---
date: 2026-02-07
description: Dowiedz się, jak ustawić kod waluty w Javie w projektach Aspose.Tasks,
  zmienić symbol waluty i zastosować własny format waluty w plikach Microsoft Project.
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: kod waluty java – Jak ustawić w projektach Aspose.Tasks
url: /pl/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kod waluty w Aspose.Tasks – przewodnik Java

## Wprowadzenie
W tym samouczku dowiesz się **jak ustawić kod waluty w Javie** dla pliku Microsoft Project przy użyciu API Aspose.Tasks dla Javy. Niezależnie od tego, czy musisz *zmienić walutę* dla międzynarodowych zespołów, dostosować *symbol waluty*, czy zastosować **niestandardowy format waluty**, poniższe kroki przeprowadzą Cię przez proces z jasnymi wyjaśnieniami i gotowym do uruchomienia kodem.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java.  
- **Czy mogę zmienić symbol waluty?** Tak – użyj `CurrencySymbolPositionType` i `Prj.CURRENCY_SYMBOL`.  
- **Jakie formaty plików są obsługiwane?** XML, MPP i wiele innych poprzez `SaveFileFormat`.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja jest wymagana w produkcji.  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowej konfiguracji.

## Jak ustawić kod waluty w Javie w Aspose.Tasks
Waluta projektu określa, jak wyświetlane są wartości kosztów — kod (np. `AUD`), liczba cyfr po przecinku, symbol (`$`) oraz pozycja symbolu. Ustawienie tych właściwości zapewnia, że każde pole związane z kosztami (stawki zasobów, budżety zadań itp.) odzwierciedla prawidłowy format pieniężny dla Twojej grupy odbiorców.

## Dlaczego warto używać Aspose.Tasks do zmiany waluty?
- **Brak wymogu instalacji Microsoft Project** – manipuluj plikami na dowolnym serwerze.  
- **Pełne pokrycie API** – wszystkie pola związane z walutą są dostępne poprzez stałe `Prj`.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS z dowolnym IDE kompatybilnym z Javą.  
- **Wysoka wydajność** – przetwarzaj duże pliki projektów szybko i niezawodnie.  
- **Obsługa niestandardowego formatu waluty** – możesz definiować symbole, liczby miejsc po przecinku i pozycję, aby dopasować je do standardów regionalnych.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. **IDE** – Eclipse, IntelliJ IDEA lub dowolny edytor, którego preferujesz.  
4. **Folder z prawem zapisu** – w którym zostanie zapisany wygenerowany plik projektu.

## Importowanie pakietów
Najpierw zaimportuj klasy, które zapewniają dostęp do właściwości projektu i obsługi plików.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog danych
Określ folder zawierający pliki źródłowe oraz miejsce, w którym zostanie zapisany wynik.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Utwórz nową instancję projektu
Zainicjuj nowy obiekt `Project`. Ten obiekt reprezentuje plik Microsoft Project w pamięci.

```java
Project project = new Project();
```

### Krok 3: Ustaw właściwości waluty
Tutaj **ustawiamy szczegóły waluty**, takie jak kod, liczba cyfr, symbol i pozycja symbolu.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Wskazówka:** Jeśli musisz **zmienić walutę projektu** w istniejącym pliku, po prostu wczytaj go za pomocą `new Project("file.mpp")` przed zastosowaniem powyższych ustawień.

### Krok 4: Zapisz zaktualizowany projekt
Zapisz projekt z powrotem na dysk w wybranym formacie. W tym przykładzie używamy formatu XML, ale możesz także wybrać `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Krok 5: Potwierdź powodzenie
Wypisz przyjazny komunikat, aby wiedzieć, że operacja zakończyła się bez błędów.

```java
System.out.println("Process completed Successfully");
```

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **`NullPointerException` przy `project.save`** | `dataDir` nie jest prawidłową ścieżką lub brakuje uprawnień do zapisu. | Upewnij się, że katalog istnieje i proces Java ma dostęp do zapisu. |
| **Symbol waluty nie wyświetla się** | Pozycja symbolu jest ustawiona niepoprawnie dla Twojego regionu. | Użyj `CurrencySymbolPositionType.Before`, jeśli symbol ma poprzedzać kwotę. |
| **Plik projektu nie otwiera się w MS Project** | Zapis w starszym formacie z niekompatybilnymi ustawieniami. | Zapisz używając `SaveFileFormat.MPP` dla pełnej kompatybilności z najnowszymi wersjami MS Project. |

## Najczęściej zadawane pytania

**P:** Czy mogę ustawić wiele walut w jednym projekcie przy użyciu Aspose.Tasks?  
**O:** Tak, Aspose.Tasks umożliwia obsługę wielu walut w jednym pliku projektu, ustawiając właściwości waluty na poziomie zasobu lub zadania.

**P:** Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików Microsoft Project?  
**O:** Zdecydowanie. Biblioteka obsługuje pliki MPP od Project 2000 aż po najnowsze wydania, a także XML i inne formaty.

**P:** Czy Aspose.Tasks zapewnia wsparcie dla niestandardowych formatów waluty?  
**O:** Tak, możesz definiować własne symbole, liczbę miejsc po przecinku i pozycję, aby spełnić dowolne wymagania regionalne.

**P:** Czy mogę zintegrować Aspose.Tasks z innymi bibliotekami lub frameworkami Java?  
**O:** Oczywiście. API jest czystą Javą, więc współpracuje bezproblemowo ze Spring, Hibernate, Maven, Gradle i innymi ekosystemami.

**P:** Gdzie mogę znaleźć dodatkowe wsparcie lub pomoc dotyczącą Aspose.Tasks?  
**O:** Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), aby uzyskać pomoc społeczności, lub zapoznaj się z oficjalną dokumentacją, aby uzyskać szczegółowe odniesienia do API.

## Podsumowanie
Teraz wiesz **jak ustawić kod waluty w Javie**, jak **zmienić wartości waluty** oraz jak **zmienić symbol waluty** przy użyciu Aspose.Tasks dla Javy. Te możliwości pozwalają dostosować dane kosztowe dla zespołów międzynarodowych, generować raporty specyficzne dla regionu i utrzymać spójność plików projektów na całym świecie.

---

**Ostatnia aktualizacja:** 2026-02-07  
**Testowano z:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}