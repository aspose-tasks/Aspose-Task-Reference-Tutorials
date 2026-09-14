---
date: 2026-09-14
description: Dowiedz się, jak zmienić format waluty i odczytać właściwości waluty
  w Java przy użyciu Aspose.Tasks. Wyodrębnij currency code, pobierz currency symbol
  i zaktualizuj project currency w plikach MS Project.
keywords:
- change currency format
- retrieve currency symbol
- update project currency
- extract currency code java
lastmod: 2026-09-14
linktitle: Jak zmienić currency format
og_description: Dowiedz się, jak zmienić currency format i odczytać właściwości waluty
  w Java przy użyciu Aspose.Tasks. Przewodnik krok po kroku dotyczący wyodrębniania
  currency code i aktualizacji project currency.
og_image_alt: Tutorial showing how to change currency format in Aspose.Tasks for Java
og_title: Jak zmienić format waluty w Java przy użyciu Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to change currency format and read currency properties in
    Java using Aspose.Tasks. Extract currency code, retrieve currency symbol, and
    update project currency in MS Project files.
  headline: How to change currency format in Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Use `Project.setCurrencyCode()` and related methods, then save the
      project again.
    question: Can I change the currency after the project is already saved?
  - answer: The numeric values remain unchanged; only the display format (symbol,
      decimal separator) is updated. You must recalculate costs if you need conversion
      between currencies.
    question: Does changing the currency affect existing cost values?
  - answer: Aspose.Tasks supports any ISO‑4217 currency code, so you’re effectively
      unlimited.
    question: Are there any limits on the number of currencies I can define?
  - answer: The library falls back to the default currency (USD) and logs a warning;
      you can override this by setting the desired currency manually.
    question: What happens if I open a project with an unsupported currency code?
  - answer: Absolutely. The same API works for both *.mpp* and *.xml* formats.
    question: Is it possible to read/write currency properties in a Project XML file?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- change currency format
- Aspose.Tasks
- Java project management
- currency handling
title: Jak zmienić format waluty w Java przy użyciu Aspose.Tasks
url: /pl/java/currency-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt właściwości waluty w Javie z Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się, jak **zmienić format waluty** i odczytać właściwości waluty w projektach Java korzystających z Aspose.Tasks. Dokładne dane finansowe są niezbędne dla zespołów międzynarodowych, a opanowanie tych interfejsów API pozwala wyodrębnić kod ISO‑4217, pobrać symbol waluty i zaktualizować ustawienia pieniężne projektu bez ręcznej edycji arkuszy kalkulacyjnych.

## Szybkie odpowiedzi
- **Co oznacza „odczyt waluty”?** Oznacza to wyodrębnienie kodu waluty, symbolu oraz ustawień formatu liczbowego przechowywanych w pliku Project.  
- **Dlaczego dostosować ustawienia waluty?** Aby dopasować raporty kosztowe do regionalnych konwencji i uniknąć błędów konwersji.  
- **Czy potrzebna jest licencja?** Tak – wymagana jest ważna licencja Aspose.Tasks for Java do użytku produkcyjnego; darmowa wersja próbna działa w celach oceny.  
- **Jakie wersje Project są obsługiwane?** Zarówno formaty *.mpp* (Project 2007‑2024), jak i *.xml* są w pełni obsługiwane, obejmując ponad 20 lat wersji plików.  
- **Czy wymagana jest dodatkowa konfiguracja?** Wystarczy dodać plik JAR Aspose.Tasks for Java do classpath i zaimportować odpowiednie klasy.

## Odczyt właściwości waluty w Javie w projektach Aspose.Tasks
W dynamicznym świecie zarządzania projektami wyodrębnianie szczegółów waluty jest niezbędne do dokładnej analizy kosztów. Nasz dedykowany przewodnik **[Reading Currency Properties in Aspose.Tasks Projects](./read-properties/)** prowadzi Cię przez każdy krok — od otwarcia pliku projektu po pobranie kodu waluty, symbolu i formatu. Postępując zgodnie z samouczkiem, będziesz w stanie:
* Pobrać kod waluty (np. USD, EUR) używany w całym projekcie.  
* Uzyskać dostęp do symbolu waluty oraz ustawień formatowania liczb.  
* Wykorzystać te informacje do generowania zlokalizowanych raportów kosztowych lub zasilania pulpitów finansowych.  

