---
date: 2025-12-09
description: Dowiedz się, jak utworzyć obiekt projektu w Javie i obsługiwać funkcje
  oceny w formułach Aspose.Tasks przy użyciu Javy. Odkryj, jak utworzyć rozszerzony
  atrybut dla zadań.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Utwórz obiekt projektu w Javie – Obsługa funkcji oceny w Aspose.Tasks
url: /pl/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa funkcji oceny w formułach Aspose.Tasks

## Wprowadzenie
Aspose.Tasks for Java pozwala na **create project object java** tworzenie instancji i ocenianie funkcji Microsoft Project bezpośrednio w kodzie Java. Dzięki osadzaniu tych formuł możesz wykonywać zaawansowane obliczenia, generować niestandardowe raporty i automatyzować analizę projektu, nie opuszczając środowiska programistycznego. Ten samouczek przeprowadzi Cię przez cały proces — od skonfigurowania obiektu projektu po dodanie rozszerzonego atrybutu, który może przechowywać dane niestandardowe.

## Szybkie odpowiedzi
- **Co oznacza „create project object java”?** Tworzy w pamięci instancję `Project`, którą możesz programowo modyfikować.  
- **Jakiej biblioteki wymaga?** Aspose.Tasks for Java (pobierz ze strony oficjalnej).  
- **Czy potrzebna jest licencja?** Do użytku produkcyjnego wymagana jest tymczasowa lub pełna licencja; dostępna jest darmowa wersja próbna.  
- **Czy mogę używać pól niestandardowych?** Tak – możesz definiować i dołączać rozszerzone atrybuty do zadań.  
- **Czy jest to kompatybilne ze wszystkimi formatami plików Project?** Aspose.Tasks obsługuje formaty MPP, MPT i XML.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Środowisko programistyczne Java** – JDK 8+ oraz IDE, takie jak IntelliJ IDEA lub Eclipse.  
2. **Biblioteka Aspose.Tasks for Java** – Pobierz i dołącz bibliotekę ze [strony pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Dodaj przestrzeń nazw Aspose.Tasks do swojej klasy Java, aby móc pracować z projektami, zadaniami i rozszerzonymi atrybutami:

```java
import com.aspose.tasks.*;
```

## Krok 1: Utwórz obiekt projektu Java
Utwórz nową instancję obiektu `Project`. Będzie ona kontenerem dla wszystkich zadań, zasobów i danych niestandardowych, które zdefiniujesz.

```java
Project project = new Project();
```

Powyższa linia **creates project object java**, która zaczyna jako pusta i gotowa do dostosowania.

## Krok 2: Jak utworzyć rozszerzony atrybut
Zdefiniuj rozszerzony atrybut, który będzie przechowywać niestandardowe dane liczbowe (np. wartość sinusa) dla każdego zadania.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Tutaj **create extended attribute** typu `Number` o nazwie „Sine” i powiązujemy go z zadaniami.

## Krok 3: Dodaj rozszerzony atrybut do projektu
Zarejestruj definicję atrybutu w projekcie, aby każde zadanie mogło się do niego odwoływać.

```java
project.getExtendedAttributes().add(attr);
```

## Krok 4: Utwórz nowe zadanie
Dodaj proste zadanie o nazwie „Task” pod zadaniem głównym projektu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Krok 5: Powiąż rozszerzony atrybut z zadaniem
Połącz wcześniej zdefiniowany rozszerzony atrybut z nowo utworzonym zadaniem.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Teraz zadanie posiada niestandardowe pole „Sine”, które możesz używać w formułach lub obliczeniach.

## Dlaczego używać funkcji oceny?
Osadzanie funkcji MS Project w formułach Aspose.Tasks umożliwia:
- Wykonywanie obliczeń w locie (np. `Sin([Start])`) bez użycia zewnętrznych narzędzi.  
- Trzymanie całej logiki projektu w jednym, łatwym do utrzymania kodzie.  
- Generowanie dynamicznych raportów odzwierciedlających zmiany danych w czasie rzeczywistym.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Formuła zwraca `NaN`** | Sprawdź, czy typ pola niestandardowego odpowiada oczekiwanemu typowi liczbowemu. |
| **Rozszerzony atrybut nie jest widoczny** | Upewnij się, że definicja atrybutu została dodana do projektu **przed** tworzeniem zadań. |
| **Wyjątek licencyjny** | Zainstaluj tymczasową lub pełną licencję; tryb próbny może ograniczać niektóre funkcje. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.Tasks for Java może obsługiwać złożone formuły MS Project?**  
A: Tak, Aspose.Tasks for Java obsługuje ocenę szerokiego zakresu funkcji MS Project, umożliwiając złożone obliczenia w aplikacjach Java.

**Q: Czy Aspose.Tasks for Java jest kompatybilne z różnymi wersjami plików Microsoft Project?**  
A: Tak, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.

**Q: Czy mogę wypróbować Aspose.Tasks for Java przed zakupem?**  
A: Tak, możesz pobrać darmową wersję próbną Aspose.Tasks for Java ze strony [tutaj](https://purchase.aspose.com/buy).

**Q: Jak mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
A: Możesz uzyskać wsparcie na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**Q: Czy dostępna jest tymczasowa licencja dla Aspose.Tasks for Java?**  
A: Tak, możesz uzyskać tymczasową licencję do testów ze strony Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

**Ostatnia aktualizacja:** 2025-12-09  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}