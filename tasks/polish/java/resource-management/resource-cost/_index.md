---
date: 2026-01-15
description: Dowiedz się, jak pracować z zaplanowanymi kosztami budżetowymi w plikach
  Microsoft Project przy użyciu Aspose.Tasks dla Javy. Postępuj zgodnie z naszym przewodnikiem
  krok po kroku.
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Praca kosztowa budżetowana zaplanowana przy użyciu Aspose.Tasks dla Javy
url: /pl/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# planowany koszt pracy zaplanowanej z Aspose.Tasks for Java

## Wprowadzenie

Zarządzanie **planowanym kosztem pracy zaplanowanej** (BCWS) jest niezbędne, aby projekt pozostawał na właściwej drodze i aby prognoza finansowa była zgodna z planowaną pracą. W Microsoft Project BCWS oznacza kwotę pieniędzy, którą powinno się było wydać za pracę zaplanowaną do określonej daty. Aspose.Tasks for Java daje pełną programistyczną kontrolę nad tymi wartościami, umożliwiając odczyt, modyfikację i raportowanie kosztów zasobów bez ręcznego otwierania pliku .mpp. W tym samouczku przeprowadzimy kompletny przykład, który pokaże, jak wczytać projekt, przeiterować jego zasoby i wyświetlić planowany koszt pracy zaplanowanej wraz z innymi kluczowymi metrykami kosztowymi.

## Szybkie odpowiedzi
- **Co oznacza BCWS?** Budgeted Cost Work Scheduled – planowany koszt pracy zaplanowanej do tej daty.  
- **Która właściwość API pobiera BCWS?** `Rsc.BCWS` w obiekcie `Resource`.  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa licencja ewaluacyjna wystarcza do testów; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę modyfikować wartości BCWS?** Tak, możesz ustawić `Rsc.BCWS` tak jak każde inne pole numeryczne.  
- **Obsługiwane wersje Project?** Wszystkie wersje Microsoft Project od 2000 do najnowszego formatu .mpp.

## Co to jest planowany koszt pracy zaplanowanej?

**Budgeted Cost Work Scheduled (BCWS)** to miara wydajności odzwierciedlająca koszt, który powinien zostać poniesiony za pracę zaplanowaną do określonego momentu w czasie. Jest to podstawa zarządzania wartością wypracowaną (EVM) i pomaga menedżerom projektów porównywać planowane i rzeczywiste wydatki.

## Wymagania wstępne

Zanim przejdziesz do kodu, upewnij się, że masz:

1. Solidne podstawy języka Java.  
2. Aspose.Tasks for Java dodane do projektu (Maven/Gradle lub JAR).  
3. Plik Microsoft Project (`.mpp`) zawierający zasoby z danymi kosztowymi (np. *ResourceCosts.mpp*).

## Import pakietów

Najpierw zaimportuj klasy Aspose.Tasks niezbędne do obsługi projektów i zasobów:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Krok 1: Zdefiniuj katalog danych

```java
String dataDir = "Your Data Directory";
```

Zastąp `"Your Data Directory"` absolutną lub względną ścieżką, w której znajduje się *ResourceCosts.mpp*.

## Krok 2: Wczytaj plik MS Project

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

Konstruktor `Project` odczytuje plik .mpp i buduje reprezentację w pamięci, którą możesz zapytać.

## Krok 3: Przejdź przez zasoby

```java
for (Resource res : prj.getResources()) {
```

Ta pętla przechodzi przez każdy zasób zdefiniowany w projekcie, dając dostęp do jego pól kosztowych.

## Krok 4: Sprawdź nazwę zasobu i koszty

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

Wewnątrz bloku `if` wykonujemy:

* Drukujemy **całkowity koszt** (`Rsc.COST`).  
* Drukujemy **rzeczywisty koszt wykonanego pracy** (`Rsc.ACWP`).  
* Drukujemy **planowany koszt pracy zaplanowanej** (`Rsc.BCWS`) – główną metrykę, na której się koncentrujemy.  
* Drukujemy **planowany koszt wykonanego pracy** (`Rsc.BCWP`).

Te cztery wartości dają szybki przegląd sytuacji finansowej projektu.

## Dlaczego monitorowanie planowanego kosztu pracy zaplanowanej ma znaczenie

* **Wczesne ostrzeżenie:** Jeśli BCWS jest znacznie wyższy niż rzeczywisty koszt, możesz nadmiernie przydzielać zasoby.  
* **Analiza wartości wypracowanej:** BCWS jest kluczowym wejściem do obliczania odchylenia kosztowego (CV) i odchylenia harmonogramu (SV).  
* **Prognozowanie:** Dokładne dane BCWS pomagają przewidywać przyszłe potrzeby przepływu gotówki i wspierają raportowanie interesariuszom.

## Typowe problemy i rozwiązywanie

| Objaw | Prawdopodobna przyczyna | Naprawa |
|-------|--------------------------|---------|
| `null` wydrukowane dla BCWS | Zasób nie ma zdefiniowanej tabeli stawek kosztowych | Zdefiniuj tabelę stawek kosztowych dla zasobu w Microsoft Project lub ustaw ją programowo poprzez `Rsc.COST_RATE_TABLE` |
| `ArrayIndexOutOfBoundsException` przy iteracji zasobów | Plik projektu uszkodzony lub zawiera puste wpisy zasobów | Zweryfikuj plik .mpp w Microsoft Project i usuń puste zasoby |
| Nieoczekiwane wartości (np. ujemny BCWS) | Pola niestandardowe nadpisują standardowe pola kosztowe | Upewnij się, że odwołujesz się do standardowego `Rsc.BCWS`, a nie do pola niestandardowego o tej samej nazwie |

## Najczęściej zadawane pytania

**P: Czy mogę zaktualizować wartość BCWS programowo?**  
O: Tak. Użyj `res.set(Rsc.BCWS, newValue)` i następnie zapisz projekt metodą `prj.save("Updated.mpp")`.

**P: Czy Aspose.Tasks obsługuje projekty wielowalutowe?**  
O: Absolutnie. Pola kosztowe respektują ustawienia waluty zdefiniowane w pliku projektu.

**P: Czy istnieje sposób eksportu tych metryk kosztowych do CSV?**  
O: Możesz przeiterować zasoby i zapisać wartości do `StringBuilder` lub użyć biblioteki CSV do wygenerowania pliku.

**P: Czym różni się BCWS od BCWP?**  
O: BCWS to planowany koszt pracy zaplanowanej, natomiast BCWP (Budgeted Cost Work Performed) odzwierciedla planowany koszt pracy, która faktycznie została ukończona.

**P: Czy potrzebna jest specjalna licencja do odczytu danych kosztowych?**  
O: Licencja ewaluacyjna zapewnia pełny dostęp do odczytu i zapisu; licencja komercyjna jest wymagana w środowiskach produkcyjnych.

## Zakończenie

Korzystając z Aspose.Tasks for Java, uzyskujesz precyzyjny, programistyczny dostęp do **planowanego kosztu pracy zaplanowanej** oraz innych istotnych metryk kosztowych. To umożliwia budowanie własnych pulpitów, automatyzację raportów Earned Value i utrzymanie projektów pod kontrolą finansową – wszystko bez ręcznej interakcji z Microsoft Project.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-15  
**Testowane z:** Aspose.Tasks for Java 24.12 (latest)  
**Autor:** Aspose