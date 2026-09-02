---
date: 2026-04-13
description: Zjistěte, jak nastavit pracovní hodiny a spravovat kolekce kalendářů
  v Aspose.Tasks pro .NET. Importujte kalendáře z Microsoft Project, odstraňte kalendář
  projektu a snadno získávejte kalendář podle názvu.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Správa kolekce kalendářů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Nastavte pracovní hodiny v kolekci kalendářů Aspose.Tasks
url: /cs/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení pracovních hodin v kolekci kalendářů Aspose.Tasks

V tomto tutoriálu se naučíte, jak **nastavit pracovní hodiny** a spravovat kolekce kalendářů pomocí Aspose.Tasks pro .NET. Kalendáře definují pracovní dny, svátky a výjimky, takže jejich ovládnutí vám umožní přesně řídit harmonogramy projektů. Také vám ukážeme, jak importovat kalendáře z Microsoft Project, odstranit kalendář z projektu a získat kalendář podle názvu.

## Rychlé odpovědi
- **Jaká je hlavní třída pro kalendáře?** `Project.Calendars` collection.
- **Jak nastavit pracovní hodiny?** Vytvořte nebo upravte objekt `Calendar` a definujte jeho `WorkingTime`.
- **Mohu importovat kalendáře z Microsoft Project?** Ano – načtěte soubor MPP a přistupujte k jeho kalendářům.
- **Jak odstranit kalendář z projektu?** Použijte `Project.Calendars.Remove(calendar)`.
- **Jak získat kalendář podle názvu?** Zavolejte `Project.Calendars.GetByName("YourCalendar")`.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Visual Studio: Nainstalujte Visual Studio nebo jiné kompatibilní IDE pro vývoj v .NET.  
2. Aspose.Tasks pro .NET: Stáhněte a nainstalujte Aspose.Tasks pro .NET z [zde](https://releases.aspose.com/tasks/net/).  
3. Základní znalost C#: Znalost programovacího jazyka C# bude užitečná.

## Importování jmenných prostorů

Nejprve importujme potřebné jmenné prostory pro práci s Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Vytvoření nového kalendáře

### Krok 1: Inicializujte nový objekt `Project`.
```csharp
var project = new Project();
```

### Krok 2: Přidejte kalendáře do kolekce kalendářů projektu.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Krok 3: Projděte kalendáře a zobrazte jejich názvy.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Jak nastavit pracovní hodiny pro kalendář?

Pro **nastavení pracovních hodin** upravíte kolekci `WorkingTime` objektu `Calendar`.  
Například můžete definovat standardní pracovní den od 9 do 17 hodin nebo přidat vlastní výjimky.  
Kód pro toto je stejný jako příklady uvedené níže, když vytváříme standardní kalendář.

## Nahrazení kalendáře novým kalendářem

### Krok 1: Načtěte existující projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Odstraňte existující kalendář (pokud existuje).  
Toto demonstruje scénář **odstranění kalendáře z projektu**.
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

## Získání kalendáře podle názvu nebo ID

### Krok 1: Načtěte projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Získejte kalendáře podle názvu nebo UID.  
Toto ilustruje operaci **získání kalendáře podle názvu**.
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

## Procházení kalendářů

### Krok 1: Načtěte projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Krok 2: Získejte počet kalendářů.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Krok 3: Projděte kolekci kalendářů a zobrazte názvy.
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

### Krok 2: Definujte nový kalendář a nastavte jej jako standardní.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Krok 3: Uložte projekt.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení

- **Kalendář nebyl nalezen při použití `GetByName`** – Ujistěte se, že přesný název odpovídá velikosti písmen použité při přidání kalendáře.  
- **Pracovní hodiny nebyly použity** – Po nastavení `WorkingTime` nezapomeňte projekt uložit; jinak změny zůstanou pouze v paměti.  
- **Import kalendářů z MPP souboru selže** – Ověřte, že zdrojový soubor je platný soubor Microsoft Project a že máte oprávnění ke čtení.

## Často kladené otázky

### Q1: Mohu v Aspose.Tasks vytvořit vlastní pracovní dny?
A1: Ano, můžete vytvořit vlastní pracovní dny přidáním výjimek do kalendářů.

### Q2: Je možné importovat kalendáře ze souborů Microsoft Project?
A2: Rozhodně, Aspose.Tasks podporuje import kalendářů ze souborů Microsoft Project.

### Q3: Jak mohu odstranit konkrétní kalendář z projektu?
A3: Kalendář můžete odstranit tak, že jej získáte z kolekce a poté zavoláte metodu `Remove`.

### Q4: Podporuje Aspose.Tasks export kalendářů do různých formátů?
A4: Ano, Aspose.Tasks umožňuje export kalendářů do různých formátů, jako XML, MPP atd.

### Q5: Mohu přizpůsobit pracovní hodiny pro konkrétní dny v kalendáři?
A5: Samozřejmě, můžete definovat pracovní hodiny pro jednotlivé dny pomocí výjimek v kalendáři.

## Často kladené otázky

**Q: Jaký je nejlepší způsob, jak nastavit kalendář 24‑hodinové směny?**  
A: Vytvořte nový kalendář, vymažte existující položky `WorkingTime` a přidejte jediný rozsah `WorkingTime` od 00:00 do 24:00 pro každý pracovní den.

**Q: Mohu zkopírovat kalendář z jednoho projektu do druhého?**  
A: Ano — exportujte kalendář do XML pomocí `project.Save` a poté jej importujte do jiného projektu pomocí `new Project(xmlPath)`.

**Q: Jak programově importovat kalendáře z Microsoft Project?**  
A: Načtěte soubor MPP pomocí `new Project("source.mpp")`; kalendáře budou dostupné přes `project.Calendars`.

**Q: Existuje limit na počet kalendářů v projektu?**  
A: Prakticky ne; kolekce může obsahovat tolik kalendářů, kolik paměť umožňuje, ale pro výkon udržujte seznam přehledný.

**Q: Aktualizují se změny v kalendáři automaticky u úkolů, které jej používají?**  
A: Ano — úkoly propojené s kalendářem odrážejí aktualizované pracovní časy po uložení projektu.

---

**Poslední aktualizace:** 2026-04-13  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}