---
date: 2026-01-10
description: Dowiedz się, jak zatrzymać przydział, zarządzać przydziałami zasobów
  i zobaczyć przykład przydziału zasobów w Aspose.Tasks for Java dzięki temu samouczkowi
  krok po kroku.
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak zatrzymać przydział i wznowić przydziały zasobów w Aspose.Tasks
url: /pl/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak można przydział i wznowić przydziały zasobów w Aspose.Tasks

## Wstęp
W tym samouczku **dowiesz się, jak przydział** i później przejdź do zmiany przy użyciu Aspose.Tasks for Java. Aspose.Tasks to API Java, które umożliwiają korzystanie z plików w Java, fizycznie dostępnych w Microsoft Project oraz przydziałami zarządzania bez konieczności posiadania go Microsoft Project. Przejdziemy krok po kroku przez każdy etap, uzasadnimy, dlaczego każda linia ma znaczenie, i jest to praktyczne, które jest rozpoznawane w odpowiednich projektach.

## Szybkie odpowiedzi
- **Co oznacza „zatrzymaj przypisanie”?** do przydziału zasobu jako podstawowego nieaktywnego od danych daty dostępu.
- **Czy mogę później opóźnić ten sam przydział?** Tak, ustawiając datę aktualizacji w tym samym miejscu.
- **Czy jest dostępny Microsoft Project, aby dostosować tego API?** Nie, Aspose.Tasks działa od Microsoft Project.
- **Jaka wersja Javy jest wymagana?** Zalecana jest Java8 lub terazsza.
- **Gdzie można odebrać bibliotekę?** Ze strony pobierania Aspose.Tasks Java.

## Co to jest „jak zatrzymać przypisanie” w kontekście Aspose.Tasks?
Zatrzymanie przydziału użytkowania planistę, aby zapewnić obciążenie przydzielonej zasobowi po **dacie dostępu** aż do **data wznowienia** (jeśli istnieje). Jest to dodatek do użytku przy urlopach, przestojów sprzętu lub pierwszego dnia, w którym zasób nie powinien być uznawany za aktywny.

## Dlaczego warto używać Aspose.Tasks do zarządzania przypisaniami zasobów?
- **Brak konieczności korzystania z Microsoft Project** – pracuj bezpośrednio z plikami .mpp.
- **Pełna kontrola nad danymi** – możesz zaprogramować datę opóźnienia, datę aktualizacji i je zachować.
- **Międzyplatformowy** – działa na każdym systemie uruchamiającym obsługującym Javę.
- **Bogate API** – udostępnienie *przykład przypisania zasobów*, które można rozbudować o własne raporty.

## Warunki wstępne
Zanim uruchomimy, wykonamy, że masz:

- Zainstalowany zestaw Java Development Kit (JDK) na swoim komputerze.
- Pobraną bibliotekę Aspose.Zadania dla Java. Możesz ją zabrać z [tutaj](https://releases.aspose.com/tasks/java/).
- Podstawową przyjemność programowania w Javie.

## Importuj pakiety
Ostatni zaimportuj niezbędny pakiety do swojego projektu Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Krok 1: Załaduj plik projektu
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Tutaj **odczytujemy plik projektu Java** w formacie (`.mpp`) i tworzymy obiekt `Project`, który daje dostęp do wszystkich danych projektu, w tym przydziałów zasobów.

## Krok 2: Przejrzyj przypisania zasobów
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Ustawiamy **minimalną datę**, aby odfiltrować daty zastępcze, a następnie iterujemy po każdym przydziale. To typowy wzorzec *resource assignment example* używany, gdy trzeba przejrzeć lub zmodyfikować przydziały.

## Krok 3: Sprawdź daty zakończenia i wznowienia
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

W tym bloku **sprawdzamy datę rejestracji** i **data odnowienia** dla każdego przydziału. Jeśli dane są wcześniejsza niż nasz `minDate`, następujemy ją jako nieustawioną („NA”`); w razie wypadku wyświetlamy rzeczywistą datę. Ta logika jest równa do **zarządzania przydziałami zasobów** prawidłowych.

## Typowe problemy i rozwiązania
- **Daty zerowe** – `ra.get(Asn.STOP)` może oznaczać `null`. Zabezpieczenie się przed tym, dodając null przed wywołaniem `.before(minDate)`.
- **Nieprawidłowa ścieżka pliku** – następuje, że `dataDir` kończy się separatorem systemowym (`/` lub `\\`) kontrolowanym dla systemu operacyjnego.
- **Niezgodność wersji** – dostępna najnowsza wersja Aspose.Tasks dla Java, aby uzyskać brakujące wartości wyliczeniowe.

## Często zadawane pytania

**P: Jak programowo ustawić datę zakończenia zadania?**
O: Użyj `ra.set(Asn.STOP, yourDateObject);`, gdzie `yourDateObject` to `java.util.Date`.

**P: Co się stanie, jeśli data wznowienia jest wcześniejsza niż data zakończenia?**
O: API nie wymusza kolejności chronologicznej; jednak harmonogram potraktuje zadanie jako aktywne dopiero po późniejszej z dwóch dat, dlatego należy samodzielnie zweryfikować daty.

**P: Czy mogę filtrować zadania tylko do tych, które mają ustawioną datę zakończenia?**
O: Tak, przeprowadź iterację przez `prj.getResourceAssignments()` i sprawdź, czy `ra.get(Asn.STOP) != null`.

**P: Czy można usunąć raz ustawioną datę zakończenia?**
O: Ustaw datę końcową na „null” za pomocą „ra.set(Asn.STOP, null);”, a następnie zapisz projekt.

**P: Czy Aspose.Tasks obsługuje inne pola związane z datą, takie jak początek, koniec lub faktyczny początek?**
O: Absolutnie. Wyliczenie `Asn` zapewnia stałe dla wszystkich pól przypisania, takie jak `Asn.START`, `Asn.FINISH` itp.

## Wniosek
Po wykonaniu tych kroków, teraz wiesz **jak przydział**, sprawdzenie daty zakończenia/wznowienia i powtórzenie przydziału w razie potrzeby. Ta funkcjonalność pozwala **zarządzać przydziałami zasobów**, szczegółowo określając, w szczególności w sytuacjach takich jak zasoby urlopowe czy przestoje sprzętu. Śmiało rozbudowuj przykład, aby aktualizować daty, generować raporty lub integrować go z własną logiką internetową.

---

**Ostatnia aktualizacja:** 2026-01-10
**Testowano z:** Aspose.Tasks dla Java 24.12
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}