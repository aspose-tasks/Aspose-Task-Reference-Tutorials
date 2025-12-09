---
date: 2025-12-02
description: Dowiedz się, jak dodać kalendarz do projektu, jak utworzyć kalendarz
  MS Project oraz jak zapisać projekt jako XML przy użyciu Aspose.Tasks dla Javy.
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Dodaj kalendarz do projektu przy użyciu Aspose.Tasks dla Javy
url: /pl/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj kalendarz do projektu przy użyciu Aspose.Tasks dla Java

## Introduction
W nowoczesnych przepływach pracy zarządzania projektami możliwość **dodania kalendarza do projektu** programowo może zaoszczędzić godziny ręcznej edycji. Aspose.Tasks for Java daje programistom czyste, typowo‑bezpieczne API do manipulacji plikami Microsoft Project bez konieczności otwierania klienta desktopowego. W tym samouczku nauczysz się **jak dodać kalendarz**, **jak utworzyć kalendarz MS Project**, oraz **zapisać projekt jako XML** — wszystko przy użyciu kilku linii kodu Java.

## Quick Answers
- **Co oznacza „add calendar to project”?**  
  Oznacza to wstawienie nowej definicji czasu pracy (kalendarza) do pliku Microsoft Project za pomocą kodu.  
- **Która biblioteka obsługuje to zadanie?**  
  Aspose.Tasks for Java udostępnia klasę `Calendar` oraz kontener `Project` do zarządzania kalendarzami.  
- **Czy potrzebna jest licencja?**  
  Tymczasowa licencja ewaluacyjna wystarczy do testów; pełna licencja jest wymagana w środowisku produkcyjnym.  
- **Czy mogę zapisać plik jako XML?**  
  Tak — użyj `SaveFileFormat.Xml`, aby wyeksportować projekt jako plik XML.  
- **Jakie są wymagania wstępne?**  
  Java JDK 8+ oraz plik JAR Aspose.Tasks for Java w classpath.

## What is “add calendar to project”?
Dodanie kalendarza do projektu tworzy niestandardowy harmonogram definiujący dni robocze, święta i dzienne godziny pracy. Ten kalendarz może być następnie przypisany do zadań, zasobów lub całego projektu, zapewniając, że obliczenia takie jak daty rozpoczęcia i trwania respektują zdefiniowany czas pracy.

## Why use Aspose.Tasks for Java to add calendar to project?
- **Full control** – brak wymogu interfejsu UI; automatyzacja masowego tworzenia kalendarzy w wielu projektach.  
- **Cross‑version compatibility** – działa z plikami Project 2007, 2010, 2013, 2016 i nowszymi.  
- **No Microsoft Project installation** – uruchamiane na dowolnym serwerze lub w pipeline CI.  
- **Export flexibility** – zapis jako XML, MPP lub inne obsługiwane formaty.

## Prerequisites
- **Java Development Kit (JDK) 8 lub nowszy** zainstalowany i skonfigurowany.  
- **Aspose.Tasks for Java** – pobierz z [official website](https://releases.aspose.com/tasks/java/) i dodaj plik JAR do classpath projektu.  
- IDE lub narzędzie budujące (Maven/Gradle) według własnego wyboru.

## Step‑by‑step guide

### Step 1: Import the required Aspose.Tasks package
First, bring the Aspose.Tasks classes into scope so you can work with projects and calendars.

```java
import com.aspose.tasks.*;
```

### Step 2: Set the data directory path
Define where the generated project file will be written. Replace the placeholder with an absolute or relative path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a new Project instance
Instantiate a `Project` object – this represents an empty Microsoft Project file that you can populate.

```java
Project prj = new Project();
```

### Step 4: Define the calendars you want to add
Use the `Calendars.add(String name)` method to create new calendar entries. In this example we add three calendars, but you can add as many as needed and configure their working times later.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** After adding a calendar, you can customize its working days with `cal1.getWeekDays().add(...)` and set daily work hours using `cal1.getBaseCalendar().setWorkingTime(...)`.

### Step 5: Save the project (save project as XML)
Persist the project, including the newly added calendars, to an XML file. This format is easy to inspect and compatible with many tools.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 6: Display a completion message
Let the user know the operation finished successfully.

```java
System.out.println("Process completed Successfully");
```

By following these six concise steps, you have successfully **added a calendar to a project** and saved the result as an XML file.

## Common Issues and Solutions
| Problem | Przyczyna | Rozwiązanie |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Obiekt projektu nie został poprawnie zainicjowany. | Upewnij się, że wywołano `new Project()` przed dostępem do kalendarzy. |
| **File not found when saving** | `dataDir` wskazuje na nieistniejący folder. | Utwórz katalog najpierw lub użyj ścieżki bezwzględnej. |
| **Calendar name appears as “no info”** | Użyto nazw zastępczych w przykładzie. | Zastąp je znaczącymi nazwami odzwierciedlającymi harmonogram (np. “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | Używana jest przestarzała wersja Aspose.Tasks. | Zaktualizuj do najnowszej wersji Aspose.Tasks for Java. |

## Frequently Asked Questions

**Q: Czy Aspose.Tasks radzi sobie z złożonymi kalendarzami zawierającymi wiele wyjątków?**  
A: Tak – po dodaniu kalendarza możesz definiować wyjątki, godziny pracy i dni wolne, używając klas `WeekDay` i `Exception`.

**Q: Czy można przypisać nowy kalendarz do konkretnych zadań?**  
A: Oczywiście. Pobierz zadanie za pomocą `prj.getRootTask().getChildren().add("Task Name")` i ustaw `task.set(Tsk.CALENDAR, cal3);`.

**Q: Czy biblioteka obsługuje zapisy w innych formatach, takich jak MPP?**  
A: Tak. Zamień `SaveFileFormat.Xml` na `SaveFileFormat.Mpp` lub `SaveFileFormat.P6` w zależności od potrzeb.

**Q: Czy potrzebna jest licencja do wersji deweloperskich?**  
A: Tymczasowa licencja ewaluacyjna wystarczy do testów; pełna licencja jest wymagana w środowisku produkcyjnym.

**Q: Gdzie mogę uzyskać pomoc w razie problemów?**  
A: Forum społeczności Aspose.Tasks jest doskonałym źródłem: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Korzystając z Aspose.Tasks for Java, możesz programowo **dodać kalendarz do projektu**, dostosować reguły harmonogramu i **zapisać projekt jako XML** przy użyciu kilku linii kodu. Automatyzacja ta redukuje ręczną pracę, eliminuje błędy ludzkie i umożliwia przetwarzanie wsadowe dużych portfeli projektów.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}