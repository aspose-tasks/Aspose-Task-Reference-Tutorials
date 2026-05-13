---
date: 2026-01-10
description: Dowiedz się, jak odczytywać skalę stawek i zarządzać przydziałami zasobów
  w Aspose.Tasks dla Javy. Zdefiniuj zasób materialny, jak ustawić skalę oraz przydzielić
  zasoby do zadania.
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak odczytać skalę stawek i zapisać skalę stawek dla przydziałów zasobów w
  Aspose.Tasks
url: /pl/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać skalę stawek i zapisać skalę stawek dla przydziałów zasobów w Aspose.Tasks

W tym samouczku odkryjesz **jak odczytać skalę stawek** i dostosować ją dla przydziałów zasobów przy użyciu Aspose.Tasks for Java. Niezależnie od tego, czy tworzysz harmonogram, narzędzie raportujące, czy po prostu potrzebujesz automatyzować aktualizacje projektów, opanowanie manipulacji skalą stawek daje Ci precyzyjną kontrolę nad zasobami materiałowymi i roboczymi.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do obsługi stawek?** `ResourceAssignment` z właściwością `Asn.RATE_SCALE`.  
- **Które wyliczenie definiuje opcje skali?** `RateScaleType` (Day, Week, Month, itp.).  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa licencja ewaluacyjna działa w testach; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę zmienić skalę po zapisaniu?** Tak – wczytaj projekt ponownie i zmodyfikuj `Asn.RATE_SCALE` jak pokazano.  
- **ługiwane IDE?** Każde środowisko Java IDE (IntelliJ IDEA, Eclipse, NetBeans) może kompilować kod.

## Co to jest skala stawek?
Skala stawek określa jednostkę czasu (dzień, tydzień, miesiąc, itp.), do której stosowana jest stawka kosztowa zasobu. Dostosowanie skali pozwala dokładnie modelować zużycie materiałów lub nakład pracy.

## Dlaczego odczytywać i zapisywać skalę stawek?
Odczyt bieżącej skali pomaga audytować istniejące harmonogramy, natomiast zapis nowej skali pozwala dopasować zasoby do zasad rozliczania lub zużycia projektu. Jest to szczególnie przydatne przy **definiowaniu kosztów zasobów materiałowych** lub gdy trzeba **ustawić skalę** dla niestandardowych kalendarzy pracy.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. **Środowisko programistyczne Java** – zainstalowany JDK 8 lub nowszy.  
2. **Biblioteka Aspose.Tasks for Java** – pobierz i zainstaluj bibliotekę z [tutaj](https://releases.aspose.com/tasks/java/).

## Importowanie pakietów
Najpierw zaimportuj niezbędne klasy Aspose.Tasks.

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

## Krok 2: Wczytaj plik projektu
Wczytaj istniejący plik Microsoft Project, z którym chcesz pracować.

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
Tutaj **definiujemy zasób materiałowy** oraz zwykły zasób roboczy. Zwróć uwagę na użycie `ResourceType.Material` dla zasobu typu materiałowego.

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
- **Niezgodność UID** – Przy pobieraniu przydziałów po UID, upewnij się, że wartości UID pasują do tych przydzielonych podczas tworzenia.  
- **Nieprawidłowy typ zasobu** – Użycie `ResourceType.Material` dla zasobu roboczego spowoduje nieoczekiwane zachowanie obliczeń stawek.  
- **Format zapisu** – Zawsze zapisuj używając `SaveFileFormat.Mpp` (lub innego obsługiwanego formatu), aby zachować pola niestandardowe, takie jak skala stawek.

## Zakończenie
Zarządzanie i kontrola skali stawek dla przydziałów zasobów w Aspose.Tasks for Java jest prosta, gdy znasz odpowiednie klasy i właściwości. Postępując zgodnie z tym przewodnikiem, możesz **odczytać informacje o stawkach**, **zdefiniować obiekty zasobów materiałowych**, **ustawić skalę** oraz **przypisać zasoby do zadania** z pewnością.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Tasks for Java w dowolnym IDE Java?**  
A: Tak, Aspose.Tasks for Java jest kompatybilny ze wszystkimi głównymi IDE Java, w tym IntelliJ IDEA, Eclipse i NetBeans.

**Q: Czy Aspose.Tasks obsługuje inne formaty plików poza MPP?**  
A: Tak, Aspose.Tasks obsługuje różne formaty plików, w tym MPP, XML i HTML.

**Q: Czy Aspose.Tasks jest odpowiedni do zarządzania projektami na poziomie przedsiębiorstwa?**  
A: Absolutnie, Aspose.Tasks oferuje kompleksowe funkcje do zarządzania projektami każdej skali, co czyni go odpowiednim do zarządzania projektami na poziomie przedsiębiorstwa.

**Q: Czy mogę dalej dostosowywać przydziały zasobów poza skalą stawek?**  
A: Tak, Aspose.Tasks zapewnia rozbudowane możliwości dostosowywania przydziałów zasobów, w tym kosztów, pracy i korekt czasu trwania.

**Q: Czy istnieje forum społecznościowe wsparcia Aspose.Tasks?**  
A: Tak, wsparcie i interakcję z innymi użytkownikami można znaleźć na forum Aspose.Tasks [tutaj](https://forum.aspose.com/c/tasks/15).

---

**Ostatnia aktualizacja:** 2026-01-10  
**Testowano z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}