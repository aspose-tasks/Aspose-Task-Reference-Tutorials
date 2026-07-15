---
date: 2026-02-10
description: Dowiedz się, jak wyodrębniać i aktualizować właściwości projektu Java,
  takie jak symbol waluty, przy użyciu Aspose.Tasks for Java. Zmieniaj walutę projektu
  i łatwo pobieraj symbol waluty.
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Właściwości projektu Java – wyodrębnij symbol waluty z pliku MPP przy użyciu
  Aspose.Tasks dla Javy
url: /pl/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyodrębnianie symbolu waluty mpp przy użyciu Aspose.Tasks dla Javy

## Wstęp
W tym samouczku nauczysz się, jak pracować z **java project properties** — konkretnie jak wyodrębnić symbol waluty z pliku Microsoft Project (MPP) oraz jak **change currency symbol java** lub **retrieve currency symbol java** przy użyciu biblioteki Aspose.Tasks. Niezależnie od tego, czy tworzysz narzędzie raportujące, integrujesz dane Project z systemem finansowym, czy po prostu potrzebujesz wyświetlić prawidłowy symbol waluty w interfejsie użytkownika, opanowanie tego małego, ale istotnego zadania sprawi, że Twoje aplikacje Java będą bardziej solidne i przyjazne dla użytkownika.

## Szybkie odpowiedzi
- **Co oznacza „extract currency symbol mpp”?** Oznacza to odczytanie symbolu waluty zapisanego w pliku MPP (Microsoft Project).  
- **Która biblioteka to obsługuje?** Aspose.Tasks for Java zapewnia prosty interfejs API do tego zadania.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jak długo to trwa?** Dzięki poniższemu kodowi możesz uzyskać symbol w mniej niż minutę.  
- **Czy mogę także zmienić symbol?** Tak – możesz ustawić nową wartość używając tej samej właściwości `Prj.CURRENCY_SYMBOL`.

## Co to jest „extract currency symbol mpp”?
Microsoft Project przechowuje symbol waluty (np. $, €, £) w nagłówku pliku projektu. Operacja **extract currency symbol mpp** odczytuje tę wartość, abyś mógł ją wyświetlić lub manipulować nią programowo.

## Dlaczego aktualizować symbol waluty w java project properties?
Projekty często obejmują wiele regionów. Możliwość **change project currency** lub **update currency symbol** w czasie działania pozwala dostosować raporty, faktury czy pulpity nawigacyjne do lokalnego rynku bez konieczności tworzenia nowego pliku projektu. Ta elastyczność jest kluczowym elementem efektywnego zarządzania java project properties.

## Prerequisites
Zanim przejdziesz dalej, upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub wyższa.  
2. **Aspose.Tasks for Java** – pobierz najnowszy plik JAR ze [strony pobierania Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. Ważny plik **project.mpp** umieszczony w folderze, do którego możesz odwołać się w kodzie.

## Importowanie pakietów
Najpierw zaimportuj klasy, które będą potrzebne do pracy z plikami Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Krok 1: Zdefiniuj katalog danych
Powiedz aplikacji, gdzie znajduje się Twój plik *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Wskazówka:** Użyj `System.getProperty("user.dir")`, aby zbudować ścieżkę bezwzględną działającą na dowolnym komputerze.

## Krok 2: Załaduj plik MS Project
Utwórz obiekt `Project`, który reprezentuje plik MPP w pamięci.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Krok 3: Pobierz (i opcjonalnie zmień) symbol waluty
Teraz **retrieve currency symbol java** poprzez odczytanie właściwości `Prj.CURRENCY_SYMBOL`. Możesz także **change currency symbol java** (lub **change project currency**) przypisując nowy ciąg znaków do tej samej właściwości.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Wywołanie `System.out.println` wypisuje symbol (np. `$`) na konsolę, potwierdzając, że wyodrębnianie zakończyło się sukcesem.

## Typowe problemy i jak je naprawić
| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| `NullPointerException` on `project.get(...)` | Nieprawidłowa ścieżka do pliku lub plik nie został znaleziony | Zweryfikuj `dataDir` i nazwę pliku; użyj `new File(dataDir).exists()` do debugowania |
| Unexpected symbol (e.g., `?`) | Projekt utworzony z nietypową lokalizacją | Upewnij się, że źródłowy plik MPP rzeczywiście definiuje symbol waluty; możesz ustawić go programowo, jak pokazano wyżej |
| License error | Korzystanie z wersji próbnej bez ważnego pliku licencji | Załaduj licencję przy pomocy `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` przed utworzeniem obiektu `Project` |

## Najczęściej zadawane pytania

**Q: Czy mogę manipulować innymi atrybutami projektu oprócz symboli waluty przy użyciu Aspose.Tasks?**  
A: Tak, Aspose.Tasks pozwala edytować zadania, zasoby, przydziały, kalendarze i wiele innych właściwości projektu.

**Q: Czy Aspose.Tasks jest kompatybilny z różnymi wersjami plików MS Project?**  
A: Absolutnie. Obsługuje formaty MPP, MPT i XML od Project 98 aż po najnowsze wydania.

**Q: Czy Aspose.Tasks oferuje dokumentację i wsparcie dla deweloperów?**  
A: Kompleksowa dokumentacja API, przykłady kodu oraz dedykowane forum wsparcia są dostępne na stronie internetowej Aspose.Tasks.

**Q: Czy mogę wypróbować Aspose.Tasks przed zakupem?**  
A: Tak – w pełni funkcjonalną wersję próbną można pobrać ze [strony Aspose](https://purchase.aspose.com/buy).

**Q: Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks?**  
A: Tymczasowe licencje są dostępne na [stronie tymczasowych licencji Aspose](https://purchase.aspose.com/temporary-license/) w celu oceny.

---

**Ostatnia aktualizacja:** 2026-02-10  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}