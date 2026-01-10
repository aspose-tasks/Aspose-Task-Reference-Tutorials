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

# Jak zatrzymać przydział i wznowić przydziały zasobów w Aspose.Tasks

## Introduction
W tym samouczku **dowiesz się, jak zatrzymać przydział** i później go wznowić przy użyciu Aspose.Tasks for Java. Aspose.Tasks to potężne API Java, które umożliwia odczytywanie plików projektów w formacie Java, manipulowanie danymi Microsoft Project oraz zarządzanie przydziałami zasobów bez konieczności posiadania zainstalowanego Microsoft Project. Przejdziemy krok po kroku przez każdy etap, wyjaśnimy, dlaczego każda linia ma znaczenie, i podamy praktyczne wskazówki, które możesz zastosować w rzeczywistych projektach.

## Quick Answers
- **Co oznacza „stop assignment”?** Oznacza to przydział zasobu jako tymczasowo nieaktywny od określonej daty zatrzymania.  
- **Czy mogę później wznowić ten sam przydział?** Tak, ustawiając datę wznowienia w tym samym przydziale.  
- **Czy potrzebuję Microsoft Project, aby używać tego API?** Nie, Aspose.Tasks działa niezależnie od Microsoft Project.  
- **Jaka wersja Javy jest wymagana?** Zalecana jest Java 8 lub nowsza.  
- **Gdzie mogę pobrać bibliotekę?** Ze strony oficjalnej pobierania Aspose.Tasks Java.

## What is “how to stop assignment” in the context of Aspose.Tasks?
Zatrzymanie przydziału informuje planistę, aby ignorował pracę przydzieloną zasobowi po **dacie zatrzymania** aż do **daty wznowienia** (jeśli istnieje). Jest to przydatne przy obsłudze urlopów, przestojów sprzętu lub dowolnego okresu, w którym zasób nie powinien być uznawany za aktywny.

## Why use Aspose.Tasks to manage resource assignments?
- **Brak potrzeby Microsoft Project** – pracuj bezpośrednio z plikami .mpp.  
- **Pełna kontrola nad datami** – możesz programowo sprawdzać datę zatrzymania, datę wznowienia i je modyfikować.  
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę.  
- **Bogate API** – udostępnia *resource assignment example*, które możesz rozbudować o własne raporty.

## Prerequisites
Zanim zaczniemy, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK) na swoim komputerze.  
- Pobraną bibliotekę Aspose.Tasks for Java. Możesz ją pobrać z [tutaj](https://releases.aspose.com/tasks/java/).  
- Podstawową znajomość programowania w Javie.  

## Import Packages
Najpierw zaimportuj niezbędne pakiety do swojego projektu Java:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## Step 1: Load the Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

Tutaj **odczytujemy plik projektu Java** w formacie (`.mpp`) i tworzymy obiekt `Project`, który daje dostęp do wszystkich danych projektu, w tym przydziałów zasobów.

## Step 2: Iterate Through Resource Assignments
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

Ustawiamy **minimalną datę**, aby odfiltrować daty zastępcze, a następnie iterujemy po każdym przydziale. To typowy wzorzec *resource assignment example* używany, gdy trzeba przejrzeć lub zmodyfikować przydziały.

## Step 3: Check Stop and Resume Dates
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

W tym bloku **sprawdzamy datę zatrzymania** i **datę wznowienia** dla każdego przydziału. Jeśli data jest wcześniejsza niż nasz `minDate`, traktujemy ją jako nieustawioną (`"NA"`); w przeciwnym razie wyświetlamy rzeczywistą datę. Ta logika jest niezbędna do **zarządzania przydziałami zasobów** prawidłowo.

## Common Issues and Solutions
- **Null dates** – `ra.get(Asn.STOP)` może zwrócić `null`. Zabezpiecz się przed tym, dodając sprawdzenie null przed wywołaniem `.before(minDate)`.  
- **Incorrect file path** – Upewnij się, że `dataDir` kończy się separatorem ścieżki (`/` lub `\\`) odpowiednim dla twojego systemu operacyjnego.  
- **Version mismatch** – Użyj najnowszej wersji Aspose.Tasks for Java, aby uniknąć brakujących wartości wyliczeniowych.

## FAQ's
### Czy mogę używać Aspose.Tasks bez zainstalowanego Microsoft Project?
Tak, Aspose.Tasks pozwala pracować z plikami Microsoft Project bez konieczności instalacji Microsoft Project na twoim komputerze.

### Gdzie mogę znaleźć więcej dokumentacji?
Szczegółową dokumentację znajdziesz [tutaj](https://reference.aspose.com/tasks/java/).

### Czy dostępna jest darmowa wersja próbna?
Tak, darmową wersję próbną możesz uzyskać [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie, jeśli napotkam problemy?
Wsparcie od społeczności dostępne jest [tutaj](https://forum.aspose.com/c/tasks/15).

### Czy mogę kupić tymczasową licencję?
Tak, tymczasową licencję możesz zakupić [tutaj](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: How do I programmatically set a stop date for an assignment?**  
A: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.

**Q: What happens if the resume date is earlier than the stop date?**  
A: The API does not enforce chronological order; however, the scheduler will treat the assignment as active only after the later of the two dates, so you should validate dates yourself.

**Q: Can I filter assignments to only those that have a stop date set?**  
A: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP) != null`.

**Q: Is it possible to remove a stop date once set?**  
A: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save the project.

**Q: Does Aspose.Tasks support other date‑related fields like start, finish, or actual start?**  
A: Absolutely. The `Asn` enum provides constants for all assignment fields, such as `Asn.START`, `Asn.FINISH`, etc.

## Conclusion
Postępując zgodnie z tymi krokami, teraz wiesz **jak zatrzymać przydział**, sprawdzić daty zatrzymania/wznowienia i wznowić przydział w razie potrzeby. Ta funkcjonalność pozwala **zarządzać przydziałami zasobów** precyzyjniej, szczególnie w sytuacjach takich jak urlopy zasobów czy przestoje sprzętu. Śmiało rozbudowuj przykład, aby aktualizować daty, generować raporty lub integrować go z własną logiką planowania.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}