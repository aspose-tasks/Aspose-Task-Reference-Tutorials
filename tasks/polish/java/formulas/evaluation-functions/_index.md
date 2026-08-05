---
date: 2026-02-13
description: Dowiedz się, jak generować raport projektu, tworząc obiekt projektu w
  Javie, dodając rozszerzone atrybuty i używając funkcji oceny z Aspose.Tasks.
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: Generuj raport projektu – Utwórz obiekt projektu w Javie
url: /pl/java/formulas/evaluation-functions/
weight: 10
---

.

Make sure to keep bold formatting.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obsługa funkcji oceny w formułach Aspose.Tasks

## Wprowadzenie
Aspose.Tasks for Java pozwala **generować raport projektu** poprzez utworzenie **obiektu projektu** w Javie i ocenianie funkcji Microsoft Project bezpośrednio w kodzie. Dzięki osadzeniu tych formuł możesz wykonywać zaawansowane obliczenia, generować niestandardowe raporty i automatyzować analizę projektu bez opuszczania środowiska programistycznego. W tym samouczku przejdziemy przez tworzenie obiektu projektu, dodawanie rozszerzonego atrybutu oraz użycie funkcji oceny do **dodania danych pola niestandardowego zadania**.

## Szybkie odpowiedzi
- **Co oznacza „create project object java”?** Tworzy on w pamięci instancję `Project`, którą możesz programowo modyfikować.  
- **Jakiej biblioteki potrzebuję?** Aspose.Tasks for Java (pobierz ze strony oficjalnej).  
- **Czy potrzebna jest licencja?** Do użytku produkcyjnego wymagana jest tymczasowa lub pełna licencja Aspose.Tasks; dostępna jest wersja próbna.  
- **Czy mogę używać pól niestandardowych?** Tak – możesz **dodać rozszerzony atrybut** do zadań i traktować go jako pole niestandardowe.  
- **Czy jest to kompatybilne ze wszystkimi formatami plików Project?** Aspose.Tasks obsługuje formaty MPP, MPT i XML.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz:

1. **Środowisko programistyczne Java** – JDK 8+ oraz IDE, takie jak IntelliJ IDEA lub Eclipse.  
2. **Bibliotekę Aspose.Tasks for Java** – Pobierz i dołącz bibliotekę z [strony pobierania Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Dodaj przestrzeń nazw Aspose.Tasks do swojej klasy Java, aby móc pracować z projektami, zadaniami i rozszerzonymi atrybutami:

```java
import com.aspose.tasks.*;
```

## Generowanie raportu projektu – Utworzenie obiektu projektu w Javie
Zainicjuj nowy obiekt `Project`. Będzie on kontenerem dla wszystkich zadań, zasobów i danych niestandardowych, które zdefiniujesz.

```java
Project project = new Project();
```

Powyższa linia **tworzy obiekt projektu java**, który początkowo jest pusty i gotowy do dalszej konfiguracji.

## Jak dodać rozszerzony atrybut
Zdefiniuj rozszerzony atrybut, który będzie przechowywał niestandardowe dane liczbowe (np. wartość sinusa) dla każdego zadania.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Tutaj **dodajemy rozszerzony atrybut** typu `Number` o nazwie „Sine” i powiązujemy go z zadaniami.

## Dodanie rozszerzonego atrybutu do projektu
Zarejestruj definicję atrybutu w projekcie, aby każde zadanie mogło się do niego odwoływać.

```java
project.getExtendedAttributes().add(attr);
```

## Utworzenie nowego zadania
Dodaj proste zadanie o nazwie „Task” pod zadaniem głównym projektu.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Powiązanie rozszerzonego atrybutu z zadaniem
Połącz wcześniej zdefiniowany rozszerzony atrybut z nowo utworzonym zadaniem.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Teraz zadanie posiada niestandardowe pole „Sine”, które możesz wykorzystać w formułach lub obliczeniach. To właśnie sposób, w jaki **dodajesz dane pola niestandardowego zadania** programowo.

## Dlaczego warto używać funkcji oceny?
Osadzanie funkcji MS Project w formułach Aspose.Tasks umożliwia:

- Wykonywanie obliczeń w locie (np. `Sin([Start])`) bez użycia zewnętrznych narzędzi.  
- Trzymanie całej logiki projektu w jednym, łatwym do utrzymania kodzie.  
- Generowanie dynamicznych raportów odzwierciedlających zmiany danych w czasie rzeczywistym, pomagając **automatycznie generować raport projektu**.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Formuła zwraca `NaN`** | Sprawdź, czy typ pola niestandardowego odpowiada oczekiwanemu typowi liczbowemu. |
| **Rozszerzony atrybut nie jest widoczny** | Upewnij się, że definicja atrybutu została dodana do projektu **przed** utworzeniem zadań. |
| **Wyjątek licencyjny** | Zainstaluj tymczasową lub pełną **licencję Aspose.Tasks**; tryb próbny może ograniczać niektóre funkcje. |
| **Brak tymczasowej licencji** | Uzyskaj **tymczasową licencję Aspose** ze strony Aspose. |

## Najczęściej zadawane pytania

**P: Czy Aspose.Tasks for Java radzi sobie z złożonymi formułami MS Project?**  
O: Tak, Aspose.Tasks for Java obsługuje ocenę szerokiego zakresu funkcji MS Project, umożliwiając skomplikowane obliczenia w aplikacjach Java.

**P: Czy Aspose.Tasks for Java jest kompatybilny z różnymi wersjami plików Microsoft Project?**  
O: Tak, Aspose.Tasks for Java obsługuje różne wersje plików Microsoft Project, w tym formaty MPP, MPT i XML.

**P: Czy mogę wypróbować Aspose.Tasks for Java przed zakupem?**  
O: Tak, możesz pobrać darmową wersję próbną Aspose.Tasks for Java ze strony [tutaj](https://purchase.aspose.com/buy).

**P: Jak mogę uzyskać wsparcie dla Aspose.Tasks for Java?**  
O: Wsparcie dostępne jest na forum społeczności Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

**P: Czy dostępna jest tymczasowa licencja dla Aspose.Tasks for Java?**  
O: Tak, tymczasową licencję do testów można uzyskać na stronie Aspose [tutaj](https://purchase.aspose.com/temporary-license/).

## Podsumowanie
Postępując zgodnie z powyższymi krokami, nauczyłeś się **tworzyć obiekt projektu**, **dodawać rozszerzony atrybut** oraz wykorzystywać funkcje oceny do **automatycznego generowania raportu projektu**. Teraz możesz rozbudować tę podstawę, tworząc bardziej zaawansowane analizy projektowe, niestandardowe pulpity nawigacyjne lub zautomatyzowane narzędzia planowania – wszystko zasilane przez Aspose.Tasks for Java.

---

**Ostatnia aktualizacja:** 2026-02-13  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}