---
date: 2026-01-18
description: Dowiedz się, jak ustawić standardową stawkę i inne właściwości zasobów
  w MS Project przy użyciu Aspose.Tasks dla Javy, w tym jak dodać zasób w MS Project
  i efektywnie zarządzać zasobami.
linktitle: Set Resource Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ustawić standardową stawkę dla zasobów w Aspose.Tasks
url: /pl/java/resource-management/set-resource-properties/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw standardową stawkę dla zasobów w Aspose.Tasks

## Wprowadzenie
Jeśli tworzysz aplikacje Java, które muszą współpracować z plikami Microsoft Project, **ustawianie standardowej stawki** dla zasobu jest jednym z najczęstszych zadań. W tym samouczku dowiesz się, jak **ustawić standardową stawkę** oraz inne właściwości zasobu przy użyciu Aspose.Tasks for Java. Po zakończeniu przewodnika będziesz w stanie utworzyć obiekt projektu, dodać zasób do pliku MS Project i zarządzać zasobami MS Project z pewnością.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do pracy z plikiem Project?** `Project`
- **Która metoda dodaje nowy zasób?** `project.getResources().add()`
- **Jak ustawić standardową stawkę?** `rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(...))`
- **Czy potrzebna jest licencja do produkcji?** Tak, wymagana jest ważna licencja Aspose.Tasks.
- **Która wersja Javy jest obsługiwana?** Java 8+ (zalecana najnowsza JDK).

## Co to jest „ustaw standardową stawkę”?
Operacja *ustaw standardową stawkę* przypisuje zasobowi domyślny koszt godzinowy. Kierownicy projektów używają tej wartości do obliczania kosztów pracy, generowania raportów kosztowych i prognozowania budżetów.

## Dlaczego ustawiać stawki przy użyciu Aspose.Tasks?
- **Brak konieczności instalacji Microsoft Project** – manipulacja plikami bezpośrednio z Java.  
- **Pełna wierność** – wszystkie pola zasobów, w tym nadgodziny i stawki kosztów, są zachowane.  
- **Cross‑platform** – działa na Windows, Linux i macOS.  
- **Przyjazny automatyzacji** – idealny do przetwarzania wsadowego lub integracji z pipeline’ami CI.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz następujące elementy:

### Konfiguracja środowiska programistycznego Java
1. **Zainstaluj JDK:** Upewnij się, że masz zainstalowany Java Development Kit (JDK) w systemie. Możesz go pobrać ze [strony Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Konfiguracja IDE:** Wybierz Zintegrowane Środowisko Programistyczne (IDE), takie jak IntelliJ IDEA, Eclipse lub NetBeans i skonfiguruj je na swoim komputerze.

### Instalacja Aspose.Tasks for Java
1. **Pobierz Aspose.Tasks for Java:** Przejdź do [strony pobierania](https://releases.aspose.com/tasks/java/) i pobierz najnowszą wersję Aspose.Tasks for Java.  
2. **Integracja z projektem:** Dodaj bibliotekę Aspose.Tasks for Java do swojego projektu Java, dodając ją jako zależność.

## Importowanie pakietów
Aby rozpocząć, musisz zaimportować niezbędne pakiety z Aspose.Tasks for Java do swojego projektu. Ten krok zapewnia dostęp do wymaganych funkcjonalności.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import java.math.BigDecimal;
```

## Krok 1: Utwórz obiekt Project
Utworzenie **obiektu projektu** jest pierwszym krokiem do dowolnej manipulacji MS Project. Reprezentuje on cały plik projektu w pamięci.

```java
Project project = new Project();
```

## Krok 2: Dodaj zasób (add resource ms project)
Teraz **dodamy zasób MS Project** przy użyciu kolekcji Resources. Nazwa zasobu może być dowolna, pod warunkiem że ma sens w twoim harmonogramie.

```java
Resource rsc = project.getResources().add("Rsc");
```

## Krok 3: Ustaw właściwości zasobu (how to set rates)
Tutaj **ustawiamy standardową stawkę** oraz pokazujemy, jak ustawić stawkę nadgodzin. Stawki te są przechowywane jako wartości `BigDecimal`, aby zachować precyzję.

```java
// Set standard rate for the resource
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(15));
// Set overtime rate for the resource
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(20));
```

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| `NullPointerException` podczas wywoływania `set` | Zasób nie został poprawnie dodany. | Upewnij się, że `project.getResources().add()` zwraca nie‑nullowy `Resource`. |
| Stawki pojawiają się jako 0 w zapisanym pliku | Używanie `int` zamiast `BigDecimal`. | Zawsze używaj `BigDecimal.valueOf()` dla wartości pieniężnych. |
| Nie znaleziono licencji | Plik licencji nie został załadowany przed utworzeniem `Project`. | Załaduj licencję (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`) na początku programu. |

## Podsumowanie
Postępując zgodnie z tymi krokami, nauczyłeś się **tworzyć obiekt projektu**, **dodawać zasób MS Project** oraz **ustawiać standardową stawkę** wraz z innymi właściwościami zasobu. Daje to możliwość automatyzacji obliczeń kosztów, generowania niestandardowych raportów i pełnego zarządzania zasobami MS Project z poziomu Java.

## FAQ
### Czy Aspose.Tasks for Java radzi sobie z złożonymi plikami MS Project?
Tak, Aspose.Tasks for Java jest w stanie obsługiwać szeroką gamę formatów plików MS Project, w tym złożone, zawierające rozbudowane hierarchie zadań.

### Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?
Tak, możesz uzyskać darmową wersję próbną Aspose.Tasks for Java [tutaj](https://releases.aspose.com/).

### Gdzie mogę znaleźć wsparcie dla Aspose.Tasks for Java?
Możesz uzyskać pomoc i uczestniczyć w dyskusjach dotyczących Aspose.Tasks for Java na [forum wsparcia](https://forum.aspose.com/c/tasks/15).

### Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?
Możesz uzyskać tymczasową licencję ze [strony tymczasowych licencji](https://purchase.aspose.com/temporary-license/) w celu oceny.

### Gdzie mogę kupić licencjonowaną wersję Aspose.Tasks for Java?
Możesz zakupić licencjonowaną wersję Aspose.Tasks for Java na [stronie zakupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-18  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose