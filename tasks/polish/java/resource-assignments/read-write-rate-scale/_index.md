---
date: 2026-06-10
description: Dowiedz się, jak odczytać rate i jak zapisać Rate Scale dla resource
  assignments przy użyciu Aspose.Tasks dla Java. Obsługuje material resources, multiple
  formats oraz large projects.
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: Odczyt i zapis Rate Scale dla Resource Assignments w Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak odczytać Rate Scale i zapisać Rate Scale dla resource assignments w Aspose.Tasks
url: /pl/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać skalę stawek i zapisać skalę stawek dla przydziałów zasobów w Aspose.Tasks

W tym samouczku odkryjesz **jak odczytać skalę stawek** i dostosować ją dla przydziałów zasobów przy użyciu Aspose.Tasks dla Javy. Niezależnie od tego, czy tworzysz harmonogram, narzędzie raportujące, czy po prostu potrzebujesz automatyzować aktualizacje projektu, opanowanie manipulacji skalą stawek daje Ci precyzyjną kontrolę nad zasobami materialnymi i roboczymi.

## Szybkie odpowiedzi
`ResourceAssignment` łączy zadanie z zasobem i przechowuje dane specyficzne dla przydziału.  
`Asn` zawiera stałe dla pól przydziału, w tym `RATE_SCALE`.  
`RateScaleType` wylicza możliwe jednostki czasu dla skalowania stawek.  

- **Jaka jest główna klasa obsługująca skalę stawek?** `ResourceAssignment` z właściwością `Asn.RATE_SCALE`.  
- **Które wyliczenie definiuje opcje skali?** `RateScaleType` (Day, Week, Month, itp.).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa licencja ewaluacyjna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić skalę po zapisaniu?** Tak – wczytaj projekt ponownie i zmodyfikuj `Asn.RATE_SCALE` jak pokazano.  
- **Obsługiwane IDE?** Każde IDE Java (IntelliJ IDEA, Eclipse, NetBeans) może skompilować kod.

## Jak odczytać skalę stawek dla przydziałów zasobów?

Załaduj projekt, znajdź żądany `ResourceAssignment` i wywołaj `getRateScale()` – zwróci to wartość `RateScaleType`, która informuje, czy stawka jest stosowana dziennie, tygodniowo, miesięcznie lub w innej jednostce. Odpowiedź jest natychmiastowa i wymaga tylko dwóch wywołań API, co czyni ją idealną dla skryptów audytowych lub wyświetleń UI.

## Jak zapisać skalę stawek dla przydziałów zasobów?

Utwórz lub pobierz obiekt `ResourceAssignment`, ustaw jego właściwość `Asn.RATE_SCALE` na żądany `RateScaleType` (np. `RateScaleType.Week`), a następnie zapisz projekt. Ta pojedyncza zmiana właściwości automatycznie aktualizuje kalkulacje kosztów i jest zachowywana we wszystkich obsługiwanych formatach plików. Po ustawieniu skali możesz także potrzebować dostosować standardową stawkę zasobu lub stawkę nadgodzin, aby odzwierciedlić nową jednostkę czasu, zapewniając dokładność obliczeń kosztów.

## Co to jest skala stawek?

Skala stawek określa jednostkę czasu (dzień, tydzień, miesiąc, itp.), do której stosowana jest kosztowa stawka zasobu. Dostosowanie skali pozwala precyzyjnie modelować zużycie materiałów lub nakład pracy. Na przykład ustawienie skali na Week oznacza, że stawka kosztowa jest interpretowana jako koszt na tydzień, a całkowity koszt zadania jest obliczany na podstawie liczby tygodni, w których zasób jest przydzielony.

## Dlaczego odczytywać i zapisywać skalę stawek?

Odczyt bieżącej skali pomaga audytować istniejące harmonogramy, natomiast zapis nowej skali pozwala dopasować zasoby do polityk rozliczeniowych lub konsumpcyjnych projektu. Jest to szczególnie przydatne przy **definiowaniu kosztów zasobów materialnych** lub gdy trzeba **ustawić skalę** dla niestandardowych kalendarzy pracy.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:
1. **Java Development Environment** – zainstalowany JDK 8 lub nowszy.  
2. **Aspose.Tasks for Java Library** – pobierz i zainstaluj bibliotekę z [here](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Klasa `ResourceAssignment` reprezentuje połączenie między zadaniem a zasobem, natomiast `RateScaleType` wylicza możliwe jednostki czasu dla stawki. Zaimportuj niezbędne klasy Aspose.Tasks przed rozpoczęciem kodowania.  

`Project` jest głównym obiektem, który ładuje i zapisuje pliki Microsoft Project.  
`Resource` definiuje zasób projektu, taki jak praca lub materiał.  
`ResourceType` wylicza, czy zasób jest pracą czy materiałem.  
`Task` reprezentuje element pracy w harmonogramie projektu.  
`SaveFileFormat` wylicza format wyjściowy przy zapisywaniu projektu.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Krok 1: Skonfiguruj projekt Java
Utwórz projekt Maven lub Gradle i dodaj plik JAR Aspose.Tasks do ścieżki klas. Ten krok zapewnia, że kompilator może znaleźć zaimportowane klasy.

## Krok 2: Załaduj plik projektu
Załaduj istniejący plik Microsoft Project, z którym chcesz pracować.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Krok 3: Dodaj zadanie
Utwórz nowe zadanie, które później otrzyma przydziały zasobów.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Krok 4: Zdefiniuj zasoby
Tutaj **definiujemy zasób materialny** oraz regularny zasób roboczy. Zauważ użycie `ResourceType.Material` dla zasobu typu materiałowego.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Krok 5: Przypisz zasoby do zadania
Teraz **przypisujemy zasoby do zadania** i określamy **jak ustawić skalę** używając `RateScaleType.Week`. To ilustruje zarówno odczyt, jak i zapis skali stawek.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Krok 6: Zapisz projekt
Zachowaj zmiany w nowym pliku, aby później móc zweryfikować zapisaną skalę stawek.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Krok 7: Pobierz przydziały zasobów
Wczytaj ponownie zapisany projekt i **odczytaj skalę stawek**, aby potwierdzić, że została zapisana poprawnie.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Częste pułapki i wskazówki
- **UID Mismatch** – Przy pobieraniu przydziałów po UID, upewnij się, że wartości UID są zgodne z tymi przypisanymi podczas tworzenia.  
- **Incorrect Resource Type** – Użycie `ResourceType.Material` dla zasobu roboczego spowoduje nieoczekiwane zachowanie obliczeń stawek.  
- **Saving Format** – Zawsze zapisuj używając `SaveFileFormat.Mpp` (lub innego obsługiwanego formatu), aby zachować pola niestandardowe, takie jak skala stawek.  
- **Large Projects** – Aspose.Tasks może przetwarzać pliki z **500+ stronami** bez ładowania całego dokumentu do pamięci, dzięki architekturze strumieniowej.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks dla Java w dowolnym IDE Java?**  
A: Tak, Aspose.Tasks dla Java jest kompatybilny ze wszystkimi głównymi IDE Java, w tym IntelliJ IDEA, Eclipse i NetBeans.

**Q: Czy Aspose.Tasks obsługuje inne formaty plików poza MPP?**  
A: Tak, Aspose.Tasks obsługuje różne formaty plików, w tym MPP, XML i HTML.

**Q: Czy Aspose.Tasks jest odpowiedni dla zarządzania projektami na poziomie przedsiębiorstwa?**  
A: Absolutnie, Aspose.Tasks oferuje kompleksowe funkcje do zarządzania projektami każdej skali, co czyni go odpowiednim dla zarządzania projektami na poziomie przedsiębiorstwa.

**Q: Czy mogę dalej dostosowywać przydziały zasobów poza skalą stawek?**  
A: Tak, Aspose.Tasks zapewnia rozbudowane możliwości dostosowywania przydziałów zasobów, w tym kosztów, pracy i korekt czasu trwania.

**Q: Czy istnieje forum społecznościowe wsparcia Aspose.Tasks?**  
A: Tak, możesz znaleźć wsparcie i interakcję z innymi użytkownikami na forum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Powiązane samouczki

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}