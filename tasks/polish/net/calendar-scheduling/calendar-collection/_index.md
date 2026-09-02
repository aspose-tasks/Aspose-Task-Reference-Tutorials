---
date: 2026-04-13
description: Dowiedz się, jak ustawiać godziny pracy i zarządzać kolekcjami kalendarzy
  w Aspose.Tasks dla .NET. Importuj kalendarze z Microsoft Project, usuń kalendarz
  projektu i łatwo pobierz kalendarz po nazwie.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Zarządzanie kolekcją kalendarzy w Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ustaw godziny pracy w kolekcji kalendarzy Aspose.Tasks
url: /pl/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw godziny pracy w kolekcji kalendarzy Aspose.Tasks

W tym samouczku dowiesz się, jak **ustawić godziny pracy** i zarządzać kolekcjami kalendarzy przy użyciu Aspose.Tasks dla .NET. Kalendarze definiują dni robocze, święta i wyjątki, więc ich opanowanie pozwala precyzyjnie kontrolować harmonogramy projektów. Pokażemy również, jak importować kalendarze z Microsoft Project, usunąć kalendarz z projektu oraz pobrać kalendarz po nazwie.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa dla kalendarzy?** Kolekcja `Project.Calendars`.
- **Jak ustawić godziny pracy?** Utwórz lub zmodyfikuj obiekt `Calendar` i zdefiniuj jego `WorkingTime`.
- **Czy mogę importować kalendarze z Microsoft Project?** Tak – załaduj plik MPP i uzyskaj dostęp do jego kalendarzy.
- **Jak usunąć kalendarz z projektu?** Użyj `Project.Calendars.Remove(calendar)`.
- **Jak pobrać kalendarz po nazwie?** Wywołaj `Project.Calendars.GetByName("YourCalendar")`.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Visual Studio: Zainstaluj Visual Studio lub inne kompatybilne IDE do programowania w .NET.  
2. Aspose.Tasks for .NET: Pobierz i zainstaluj Aspose.Tasks for .NET z [tutaj](https://releases.aspose.com/tasks/net/).  
3. Podstawowa znajomość C#: Znajomość języka programowania C# będzie przydatna.

## Importowanie przestrzeni nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw do pracy z Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Tworzenie nowego kalendarza

### Krok 1: Zainicjalizuj nowy obiekt `Project`.
```csharp
var project = new Project();
```

### Krok 2: Dodaj kalendarze do kolekcji kalendarzy projektu.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Krok 3: Przejdź przez kalendarze i wyświetl ich nazwy.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Jak ustawić godziny pracy dla kalendarza?

Aby **ustawić godziny pracy**, modyfikujesz kolekcję `WorkingTime` obiektu `Calendar`.  
Na przykład możesz zdefiniować standardowy dzień pracy od 9 do 17 lub dodać własne wyjątki.  
Kod dla tego jest identyczny z przykładami pokazanymi później, gdy tworzymy standardowy kalendarz.

## Zastępowanie kalendarza nowym kalendarzem

### Krok 1: Załaduj istniejący projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Usuń istniejący kalendarz (jeśli istnieje).  
To demonstruje scenariusz **usuwania kalendarza z projektu**.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Krok 3: Dodaj nowy kalendarz.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Pobieranie kalendarza po nazwie lub ID

### Krok 1: Załaduj projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Pobierz kalendarze po nazwie lub UID.  
To ilustruje operację **pobierania kalendarza po nazwie**.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Krok 3: Wyświetl szczegóły kalendarza.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterowanie po kalendarzach

### Krok 1: Załaduj projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Pobierz liczbę kalendarzy.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Krok 3: Przejdź po kolekcji kalendarzy i wyświetl ich nazwy.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Tworzenie standardowego kalendarza

### Krok 1: Zainicjalizuj nowy projekt.
```csharp
var project = new Project();
```

### Krok 2: Zdefiniuj nowy kalendarz i ustaw go jako standardowy.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Krok 3: Zapisz projekt.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Częste problemy i rozwiązania

- **Kalendarz nie został znaleziony przy użyciu `GetByName`** – Upewnij się, że dokładna nazwa jest zgodna z wielkością liter używaną przy dodawaniu kalendarza.  
- **Godziny pracy nie zostały zastosowane** – Po ustawieniu `WorkingTime` pamiętaj, aby zapisać projekt; w przeciwnym razie zmiany pozostaną tylko w pamięci.  
- **Importowanie kalendarzy z pliku MPP nie powiodło się** – Sprawdź, czy plik źródłowy jest prawidłowym plikiem Microsoft Project i czy masz uprawnienia do odczytu.

## FAQ

### P1: Czy mogę tworzyć własne dni robocze w Aspose.Tasks?

O1: Tak, możesz tworzyć własne dni robocze, dodając wyjątki do kalendarzy.

### P2: Czy można importować kalendarze z plików Microsoft Project?

O2: Oczywiście, Aspose.Tasks obsługuje importowanie kalendarzy z plików Microsoft Project.

### P3: Jak mogę usunąć konkretny kalendarz z projektu?

O3: Możesz usunąć kalendarz, pobierając go z kolekcji, a następnie wywołując metodę `Remove`.

### P4: Czy Aspose.Tasks obsługuje eksportowanie kalendarzy do różnych formatów?

O4: Tak, Aspose.Tasks umożliwia eksportowanie kalendarzy do różnych formatów, takich jak XML, MPP itp.

### P5: Czy mogę dostosować godziny pracy dla konkretnych dni w kalendarzu?

O5: Oczywiście, możesz definiować godziny pracy dla poszczególnych dni, używając wyjątków w kalendarzu.

## Najczęściej zadawane pytania

**Q: Jaki jest najlepszy sposób ustawienia kalendarza zmiany 24‑godzinnej?**  
A: Utwórz nowy kalendarz, wyczyść istniejące wpisy `WorkingTime` i dodaj pojedynczy zakres `WorkingTime` od 00:00 do 24:00 dla każdego dnia roboczego.

**Q: Czy mogę skopiować kalendarz z jednego projektu do drugiego?**  
A: Tak — wyeksportuj kalendarz do XML używając `project.Save`, a następnie zaimportuj go do innego projektu za pomocą `new Project(xmlPath)`.

**Q: Jak programowo importować kalendarze z Microsoft Project?**  
A: Załaduj plik MPP przy użyciu `new Project("source.mpp")`; kalendarze będą dostępne poprzez `project.Calendars`.

**Q: Czy istnieje limit liczby kalendarzy w projekcie?**  
A: Praktycznie nie; kolekcja może pomieścić tyle kalendarzy, ile pozwala pamięć, ale warto utrzymać listę w rozsądnych granicach dla wydajności.

**Q: Czy zmiany w kalendarzu automatycznie aktualizują zadania, które go używają?**  
A: Tak — zadania powiązane z kalendarzem odzwierciedlają zaktualizowane godziny pracy po zapisaniu projektu.

---

**Ostatnia aktualizacja:** 2026-04-13  
**Testowano z:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}