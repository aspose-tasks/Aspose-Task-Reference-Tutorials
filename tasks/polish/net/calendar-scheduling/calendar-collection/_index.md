---
title: Zarządzanie kolekcją kalendarzy w Aspose.Tasks
linktitle: Zarządzanie kolekcją kalendarzy w Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Dowiedz się, jak efektywnie zarządzać kolekcjami kalendarzy w Aspose.Tasks dla .NET. Z łatwością twórz, modyfikuj i manipuluj kalendarzami.
weight: 11
url: /pl/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzanie kolekcją kalendarzy w Aspose.Tasks

## Wstęp

W tym samouczku omówimy, jak zarządzać kolekcjami kalendarzy w Aspose.Tasks dla .NET. Kalendarze odgrywają kluczową rolę w zarządzaniu projektami, definiując dni robocze, święta i wyjątki. Aspose.Tasks zapewnia solidną funkcjonalność do manipulowania kalendarzami w projektach.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. Visual Studio: Zainstaluj Visual Studio lub dowolne inne kompatybilne IDE do programowania .NET.
2.  Aspose.Tasks dla .NET: Pobierz i zainstaluj Aspose.Tasks dla .NET z[Tutaj](https://releases.aspose.com/tasks/net/).
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie korzystna.

## Importuj przestrzenie nazw

Najpierw zaimportujmy niezbędne przestrzenie nazw do pracy z Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Tworzenie nowego kalendarza

###  Krok 1: Zainicjuj nowy`Project` object.
```csharp
var project = new Project();
```

### Krok 2: Dodaj kalendarze do kolekcji kalendarzy projektu.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Krok 3: Przeglądaj kalendarze i wyświetl ich nazwy.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Zastąpienie kalendarza nowym kalendarzem

### Krok 1: Załaduj istniejący projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Usuń istniejący kalendarz (jeśli istnieje).
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

## Pobieranie kalendarza według nazwy lub identyfikatora

### Krok 1: Załaduj projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Pobierz kalendarze według nazwy lub UID.
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

### Krok 3: Wykonaj iterację po kolekcji kalendarzy i nazwach wyświetlanych.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Tworzenie standardowego kalendarza

### Krok 1: Zainicjuj nowy projekt.
```csharp
var project = new Project();
```

### Krok 2: Zdefiniuj nowy kalendarz i uczyń go standardem.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Krok 3: Zapisz projekt.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Wniosek

Zarządzanie kolekcjami kalendarzy w Aspose.Tasks dla .NET jest niezbędne do efektywnego zarządzania projektami. Dzięki dostarczonym funkcjom możesz efektywnie tworzyć, modyfikować i manipulować kalendarzami zgodnie z wymaganiami projektu.

## Często zadawane pytania

### P1: Czy mogę tworzyć niestandardowe dni robocze w Aspose.Tasks?

Odpowiedź 1: Tak, możesz tworzyć niestandardowe dni robocze, dodając wyjątki do kalendarzy.

### P2: Czy można importować kalendarze z plików Microsoft Project?

Odpowiedź 2: Oczywiście, Aspose.Tasks obsługuje importowanie kalendarzy z plików Microsoft Project.

### P3: Jak mogę usunąć konkretny kalendarz z projektu?

 Odpowiedź 3: Możesz usunąć kalendarz, pobierając go z kolekcji, a następnie wywołując metodę`Remove` metoda.

### P4: Czy Aspose.Tasks obsługuje eksportowanie kalendarzy do różnych formatów?

O4: Tak, Aspose.Tasks umożliwia eksportowanie kalendarzy do różnych formatów, takich jak XML, MPP itp.

### P5: Czy mogę dostosować godziny pracy dla poszczególnych dni w kalendarzu?

Odp.5: Oczywiście można zdefiniować godziny pracy dla poszczególnych dni korzystając z wyjątków w kalendarzu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