Zrozumienie, jak odczytywać walutę, zapewnia możliwość audytu budżetów projektowych, porównywania kosztów między regionami oraz utrzymania zgodności ze standardami księgowymi.

## Jak wyodrębnić kod waluty w Javie przy użyciu Aspose.Tasks
Metoda `Project.getCurrencyCode()` zwraca trzy‑literowy identyfikator ISO‑4217 jednostki pieniężnej projektu.

**Bezpośrednia odpowiedź:** Wywołaj `project.getCurrencyCode()`, aby uzyskać kod waluty, taki jak **USD** lub **EUR**; możesz następnie przechowywać, rejestrować lub przekazywać tę wartość do zewnętrznych usług finansowych w celu konwersji. To jednowierszowe wywołanie zapewnia niezawodny, oparty na standardach identyfikator, który działa we wszystkich obsługiwanych wersjach Project.  

Metoda zapewnia szybki sposób synchronizacji danych projektu z systemami ERP, które oczekują ustandaryzowanego kodu.

## Jak dostosować format waluty w Javie przy użyciu Aspose.Tasks
Zmiana wizualnej reprezentacji wartości pieniężnych odbywa się za pomocą trzech prostych właściwości.

`project.setCurrencySymbol(String)` ustawia symbol waluty wyświetlany przy wartościach pieniężnych.  
`project.setCurrencyDecimalSeparator(char)` definiuje znak używany do oddzielenia części całkowitej od ułamkowej.  
`project.setCurrencyThousandsSeparator(char)` definiuje znak używany do oddzielenia grup tysięcy.  

**Bezpośrednia odpowiedź:** Użyj `project.setCurrencySymbol("€")`, `project.setCurrencyDecimalSeparator(",")` i `project.setCurrencyThousandsSeparator(".")`, aby odpowiednio zdefiniować symbol, separator dziesiętny i separator tysięcy — to w pełni zmienia format waluty jednorazowo. Dostosowanie tych ustawień zapewnia, że każdy interesariusz widzi liczby w znanym stylu, co zmniejsza ryzyko nieporozumień.  

* `project.setCurrencySymbol("€")` – ustawia wizualny symbol.  
* `project.setCurrencyDecimalSeparator(",")` – definiuje separator dziesiętny.  
* `project.setCurrencyThousandsSeparator(".")` – definiuje separator tysięcy.  

## Jak ustawić właściwości waluty w projektach Aspose.Tasks
Gdy projekt przenosi się na nowy rynek lub klient żąda innego formatu pieniężnego, konieczne będzie programowe zaktualizowanie waluty.  

`project.setCurrencyCode(String)` definiuje kod waluty ISO‑4217 dla projektu.  

**Bezpośrednia odpowiedź:** Wywołaj `project.setCurrencyCode("GBP")` razem z `project.setCurrencySymbol("£")` oraz odpowiednimi separatorami, a następnie zapisz projekt; biblioteka aktualizuje wszystkie ustawienia wyświetlania, zachowując istniejące dane kosztowe. To podejście daje pełną kontrolę nad finansową reprezentacją harmonogramu.  

Nasz przewodnik krok po kroku **[Setting Currency Properties in Aspose.Tasks Projects](./set-properties/)** wyjaśnia, jak:
* Zdefiniować nowy kod waluty i symbol dla całego projektu.  
* Dostosować format liczbowy (miejsca dziesiętne, separatory tysięcy) do lokalnych konwencji.  
* Zapisać zaktualizowany plik projektu bez utraty istniejących danych.  

Opanowując, jak ustawiać walutę, możesz w locie przełączać się między USD, GBP, JPY lub dowolną obsługiwaną walutą.

## Dlaczego opanować obsługę waluty w Aspose.Tasks?
Właściwa obsługa waluty eliminuje kosztowne nieporozumienia i usprawnia globalną współpracę.  

