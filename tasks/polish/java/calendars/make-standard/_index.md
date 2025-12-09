---
date: 2025-12-03
description: Dowiedz się, jak stworzyć kalendarz w Javie przy użyciu Aspose.Tasks.
  Ten przewodnik krok po kroku pokazuje, jak utworzyć standardowy kalendarz MS Project,
  dodać standardowy kalendarz i skutecznie korzystać z Aspose.Tasks.
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak utworzyć kalendarz – Stwórz standardowy kalendarz w Aspose.Tasks
url: /pl/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kalendarz – Utwórz standardowy kalendarz w Aspose.Tasks

## Wprowadzenie
W tym samouczku nauczysz się **jak utworzyć kalendarz** obiektów dla plików Microsoft Project przy użyciu biblioteki Aspose.Tasks for Java. Przejdziemy przez tworzenie standardowego kalendarza MS Project, ustawienie go jako domyślnego (standardowego) kalendarza oraz zapisanie pliku projektu. Po zakończeniu przewodnika będziesz w stanie zintegrować tworzenie kalendarzy z dowolnym rozwiązaniem do zarządzania projektami opartym na Javie.

## Szybkie odpowiedzi
- **Co oznacza „standardowy kalendarz”?** To domyślna definicja czasu pracy używana przez zadania, które nie określają własnego kalendarza.  
- **Która biblioteka jest wymagana?** Aspose.Tasks for Java (część „jak używać Aspose”).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jaki format pliku jest tworzony?** Plik Microsoft Project oparty na XML (`.xml`).  
- **Jak długo trwa implementacja?** Około 5‑10 minut dla podstawowego kalendarza.

## Co to jest standardowy kalendarz w Microsoft Project?
**Standardowy kalendarz** definiuje domyślne dni robocze i godziny pracy dla projektu. Gdy dodasz standardowy kalendarz, wszystkie zadania, które nie mają przypisanego konkretnego kalendarza, będą korzystać z jego harmonogramu.

## Dlaczego używać Aspose.Tasks do tworzenia kalendarza?
Aspose.Tasks udostępnia czysto‑Java API, które pozwala manipulować plikami Project bez konieczności instalacji Microsoft Project. Dzięki temu jest idealny do automatyzacji po stronie serwera, potoków CI lub dowolnej aplikacji Java, która potrzebuje **tworzyć obiekty kalendarza MS Project** programowo.

## Wymagania wstępne
Before you start, ensure the following are in place:

### Instalacja Java Development Kit (JDK)
Install the latest JDK from the Oracle website or an OpenJDK distribution.

### Biblioteka Aspose.Tasks for Java
Download the library from the [download page](https://releases.aspose.com/tasks/java/). Add the JAR to your project’s classpath.

## Importowanie pakietów
We need only one import for this tutorial:

```java
import com.aspose.tasks.*;
```

## Przewodnik krok po kroku

### Krok 1: Ustaw katalog danych
Define where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).

### Krok 2: Utwórz instancję Project
Instantiate a new, empty Project object that will hold the calendar.

```java
Project project = new Project();
```

### Krok 3: Zdefiniuj i ustaw kalendarz jako standardowy
Add a new calendar named **“My Cal”** and promote it to the standard calendar for the project.

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **Wskazówka:** Metoda `makeStandardCalendar` automatycznie oznacza podany kalendarz jako domyślny dla projektu, co jest dokładnie tym, czego potrzebujesz, gdy chcesz **dodać funkcję standardowego kalendarza**.

### Krok 4: Zapisz projekt
Persist the project (including the new calendar) to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

You can change the file name or format (`SaveFileFormat.Pp`) if you prefer a different Project version.

### Krok 5: Wyświetl komunikat o zakończeniu
Give yourself a visual cue that the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Częste problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **File not found** | `dataDir` wskazuje na nieistniejący folder | Utwórz folder lub użyj ścieżki bezwzględnej |
| **License exception** | Uruchamianie bez ważnej licencji Aspose.Tasks w środowisku produkcyjnym | Zastosuj plik licencji poprzez `License license = new License(); license.setLicense("Aspose.Tasks.lic");` |
| **Empty calendar** | Zapomniano dodać definicje czasu pracy | Użyj `cal1.getWeekDays().add(WeekDay.DayType.Monday)` itd., jeśli potrzebujesz niestandardowych godzin |

## Najczęściej zadawane pytania

**P:** Czy Aspose.Tasks jest kompatybilny ze wszystkimi wersjami Microsoft Project?  
**O:** Tak, Aspose.Tasks obsługuje szeroki zakres wersji Microsoft Project, od 2000 do najnowszych wydań.

**P:** Czy mogę dalej dostosować ustawienia kalendarza?  
**O:** Oczywiście! Możesz modyfikować dni robocze, dodawać wyjątki i definiować konkretne godziny pracy przy użyciu klas `WeekDay` i `WorkingTime`.

**P:** Czy Aspose.Tasks jest odpowiedni dla aplikacji na poziomie przedsiębiorstwa?  
**O:** Zdecydowanie. Biblioteka jest zaprojektowana pod kątem wysokiej wydajności, skalowalnych środowisk i oferuje kompleksowe wsparcie dla dużych plików Project.

**P:** Czy Aspose.Tasks oferuje wsparcie techniczne dla programistów?  
**O:** Tak, Aspose zapewnia dedykowane fora, wsparcie oparte na zgłoszeniach oraz obszerną dokumentację, aby pomóc szybko rozwiązać wszelkie problemy.

**P:** Czy mogę wypróbować Aspose.Tasks przed zakupem?  
**O:** Tak, możesz wypróbować darmową wersję próbną dostępną na [stronie internetowej](https://purchase.aspose.com/buy), co pozwala ocenić wszystkie funkcje przed podjęciem decyzji.

## Zakończenie
Teraz wiesz **jak utworzyć kalendarz** obiektów w Aspose.Tasks dla Javy, ustawić je jako standardowy kalendarz i zapisać powstały plik Project. Ta możliwość pozwala automatyzować harmonogramowanie projektów, wymuszać spójne godziny pracy i integrować dane Microsoft Project bezpośrednio w aplikacjach Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2025-12-03  
**Testowano z:** Aspose.Tasks for Java 24.12  
**Autor:** Aspose  

---