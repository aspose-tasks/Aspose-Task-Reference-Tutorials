---
date: 2026-07-29
description: Naučte se, jak naplánovat nepracovní dny vytvořením projektového kalendáře
  pomocí Aspose.Tasks for Java, definováním výjimek pro pracovní dny a správou plánů
  dovolených.
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Plánování nepracovních dnů – Vytvoření projektového kalendáře Aspose
og_description: Plánujte nepracovní dny pomocí Aspose.Tasks for Java. Naučte se definovat
  pracovní dny, přidávat výjimky kalendáře a efektivně spravovat plány dovolených.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Plánování nepracovních dnů – Vytvoření projektového kalendáře Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: Plánování nepracovních dnů – Vytvoření projektového kalendáře Aspose
url: /cs/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Plánování nepracovních dnů – Vytvoření projektového kalendáře Aspose

### Úvod
Když potřebujete **plánovat nepracovní dny** pro projekt, musíte být schopni modelovat svátky, speciální směny nebo dočasné uzavření přímo v projektovém plánu. Aspose.Tasks pro Java vám poskytuje plnou kontrolu nad definicemi kalendáře, což vám umožní přidávat výjimky, které odrážejí reálné plány. V tomto tutoriálu projdeme přesné kroky k definování pracovních dnů pro kalendářové výjimky, aby vaše projektové časové osy zůstaly přesné a spolehlivé. Na konci také uvidíte, jak to zapadá do širší strategie **plánu nepracovních dnů** pro jakýkoli podnikový projekt.

## Rychlé odpovědi
- **Co znamená “schedule non working days”?**  
  Znamená to použití Aspose.Tasks k vytvoření kalendáře, který označuje konkrétní data jako nepracovní, čímž automaticky ovlivňuje termíny úkolů.  
- **Potřebuji licenci pro spuštění ukázky?**  
  Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Které IDE jsou podporovány?**  
  IntelliJ IDEA, Eclipse, NetBeans nebo jakékoli IDE, které podporuje Java 8+.  
- **Mohu přidat více výjimek do stejného kalendáře?**  
  Ano – můžete přidat libovolný počet objektů `CalendarException` podle potřeby.  
- **Do jakých formátů souborů mohu projekt uložit?**  
  XML, MPP a několik dalších formátů podporovaných Aspose.Tasks.  

## Co je projektový kalendář v Aspose.Tasks?
**Projektový kalendář** je nejvyšší objekt v Aspose.Tasks, který definuje pracovní dny a hodiny pro projekt. Přímo ovlivňuje datum zahájení/ukončení úkolů, přidělení zdrojů a celkové výpočty harmonogramu. Přizpůsobením kalendáře zajistíte, že harmonogram respektuje reálná omezení, jako jsou firemní svátky nebo pravidla práce o víkendu.

## Proč definovat pracovní dny pro kalendářové výjimky?
Definování výjimek pro pracovní dny zajišťuje, že projektový engine považuje tyto dny za nepracovní, čímž zabraňuje automatickému plánování úkolů na ně a udržuje časovou osu v souladu s reálnými omezeními, jako jsou svátky, údržbová okna nebo speciální směnové vzory v celé organizaci.

- **Přesné časové osy:** Úkoly nebudou umístěny na svátky nebo blackout období.  
- **Plánování zdrojů:** Zdroje jsou přidělovány pouze v platných pracovních dnech, čímž se zabraňuje přetížení.  
- **Soulad:** Harmonogramy automaticky dodržují politiku organizace nebo zákonné kalendáře svátků.  

## Plán nepracovních dnů s kalendářovými výjimkami
Když spravujete **plán nepracovních dnů**, obvykle máte hlavní seznam svátků, údržbových oken nebo dalších blackout období. Přidání těchto dat jako objektů `CalendarException` zaručuje, že každý výpočet – ať už jde o analýzu kritické cesty nebo vyrovnání zdrojů – automaticky respektuje tato omezení. Tento přístup eliminuje ruční úpravy dat a snižuje riziko odchylek v harmonogramu.

