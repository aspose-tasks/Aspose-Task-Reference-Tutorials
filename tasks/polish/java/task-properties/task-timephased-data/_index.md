---
date: 2026-02-28
description: Dowiedz się, jak używać Aspose.Tasks for Java do zarządzania danymi czasowymi
  zadań, pobierz bibliotekę, wypróbuj ją za darmo i usprawnij śledzenie projektów.
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak korzystać z Aspose.Tasks do zarządzania danymi czasowymi zadań (Java)
url: /pl/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose.Tasks do danych czasowych zadań

## Wprowadzenie
Jeśli szukasz **sposobu użycia Aspose**, aby mieć pełną kontrolę nad harmonogramem projektu, trafiłeś we właściwe miejsce. Precyzyjne śledzenie danych czasowych zadań jest podstawą skutecznego zarządzania projektami, a Aspose.Tasks for Java dostarcza narzędzia potrzebne do automatyzacji tego procesu. W tym samouczku przeprowadzimy Cię przez kompletny przykład od początku do końca, pokazujący, jak używać Aspose.Tasks do tworzenia projektu, przydzielania zasobów, ustalania bazowych planów oraz pobierania i wyświetlania danych czasowych.

## Szybkie odpowiedzi
- **Co oznacza „dane czasowe” (timephased data)?** To dane podzielone na przedziały czasowe (dni, tygodnie, miesiące), które pokazują pracę, koszt lub pozostałą pracę w ramach osi czasu projektu.  
- **Która biblioteka zapewnia tę funkcjonalność?** Aspose.Tasks for Java.  
- **Czy potrzebna jest licencja do uruchomienia przykładu?** Darmowa wersja próbna wystarczy do rozwoju; licencja jest wymagana w środowisku produkcyjnym.  
- **Jakiej wersji Javy potrzebuję?** Java 8 lub nowsza.  
- **Czy mogę wyeksportować wyniki do Excela?** Tak – możesz iterować kolekcję `TimephasedData` i zapisywać wartości w dowolnym potrzebnym formacie.

## Co to są dane czasowe zadania?
Dane czasowe zadania reprezentują ilość pracy (lub kosztu) zaplanowaną dla zadania w każdym przedziale czasu kalendarza projektu. Umożliwiają one podgląd rozkładu pracy, wykrycie nadmiernego obciążenia oraz porównanie planowanego i rzeczywistego postępu.

## Dlaczego warto używać Aspose.Tasks do zarządzania danymi czasowymi?
- **Pełna kontrola** – programowo twórz, modyfikuj i odczytuj informacje czasowe bez otwierania Microsoft Project.  
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę.  
- **Brak zależności COM** – idealne do automatyzacji po stronie serwera.  
- **Bogate API** – obsługuje bazowe plany, kontury pracy i pola niestandardowe od razu po wyjęciu z pudełka.

## Wymagania wstępne
Zanim przejdziesz do kodu, upewnij się, że masz:

- **Środowisko programistyczne Java** – zainstalowane JDK 8+ i skonfigurowane `JAVA_HOME`.  
- **Bibliotekę Aspose.Tasks for Java** – pobierz i dołącz bibliotekę Aspose.Tasks do swojego projektu. Bibliotekę znajdziesz [tutaj](https://releases.aspose.com/tasks/java/).  
- **Katalog dokumentów** – folder na Twoim komputerze, w którym będą odczytywane i zapisywane pliki przykładowego projektu (`project.xml`).

## Importowanie pakietów
W swoim projekcie Java zaimportuj niezbędne klasy Aspose.Tasks:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Krok 1: Ustaw datę rozpoczęcia projektu
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Wyjaśnienie:* Tworzymy instancję `Project`, inicjalizujemy `Calendar` z żądaną datą rozpoczęcia i przypisujemy ją do właściwości `START_DATE` projektu.

## Krok 2: Zdefiniuj zadanie i zasób
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Wyjaśnienie:* Dodajemy nowe zadanie o nazwie **Task** pod zadaniem głównym. Tworzymy także zasób o nazwie **Rsc** i ustawiamy jego standardowe oraz nadgodzinowe stawki.

## Krok 3: Ustaw czas trwania zadania
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Wyjaśnienie:* Zadanie jest planowane na **6 dni**.

## Krok 4: Przypisz zasób do zadania
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Wyjaśnienie:* Wcześniej zdefiniowany zasób jest powiązany z zadaniem za pomocą `ResourceAssignment`.

## Krok 5: Skonfiguruj przydział zasobu
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Wyjaśnienie:* Ustawiamy daty zatrzymania i wznowienia przydziału (używając wartości zastępczej) oraz stosujemy kontur pracy **Back‑Loaded**, który przenosi większą część pracy na koniec przydziału.

## Krok 6: Ustaw bazowy plan
```java
project.setBaseline(BaselineType.Baseline);
```
*Wyjaśnienie:* Utworzenie bazowego planu pozwala później porównać wartości planowane z rzeczywistymi.

## Krok 7: Zaktualizuj postęp zadania
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Wyjaśnienie:* Zadanie jest oznaczone jako **50 % ukończone**, co wpływa na obliczenia pozostałej pracy.

## Krok 8: Pobierz dane czasowe
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Wyjaśnienie:* To wywołanie pobiera **pozostałą pracę** dla przydziału, podzieloną na przedziały czasowe projektu.

## Krok 9: Wyświetl dane czasowe
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Wyjaśnienie:* Po prostu wypisujemy liczbę wpisów czasowych oraz wartość pierwszego wpisu. W rzeczywistym scenariuszu iterowałbyś listę i eksportował dane do raportu lub interfejsu użytkownika.

## Typowe problemy i rozwiązania
- **NullPointerException przy `getTimephasedData`** – Upewnij się, że daty `START` i `FINISH` przydziału są ustawione przed wywołaniem metody.  
- **Nieprawidłowy kontur pracy** – Sprawdź, czy wybrany `WorkContourType` odpowiada Twojej strategii planowania; `BackLoaded` to tylko jedna z kilku dostępnych opcji.  
- **Bazowy plan nie odzwierciedla zmian** – Pamiętaj, aby wywołać `project.setBaseline` *po* zdefiniowaniu zadań, zasobów i przydziałów.

## Najczęściej zadawane pytania
### P: Czy mogę używać Aspose.Tasks for Java w dowolnym projekcie Java?
O: Tak, Aspose.Tasks for Java jest kompatybilny z każdym projektem opartym na Javie.

### P: Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Tasks for Java?
O: Odwiedź [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) w celu uzyskania pomocy i dyskusji.

### P: Czy dostępna jest darmowa wersja próbna Aspose.Tasks for Java?
O: Tak, darmową wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

### P: Jak mogę uzyskać tymczasową licencję dla Aspose.Tasks for Java?
O: Tymczasową licencję możesz nabyć [tutaj](https://purchase.aspose.com/temporary-license/).

### P: Gdzie mogę kupić Aspose.Tasks for Java?
O: Zakup Aspose.Tasks for Java jest możliwy [tutaj](https://purchase.aspose.com/buy).

---

**Ostatnia aktualizacja:** 2026-02-28  
**Testowane z:** Aspose.Tasks for Java 24.12 (najnowsza w momencie pisania)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}