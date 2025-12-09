---
date: 2025-12-04
description: Dowiedz się, jak ustawić kalendarz projektu i zarządzać właściwościami
  kalendarza MS Project w Javie przy użyciu Aspose.Tasks. Przewodnik krok po kroku,
  jak wyświetlić godziny pracy kalendarza i dostosować harmonogramy.
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak ustawić kalendarz projektu w Aspose.Tasks dla Javy
url: /pl/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kalendarz projektu przy użyciu Aspose.Tasks dla Javy

## Introduction
W tym samouczku dowiesz się, **jak ustawić kalendarz projektu** programowo przy użyciu biblioteki Aspose.Tasks dla Javy. Kontrolowanie właściwości kalendarza pozwala **wyświetlać godziny pracy kalendarza**, definiować niestandardowe dni robocze i dopasować harmonogram projektu do rzeczywistych ograniczeń. Przejdziemy przez każdy krok — od konfiguracji środowiska po iterację po kalendarzach i odczyt ich właściwości — abyś mógł pewnie zarządzać kalendarzami MS Project w swoich aplikacjach.

## Quick Answers
- **Co oznacza „ustawienie kalendarza projektu”?** Oznacza to tworzenie lub aktualizację godzin pracy kalendarza, kalendarza bazowego i typów dni w pliku MS Project.  
- **Która biblioteka jest wymagana?** Aspose.Tasks for Java (dowolna aktualna wersja).  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę wyświetlić godziny pracy kalendarza?** Tak — odczytując każdy `WeekDay` możesz wypisać godziny dla każdego typu dnia.  
- **Czy jest to kompatybilne z Maven/Gradle?** Oczywiście — dodaj plik JAR Aspose.Tasks jako zależność.

## What Is a Project Calendar?
Kalendarz projektu definiuje dni robocze i godziny pracy dla zadań, zasobów oraz całego harmonogramu projektu. W MS Project kalendarze mogą dziedziczyć po kalendarzu bazowym, a każdy typ dnia (np. **Standard**, **Non‑working**) może mieć własny czas pracy. Zarządzanie tymi ustawieniami programowo umożliwia dynamiczne dostosowywanie harmonogramu bez ręcznej edycji.

## Why Manage MS Project Calendar Programmatically?
- **Automatyzacja:** Dostosowywanie kalendarzy w wielu projektach za pomocą jednego skryptu.  
- **Spójność:** Egzekwowanie polityk czasu pracy obowiązujących w całej organizacji.  
- **Integracja:** Synchronizacja kalendarzy z zewnętrznymi systemami (HR, ERP).  
- **Widoczność:** Szybkie **wyświetlanie godzin pracy kalendarza** w raportach lub podczas debugowania.

## Prerequisites
Before you start, make sure you have:

- **Java Development Kit (JDK) 8+** installed and `JAVA_HOME` configured.  
- **Aspose.Tasks for Java** library downloaded from the [download page](https://releases.aspose.com/tasks/java/). Add the JAR to your project's classpath or Maven/Gradle dependencies.  

## Import Packages
First, import the core Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives us access to all calendars stored in the file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: Iterate Through Calendars and Display Working Hours
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar** values and also how to **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Calendar is a base calendar itself (`isBaseCalendar()` returns `true`). | Use the ternary check as shown (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | The project file uses a different time unit (ticks). | Verify the file format; Aspose.Tasks normalizes to milliseconds, but ensure you’re loading the correct file type. |
| Unable to locate `project.xml` | Incorrect `dataDir` path. | Use an absolute path or `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Czy mogę modyfikować właściwości kalendarza programowo przy użyciu Aspose.Tasks?**  
A: Tak, API zapewnia pełny dostęp do odczytu i zapisu kalendarzy, umożliwiając dodawanie, edytowanie lub usuwanie godzin pracy, wyjątków i relacji kalendarza bazowego.

**Q: Czy istnieją ograniczenia w dostosowywaniu kalendarza przy użyciu Aspose.Tasks?**  
A: Biblioteka odzwierciedla możliwości Microsoft Project, więc możesz dostosować praktycznie wszystkie aspekty kalendarza. Jedynie bardzo stare wersje plików Project mogą mieć drobne niezgodności.

**Q: Czy mogę zintegrować zarządzanie kalendarzem z istniejącymi projektami Java?**  
A: Oczywiście. Wystarczy dodać plik JAR Aspose.Tasks do ścieżki kompilacji i używać tych samych wzorców kodu, które pokazano w tym samouczku.

**Q: Czy Aspose.Tasks obsługuje inne funkcjonalności zarządzania projektami poza zarządzaniem kalendarzem?**  
A: Tak, obejmuje zadania, zasoby, przydziały, struktury, linie bazowe i wiele więcej — co czyni go kompleksowym rozwiązaniem do automatyzacji projektów w Javie.

**Q: Czy dostępne jest wsparcie techniczne dla deweloperów korzystających z Aspose.Tasks?**  
A: Tak, Aspose zapewnia dedykowane fora, wsparcie e‑mailowe oraz obszerną dokumentację dla wszystkich licencjonowanych użytkowników.

## Conclusion
By following this guide you now know **how to set project calendar** values, read and **display calendar working hours**, and integrate these capabilities into any Java application using Aspose.Tasks. This empowers you to automate schedule adjustments, enforce consistent working policies, and build richer project‑management solutions.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}