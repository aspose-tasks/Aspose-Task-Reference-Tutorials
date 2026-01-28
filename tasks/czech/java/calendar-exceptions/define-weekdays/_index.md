---
date: 2026-01-28
description: Naučte se, jak vytvořit projektový kalendář v Aspose, definovat pracovní
  dny pro výjimky v kalendáři a spravovat rozvrh nepracovních dnů pomocí Aspose.Tasks
  pro Javu.
linktitle: Create Project Calendar Aspose – Define Weekdays for Calendar Exceptions
second_title: Aspose.Tasks Java API
title: Vytvořit kalendář projektu Aspose – Definovat pracovní dny pro výjimky kalendáře
url: /cs/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření projektového kalendáře Aspose – Definování pracovních dnů pro výjimky v kalendáři

### Introduction
Když potřebujete **create project calendar aspose**, musíte být schopni modelovat nestandardní pracovní dny, jako jsou svátky, speciální směny nebo dočasné uzavírky. Aspose.Tasks pro Java vám poskytuje plnou kontrolu nad definicemi kalendářů, což vám umožní přidávat výjimky, které odrážejí reálné plány. V tomto tutoriálu projdeme přesné kroky k definování pracovních dnů pro výjimky v kalendáři, aby vaše projektové časové osy zůstaly přesné a spolehlivé. Na konci také uvidíte, jak to zapadá do širší strategie **non‑working days schedule** pro jakýkoli podnikoví projekt.

## Quick Answers
- **Co znamená “create project calendar aspose”?**  
  Odkazuje na použití Aspose.Tasks k vytvoření vlastního kalendářového objektu, který řídí plánování úkolů.
- **Potřebuji licenci pro spuštění ukázky?**  
  Pro vývoj stačí bezplatná zkušební verze; pro produkci je vyžadována komerční licence.
- **Jaká IDE jsou podporována?**  
  IntelliJ IDEA, Eclipse, NetBeans nebo jakékoli IDE podporující Java 8+.
- **Mohu přidat více výjimek do stejného kalendáře?**  
  Ano – můžete přidat libovolný počet objektů `CalendarException`.
- **Do jakých formátů mohu projekt uložit?**  
  XML, MPP a několik dalších formátů podporovaných Aspose.Tasks.

## What is a Project Calendar in Aspose.Tasks?
Projektový kalendář definuje pracovní dny a hodiny pro projekt. Ovlivňuje datum zahájení/ukončení úkolů, přidělování zdrojů a celkové výpočty harmonogramu. Přizpůsobením kalendáře zajistíte, že plán respektuje reálná omezení, jako jsou firemní svátky nebo politika práce o víkendech.

## Why define weekdays for calendar exceptions?
- **Přesné časové osy:** Úkoly nebudou naplánovány na dny označené jako nepracovní.
- **Plánování zdrojů:** Zdroje jsou přidělovány pouze v platných pracovních dnech.
- **Soulad:** Harmonogramy projektů jsou v souladu s firemními politikami nebo zákonnými svátky.

## Non‑working Days Schedule with Calendar Exceptions
Pokud spravujete **non‑working days schedule**, obvykle máte hlavní seznam svátků, údržbových oken nebo jiných blackout období. Přidáním těchto dat jako objektů `CalendarException` zajistíte, že každý výpočet – ať už jde o analýzu kritické cesty nebo vyrovnání zdrojů – automaticky respektuje tato omezení. Tento přístup eliminuje ruční úpravy dat a snižuje riziko odchylek v harmonogramu.

## Prerequisites
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější.  
2. **Aspose.Tasks for Java** – stáhněte z oficiální [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli editor kompatibilní s Javou.  

## How to create project calendar aspose – Define weekdays for calendar exceptions

### Step‑by‑Step Guide

### Step 1: Import Required Packages
Potřebujeme základní třídy Aspose.Tasks a Java `GregorianCalendar` pro práci s daty.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Step 2: Define the Data Directory
Určete, kam bude vygenerovaný soubor projektu uložen.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a Project Instance
Vytvořte novou instanci objektu `Project` – jedná se o kontejner pro všechna projektová data, včetně kalendářů.

```java
Project project = new Project();
```

### Step 4: Define a Calendar
Přidejte do projektu vlastní kalendář. Tento kalendář bude obsahovat naše výjimky.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Step 5: Define Weekdays Exception
Vytvořte `CalendarException`, který označí rozsah dnů (např. poslední týden prosince) jako nepracovní.  
Příklad nastavuje výjimku od **24 Dec 2009** do **31 Dec 2009**, zakazuje práci v těchto dnech a považuje výjimku za denní typ.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Step 6: Save the Project
Uložte projekt, včetně vlastního kalendáře a jeho výjimky, do souboru XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Problém | Řešení |
|---------|--------|
| **Datumy výjimek nejsou aplikovány** | Ujistěte se, že je voláno `setEnteredByOccurrences(false)` a že hodnoty `FromDate/ToDate` jsou správné. |
| **Uložený soubor je prázdný** | Ověřte, že `dataDir` ukazuje na zapisovatelnou složku a že název souboru končí na `.xml`. |
| **Kalendář se nepromítá do plánování úkolů** | Přiřaďte kalendář úkolům nebo zdrojům pomocí `task.setCalendar(cal)` nebo `resource.setCalendar(cal)`. |

## Frequently Asked Questions

**Q: Mohu definovat více výjimek pro různé pracovní dny ve stejném kalendáři?**  
A: Ano. Přidejte další objekty `CalendarException` do `cal.getExceptions()` pro každé samostatné období nebo pravidlo.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými Java IDE?**  
A: Rozhodně. Knihovna funguje s IntelliJ IDEA, Eclipse, NetBeans a jakýmkoli IDE, které podporuje standardní Java projekty.

**Q: Mohu přizpůsobit typy výjimek jiných než denní výjimky?**  
A: Ano. Použijte `CalendarExceptionType.Weekly`, `Monthly` nebo `Yearly` podle vašich potřeb plánování.

**Q: Jak mohu dynamicky zpracovávat výjimky na základě požadavků projektu?**  
A: Vytvářejte objekty výjimek programově – např. načtěte data svátků z databáze nebo konfiguračního souboru a v cyklu vytvořte instance `CalendarException`.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi ze [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusion
Po provedení těchto kroků nyní víte, jak **create project calendar aspose** a definovat výjimky pracovních dnů, které přesně odrážejí svátky nebo speciální nepracovní období. Správná konfigurace kalendáře je nezbytná pro realistické harmonogramy, přidělování zdrojů a celkový úspěch projektu. Dále můžete připojit vlastní kalendář k úkolům nebo zdrojům a experimentovat s dalšími typy výjimek a vytvořit tak komplexní **non‑working days schedule** pro jakýkoli projekt.

---

**Last Updated:** 2026-01-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}