## Požadavky
Před začátkem se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo novější.  
2. **Aspose.Tasks pro Java** – stáhněte z oficiální [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, NetBeans nebo jakýkoli editor kompatibilní s Java.  

## Jak naplánovat nepracovní dny pomocí kalendářových výjimek
Načtěte svůj projekt, vytvořte vlastní kalendář a přidejte objekty `CalendarException`, které označí požadované pracovní dny jako nepracovní. Tento celý proces lze dokončit během několika jednoduchých kroků a výsledný kalendář automaticky ovlivní veškerou logiku plánování úkolů.

### Průvodce krok za krokem

### Krok 1: Import požadovaných balíčků
Potřebujeme základní třídy Aspose.Tasks a `GregorianCalendar` z Javy pro práci s daty.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Krok 2: Definice adresáře dat
Určete, kam bude vygenerovaný soubor projektu uložen.

```java
String dataDir = "Your Data Directory";
```

### Krok 3: Vytvoření instance projektu
`Project` je hlavní objekt, který obsahuje všechna data projektu, včetně úkolů, zdrojů a kalendářů.

```java
Project project = new Project();
```

### Krok 4: Definice kalendáře
`Calendar` představuje rozvrh pracovních a nepracovních časů v rámci projektu.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Krok 5: Definice výjimky pro pracovní dny
`CalendarException` představuje období, které je v kalendáři označeno jako nepracovní.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Krok 6: Uložení projektu
Uložte projekt, včetně vlastního kalendáře a jeho výjimky, do souboru XML.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Datum výjimek nebylo použito** | Zajistěte `setEnteredByOccurrences(false)` a správné hodnoty `FromDate/ToDate`. |
| **Uložený soubor je prázdný** | Ověřte, že `dataDir` ukazuje na zapisovatelnou složku a název souboru končí na `.xml`. |
| **Kalendář se neprojevuje v plánování úkolů** | Přiřaďte kalendář úkolům nebo zdrojům pomocí `task.setCalendar(cal)` nebo `resource.setCalendar(cal)`. |

## Často kladené otázky

**Q: Mohu definovat více výjimek pro různé pracovní dny ve stejném kalendáři?**  
A: Ano. Přidejte další objekty `CalendarException` do `cal.getExceptions()` pro každé odlišné období nebo pravidlo.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými Java IDE?**  
A: Rozhodně. Knihovna funguje s IntelliJ IDEA, Eclipse, NetBeans a jakýmkoli IDE, které podporuje standardní Java projekty.

**Q: Mohu přizpůsobit typy výjimek jiných než denní výjimky?**  
A: Ano. Použijte `CalendarExceptionType.Weekly`, `Monthly` nebo `Yearly` podle vašich potřeb plánování.

**Q: Jak mohu dynamicky zpracovávat výjimky na základě požadavků projektu?**  
A: Vytvořte objekty výjimek programově – např. načtěte data svátků z databáze nebo konfiguračního souboru a v cyklu vytvořte instance `CalendarException`.

**Q: Je k dispozici zkušební verze pro Aspose.Tasks pro Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Závěr
Po provedení těchto kroků nyní víte, jak **plánovat nepracovní dny** vytvořením projektového kalendáře a definováním výjimek pro pracovní dny, které přesně odrážejí svátky nebo speciální nepracovní období. Správná konfigurace kalendáře je nezbytná pro realistické harmonogramy, přidělování zdrojů a celkový úspěch projektu. Dále můžete prozkoumat připojení vlastního kalendáře k úkolům nebo zdrojům a experimentovat s dalšími typy výjimek, abyste vytvořili komplexní **plán nepracovních dnů** pro jakýkoli projekt.

---

**Poslední aktualizace:** 2026-07-29  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Vytvořit výjimku kalendáře Aspose pro Java](/tasks/java/calendar-exceptions/add-remove/)
- [Jak nastavit kalendář a definovat pracovní dny v MS Project pomocí Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}