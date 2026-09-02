---
date: 2026-04-09
description: Naučte se nastavit standardní kalendář a spravovat svátky projektu ve
  svých .NET projektech pomocí Aspose.Tasks pro přesné plánování.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Nastavte standardní kalendář a řešte výjimky v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Nastavte standardní kalendář a zpracujte výjimky v Aspose.Tasks
url: /cs/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte standardní kalendář a řešte výjimky v Aspose.Tasks

## Úvod

Přesné plánování je základem každého úspěšného projektu a reálné plány často musí odbočit od výchozího pracovního kalendáře kvůli svátkům, zvláštním událostem nebo nečekaným odstávkám. Aspose.Tasks pro .NET usnadňuje nastavení **set standard calendar** a následné přidání vlastních výjimek. V tomto tutoriálu se naučíte, jak načíst kalendář projektu, nastavit standardní kalendář a spravovat svátky projektu pomocí funkce Calendar Exception Collection.

## Rychlé odpovědi
- **Co dělá “set standard calendar”?** Resetuje kalendář na výchozí pracovní dobu (9 AM‑5 PM, pondělí‑pátek) před přidáním vlastních výjimek.  
- **Která metoda vymaže existující výjimky?** `Calendar.Exceptions.Clear()` odstraňuje všechny dříve definované výjimky.  
- **Jak mohu přidat svátek?** Vytvořte `CalendarException` s `DayWorking = false` a přidejte jej do kolekce.  
- **Potřebuji po změnách znovu načíst projekt?** Ne, změny jsou aplikovány přímo na objekt `Project` v paměti.  
- **Jaké knihovny jsou vyžadovány?** Aspose.Tasks pro .NET (libovolná podporovaná verze .NET) a jmenné prostory `System`.

## Předpoklady

Předtím, než se ponoříte do kódu, ujistěte se, že máte:

1. **Aspose.Tasks pro .NET** – stáhněte jej [zde](https://releases.aspose.com/tasks/net/).  
2. Základní znalost **C#** – budete psát několik krátkých úryvků.  
3. Vývojové prostředí jako **Visual Studio** nebo **JetBrains Rider**.

## Importujte jmenné prostory

Tyto `using` direktivy vám poskytují přístup ke třídám potřebným pro manipulaci s kalendářem.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Co je výjimka kalendáře?

*Kalendářová výjimka* představuje období, kdy je normální pracovní rozvrh změněn – například celopodnikový svátek nebo dočasný přesčasový rozvrh. Přidáním výjimek do kalendáře můžete modelovat reálná omezení, aniž byste měnili základní kalendář.

## Jak nastavit standardní kalendář v Aspose.Tasks

Prvním krokem je načíst soubor projektu a získat kalendář, se kterým chcete pracovat.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Krok 1: Vymazat existující výjimky a resetovat na standardní kalendář

Před přidáním nových pravidel je dobré vymazat všechny staré výjimky a nastavit **set standard calendar**. To zajišťuje čistý výchozí stav.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Krok 2: Definovat výjimku pracovní doby

Někdy je potřeba vytvořit dočasný rozvrh (např. prodloužené hodiny pro uvedení produktu na trh). Následující úryvek definuje výjimku pracovní doby, která zahrnuje několik dní a obsahuje dva denní pracovní úseky.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Krok 3: Přidat výjimky nepracovních časů (svátky)

Pro **správu svátků projektu** vytvořte výjimky, kde je `DayWorking` nastaveno na `false`. Níže uvedený příklad přidává dvoudenní blok svátku.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Krok 4: Zobrazit výjimky kalendáře (ověření)

Po přidání výjimek budete často chtít ověřit, že byly zaznamenány správně. Následující smyčka vypíše podrobnosti každé výjimky do konzole.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Krok 5: Odstranit všechny výjimky (úklid)

Pokud potřebujete vrátit kalendář do původního stavu, můžete programově odstranit všechny výjimky.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| Výjimky se neobjevují po uložení | Projekt nebyl po úpravách uložen | Po provedení změn zavolejte `project.Save("output.mpp")`. |
| Překrývající se výjimky způsobují neočekávané pracovní hodiny | Aspose.Tasks používá poslední přidanou výjimku pro překrývající se období | Pečlivě uspořádejte volání `Add` nebo ručně upravte priority. |
| `MakeStandardCalendar` resetuje vlastní pracovní časy | Úmyslně vymaže vlastní časy; po volání je případně přidejte znovu. | Přidejte své vlastní objekty `WorkingTime` po volání `MakeStandardCalendar`. |

## Často kladené otázky

**Q: Mohu přidat více výjimek do jednoho kalendáře?**  
A: Ano, můžete přidat více výjimek do kalendáře pomocí metody `AddRange`.

**Q: Jak mohu řešit opakující se výjimky, například týdenní svátky?**  
A: Můžete programově vypočítat opakující se výjimky a přidat je do kalendáře pomocí vlastní logiky.

**Q: Je možné importovat kalendářové výjimky z externích zdrojů?**  
A: Ano, můžete načíst kalendářové výjimky z externích zdrojů, jako jsou databáze nebo CSV soubory, a integrovat je do svého projektu.

**Q: Co se stane, pokud jsou v kalendáři překrývající se výjimky?**  
A: Aspose.Tasks pro .NET vám umožňuje řešit překrývající se výjimky definováním priorit nebo řešením konfliktů podle požadavků vašeho projektu.

**Q: Mohu přizpůsobit pracovní časy pro každý den ve výjimce?**  
A: Ano, můžete specifikovat vlastní pracovní časy pro jednotlivé dny ve výjimce, aby vyhovovaly konkrétním potřebám plánování.

## Závěr

Nejprve **nastavením standardního kalendáře** a následným přidáním vlastních výjimek získáte plnou kontrolu nad plánováním projektu, což usnadňuje **správu svátků projektu** a jakýchkoli dalších speciálních časových os. Kolekce Calendar Exception v Aspose.Tasks poskytuje čistý programový způsob, jak modelovat reálné kalendáře přímo ve vašich .NET aplikacích.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}