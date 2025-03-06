---
title: Správa kolekce kalendářů v Aspose.Tasks
linktitle: Správa kolekce kalendářů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně spravovat kolekce kalendářů v Aspose.Tasks for .NET. Vytvářejte, upravujte a manipulujte s kalendáři snadno.
weight: 11
url: /cs/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Správa kolekce kalendářů v Aspose.Tasks

## Úvod

V tomto tutoriálu prozkoumáme, jak spravovat kolekce kalendářů v Aspose.Tasks pro .NET. Kalendáře hrají klíčovou roli v řízení projektů, definují pracovní dny, svátky a výjimky. Aspose.Tasks poskytuje robustní funkce pro manipulaci s kalendáři ve vašich projektech.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Visual Studio: Nainstalujte Visual Studio nebo jakékoli jiné kompatibilní IDE pro vývoj .NET.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro práci s Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Vytvoření nového kalendáře

###  Krok 1: Inicializujte nový`Project` object.
```csharp
var project = new Project();
```

### Krok 2: Přidejte kalendáře do kolekce kalendářů projektu.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Krok 3: Iterujte kalendáře a zobrazte jejich jména.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Nahrazení kalendáře novým kalendářem

### Krok 1: Načtěte existující projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Odeberte existující kalendář (pokud existuje).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Krok 3: Přidejte nový kalendář.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Získání kalendáře podle jména nebo ID

### Krok 1: Načtěte projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Načtěte kalendáře podle jména nebo UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Krok 3: Zobrazte podrobnosti kalendáře.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterace přes kalendáře

### Krok 1: Načtěte projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Načtěte počet kalendářů.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Krok 3: Iterujte kolekci kalendářů a zobrazované názvy.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Vytvoření standardního kalendáře

### Krok 1: Inicializujte nový projekt.
```csharp
var project = new Project();
```

### Krok 2: Definujte nový kalendář a udělejte jej standardním.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Krok 3: Uložte projekt.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Závěr

Správa kolekcí kalendářů v Aspose.Tasks for .NET je nezbytná pro efektivní řízení projektů. S poskytnutými funkcemi můžete efektivně vytvářet, upravovat a manipulovat s kalendáři podle požadavků vašeho projektu.

## FAQ

### Q1: Mohu vytvořit vlastní pracovní dny v Aspose.Tasks?

A1: Ano, můžete vytvořit vlastní pracovní dny přidáním výjimek do kalendářů.

### Q2: Je možné importovat kalendáře ze souborů aplikace Microsoft Project?

Odpověď 2: Aspose.Tasks rozhodně podporuje import kalendářů ze souborů aplikace Microsoft Project.

### Q3: Jak mohu odebrat konkrétní kalendář z projektu?

 A3: Kalendář můžete odebrat tak, že jej získáte z kolekce a poté zavoláte na`Remove` metoda.

### Q4: Podporuje Aspose.Tasks export kalendářů do různých formátů?

A4: Ano, Aspose.Tasks umožňuje export kalendářů do různých formátů, jako je XML, MPP atd.

### Q5: Mohu přizpůsobit pracovní dobu pro konkrétní dny v kalendáři?

A5: Jistě, pracovní dobu pro jednotlivé dny můžete definovat pomocí výjimek v kalendáři.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
