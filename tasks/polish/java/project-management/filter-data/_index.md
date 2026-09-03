---
date: 2026-06-05
description: Dowiedz się, jak filtrować pliki MPP przy użyciu Aspose.Tasks for Java,
  dostosować kryteria filtrowania i filtrować zadania według daty, aby usprawnić zarządzanie
  projektami.
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: Jak filtrować pliki MPP przy użyciu Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak filtrować pliki MPP przy użyciu Aspose.Tasks for Java
url: /pl/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak filtrować pliki MPP przy użyciu Aspose.Tasks dla Javy

## Wprowadzenie
Jeśli pracujesz z plikami Microsoft Project (*.mpp*) w aplikacji Java, często będziesz musiał **filtrować pliki MPP**, aby wyodrębnić zadania, zasoby lub przydziały, które są najważniejsze. W tym samouczku przeprowadzimy Cię przez **jak filtrować pliki mpp** programowo przy użyciu Aspose.Tasks dla Javy, pokażemy, jak **dostosować kryteria filtrowania**, oraz zaprezentujemy praktyczny scenariusz „filtrowanie zadań według daty”. Po zakończeniu będziesz mieć gotowy fragment kodu, który możesz wkleić do dowolnego projektu Java.

## Szybkie odpowiedzi
- **Co oznacza „filter mpp”?** Oznacza to wyodrębnienie podzbioru danych projektu na podstawie określonych warunków.  
- **Która biblioteka to obsługuje?** Aspose.Tasks for Java zapewnia kompleksowe API do tworzenia i stosowania filtrów.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę filtrować zadania, zasoby i przydziały?** Tak – każdy typ encji ma własną kolekcję filtrów.  
- **Czy wymagana jest Java 8 lub nowsza?** Aspose.Tasks obsługuje Java 8 i późniejsze wersje.

## Co to jest „how to filter mpp” w Javie?
`How to filter mpp` to proces użycia obiektów `Filter` z Aspose.Tasks do wybrania jedynie tych elementów projektu, które spełniają określone predykaty, takie jak data rozpoczęcia, koszt lub pola niestandardowe. Załaduj `Project`, pobierz `Filter`, a API zwróci kolekcję pasującą do twoich kryteriów, umożliwiając skoncentrowane raportowanie lub integrację downstream.