**Bezpośrednia odpowiedź:** Opanowanie obsługi waluty pozwala prezentować koszty w natywnym formacie każdego zespołu, zapewnia dokładne raportowanie, spełnia regionalne standardy księgowe i umożliwia zautomatyzowane przepływy pracy finansowej — oszczędzając godziny ręcznego przekształcania na projekt.  

* **Globalna współpraca:** Zespoły w różnych krajach mogą przeglądać koszty w swoim natywnym formacie.  
* **Dokładne raportowanie:** Zapobiega zaokrągleniom lub błędom konwersji, które mogą wpływać na budżetowanie.  
* **Zgodność:** Dostosuj się do regionalnych standardów księgowych i wymagań klienta.  
* **Automatyzacja:** Zmniejsz ręczne edycje, programowo stosując ustawienia waluty podczas generowania projektu.  

## Praktyczne przypadki użycia
* **Multi‑national projects:** Firma budowlana zarządzająca placami w Europie i Ameryce Północnej musi prezentować budżety zarówno w EUR, jak i USD.  
* **Financial audits:** Audytorzy potrzebują przejrzystego wglądu w kontekst waluty dla każdego wpisu kosztowego.  
* **Dynamic pricing models:** Dostawcy SaaS dostosowują koszty subskrypcji w zależności od lokalnej waluty klienta.  

## Typowe pułapki i wskazówki
* **Pułapka:** Zapomnienie o aktualizacji symbolu waluty po zmianie kodu.  
  **Wskazówka:** Zawsze ustawiaj jednocześnie kod i symbol, aby uniknąć niezgodnych wyświetleń.  
* **Pułapka:** Poleganie na domyślnej lokalizacji maszyny uruchamiającej kod.  
  **Wskazówka:** Jawnie określ żądany format waluty w kodzie Aspose.Tasks, aby zapewnić spójność w różnych środowiskach.  

## Samouczki dotyczące właściwości waluty
### [Odczyt właściwości waluty w projektach Aspose.Tasks](./read-properties/)
Dowiedz się, jak wyodrębnić informacje o walucie z plików MS Project przy użyciu Aspose.Tasks for Java. Dostarczony przewodnik krok po kroku.  

### [Ustawianie właściwości waluty w projektach Aspose.Tasks](./set-properties/)
Dowiedz się, jak ustawiać właściwości waluty w projektach Aspose.Tasks przy użyciu Javy. Manipuluj plikami Microsoft Project bez wysiłku.  

## Najczęściej zadawane pytania

**Q:** Czy mogę zmienić walutę po zapisaniu projektu?  
**A:** Tak. Użyj `Project.setCurrencyCode()` i powiązanych metod, a następnie ponownie zapisz projekt.  

**Q:** Czy zmiana waluty wpływa na istniejące wartości kosztów?  
**A:** Wartości liczbowe pozostają niezmienione; aktualizowany jest jedynie format wyświetlania (symbol, separator dziesiętny). Musisz przeliczyć koszty, jeśli potrzebna jest konwersja między walutami.  

**Q:** Czy istnieją ograniczenia co do liczby walut, które mogę zdefiniować?  
**A:** Aspose.Tasks obsługuje dowolny kod waluty ISO‑4217, więc w praktyce nie ma limitu.  

**Q:** Co się stanie, jeśli otworzę projekt z nieobsługiwanym kodem waluty?  
**A:** Biblioteka przełącza się na domyślną walutę (USD) i zapisuje ostrzeżenie; możesz to nadpisać, ręcznie ustawiając żądaną walutę.  

**Q:** Czy możliwe jest odczytywanie/zapisywanie właściwości waluty w pliku Project XML?  
**A:** Zdecydowanie tak. To samo API działa zarówno dla formatów *.mpp*, jak i *.xml*.  

---

**Ostatnia aktualizacja:** 2026-09-14  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [właściwości projektu java – wyodrębnij symbol waluty z MPP przy użyciu Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Jak pobrać walutę z MS Project przy użyciu Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Właściwości projektu Java – odczytaj metadane przy użyciu Aspose.Tasks](/tasks/java/project-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}