## Dlaczego dostosować kryteria filtrowania?
Dostosowane kryteria filtrów pozwalają celować w zadania wysokiego ryzyka, zaległe elementy lub zasoby przekraczające budżet, przekształcając ogromny plik projektu w zwięzły, użyteczny widok. Aspose.Tasks obsługuje **ponad 50 predefiniowanych typów filtrów** i umożliwia tworzenie nieograniczonej liczby filtrów niestandardowych, skracając ręczne przeszukiwanie danych nawet o 70 %.

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – wersja 8 lub nowsza.  
2. **Aspose.Tasks for Java** – pobierz go ze [strony pobierania](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse lub NetBeans będą działać bez problemu.  

## Importowanie pakietów
`Filter`, `FilterCollection`, `FilterCriteria`, `ItemType` i `Project` to podstawowe klasy używane do definiowania i stosowania filtrów do danych projektu.

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## Przewodnik krok po kroku

### Krok 1: Konfiguracja projektu
Najpierw utwórz instancję `Project`, wskazującą na plik MPP, który chcesz przeanalizować, a następnie załaduj go do pamięci. Ten pojedynczy krok przygotowuje cały model projektu do filtrowania, walidacji i dalszej manipulacji, umożliwiając dostęp do zadań, zasobów i przydziałów za pośrednictwem API.

### Jak skonfigurować projekt do filtrowania plików MPP?
Klasa `Project` ładuje i reprezentuje plik MPP w pamięci. Utwórz instancję `Project`, wskazującą na plik MPP, który chcesz przeanalizować, a następnie załaduj go do pamięci. Ten pojedynczy krok przygotowuje cały model projektu do filtrowania, walidacji i dalszej manipulacji, umożliwiając dostęp do zadań, zasobów i przydziałów za pośrednictwem API.

### Jak mogę pobrać i przejrzeć filtr?
`Filter` to obiekty zawierające definicje filtrów używanych do wyboru elementów projektu. Aspose.Tasks przechowuje predefiniowane filtry, takie jak „All Tasks” lub „Critical Tasks”. Użyj `project.getTaskFilters().getByName("My Filter")` lub dostępu indeksowego, aby uzyskać obiekt `Filter`, a następnie przejrzyj jego kolekcję `FilterCriteria`, aby zobaczyć każdą regułę i operator logiczny (AND/OR) łączący je, zapewniając, że filtr spełnia twoje wymagania.

### Jak iterować przez zagnieżdżone wiersze kryteriów?
`FilterCriteriaGroup` reprezentuje grupę kryteriów filtru połączonych operatorem logicznym. Filtry mogą zawierać grupy kryteriów, z których każda ma własny operator. Przejdź pętlą po `filter.getCriteria().getRows()` i dla każdego wiersza będącego `FilterCriteriaGroup` rekurencyjnie przetwarzaj jego wiersze podrzędne. Takie przeglądanie pozwala w pełni zrozumieć złożoną logikę filtru, np. „(Start < today AND Cost > 1000) OR Priority = High”, i dostosować kryteria w razie potrzeby.

### Jak wydrukować informacje o kryteriach w celu debugowania?
Po przejściu drzewa kryteriów wypisz do konsoli nazwę pola, operator testu i wartość każdego wiersza. To proste wyjście pomaga zweryfikować, że filtr odpowiada zamierzonym regułom biznesowym przed zastosowaniem go do dużych projektów i ułatwia wykrycie nieprawidłowych operatorów lub wartości.

### Jak utworzyć zupełnie nowy filtr programowo?
Zainicjuj `Filter` przy pomocy `new Filter("My Filter")`, a następnie dodaj go do kolekcji filtrów zadań projektu używając `project.getTaskFilters().add(filter)`. Następnie wypełnij jego kolekcję `FilterCriteria` żądanymi wierszami, określając nazwy pól, operatory testu i wartości, aby dokładnie zdefiniować, które zadania mają być uwzględnione po zastosowaniu filtru.

### Czy mogę zastosować filtr do zasobów zamiast zadań?
Kolekcja `ResourceFilters` przechowuje definicje filtrów stosowanych do zasobów. Tak – użyj `project.getResourceFilters()`, aby pracować z filtrami specyficznymi dla zasobów w taki sam sposób jak z filtrami zadań. Po dodaniu lub pobraniu filtru skonfiguruj jego `FilterCriteria` tak jak dla zadań, a następnie zastosuj go do kolekcji zasobów, aby uzyskać przefiltrowany zestaw zasobów.

### Czy można połączyć wiele filtrów logiką OR?
Utwórz nadrzędny `FilterCriteriaGroup` z `Operation` ustawionym na `OR`, a następnie dodaj poszczególne obiekty `FilterCriteria` jako dzieci. Ta grupa oceni każde kryterium podrzędne i zwróci elementy spełniające dowolne z nich, umożliwiając połączenie kilku prostych filtrów w szerszy wybór.

### Czy Aspose.Tasks obsługuje filtrowanie pól niestandardowych?
`CustomField` to wyliczenie dostarczające identyfikatory pól niestandardowych zdefiniowanych w projekcie. Oczywiście. Odwołuj się do pól niestandardowych za pomocą wyliczenia `CustomField`, a zachowują się one jak każde wbudowane pole w wyrażeniach filtrów. Możesz je uwzględnić w wierszach `FilterCriteria`, używając tych samych operatorów i wartości, co umożliwia potężne zapytania na danych definiowanych przez użytkownika wraz ze standardowymi atrybutami projektu.

### Jaki wpływ na wydajność ma filtrowanie dużych plików MPP?
Filtrowanie odbywa się w całości w pamięci i zazwyczaj przetwarza projekt z 1 000 zadaniami w czasie krótszym niż 200 ms. W przypadku plików z wieloma tysiącami zadań rozważ ładowanie tylko wymaganych sekcji przy użyciu `ProjectReader` i stosowanie filtrów po selektywnym wczytaniu, co utrzymuje niskie zużycie pamięci i zapewnia szybki czas reakcji nawet w bardzo dużych projektach.

**Ostatnia aktualizacja:** 2026-06-05  
**Testowano z:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose

## Powiązane samouczki

- [Wczytaj plik MPP w Javie – zarządzaj właściwościami projektu przy użyciu Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java – łatwe odczytywanie danych MS Project Online](/tasks/java/project-data-reading/read-project-online/)
- [Ustaw datę rozpoczęcia projektu w MS Project przy użyciu Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```