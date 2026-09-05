---
date: 2026-08-08
description: Naučte se, jak nastavit kalendář MS Project, nastavit denní pracovní
  dobu a přidat víkendové pracovní dny pomocí Aspose.Tasks pro Java. Uložte projekt
  jako XML během několika řádků kódu.
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: Jak nastavit kalendář MS Project a definovat pracovní dny
og_description: Nastavte kalendář MS Project, definujte pracovní dny a přidejte víkendové
  pracovní dny pomocí Aspose.Tasks pro Java. Postupujte podle tohoto krok‑za‑krokem
  tutoriálu a uložte jako XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Nastavte kalendář MS Project pomocí Aspose.Tasks – průvodce pro Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: Jak nastavit kalendář MS Project a definovat pracovní dny
url: /cs/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit kalendář ms project a definovat pracovní dny

V tomto tutoriálu se naučíte **jak nastavit kalendář ms project** programově, definovat pracovní dny a nakonfigurovat vlastní pracovní dny pomocí knihovny Aspose.Tasks pro Java. Ať už vytváříte plánovací engine, integrujete se systémy ERP, nebo jednoduše potřebujete vygenerovat projektový plán bez otevření Microsoft Project, níže uvedené kroky vám ukážou, jak vytvořit kalendář, nastavit denní pracovní hodiny a přidat víkendové pracovní dny v několika řádcích kódu.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Tasks for Java.  
- **Mohu přidat víkendové pracovní dny?** Ano – stačí označit sobotu a neděli jako pracovní dny.  
- **Jak uložit projekt?** Zavolejte `prj.save(..., SaveFileFormat.Xml)`.  
- **Je potřeba licence?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkční použití.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší.

## Co je nastavení kalendáře ms project?
Nastavení kalendáře v MS Project určuje, které dny jsou považovány za pracovní dny, počet pracovních hodin každý den a jakékoli speciální výjimky, jako jsou svátky nebo celopodnikové uzavření. Tyto informace řídí plánování úkolů, alokaci zdrojů a celkové časové osy projektu, čímž zajišťují, že výpočty respektují skutečné pracovní vzorce organizace.

## Proč používat Aspose.Tasks pro manipulaci s kalendářem?
Aspose.Tasks vám poskytuje programatickou kontrolu nad kalendáři bez spouštění uživatelského rozhraní Microsoft Project. Běží na jakémkoli operačním systému, který podporuje Javu, podporuje více než 50 vstupních a výstupních formátů a dokáže zpracovat projekty o stovkách stránek, aniž by načítal celý soubor do paměti, což z něj činí ideální řešení pro server‑side automatizaci.

## Předpoklady
- **Java Development Kit (JDK) 8+** – stáhněte z [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – získejte nejnovější JAR ze [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- IDE nebo nástroj pro sestavení (Maven/Gradle) pro přidání Aspose.Tasks JAR do classpathu.

## Import balíčků
Importujte třídy, které poskytují přístup k projektům, kalendářům a objektům pracovního času.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Průvodce krok za krokem

### Krok 1: vytvořit instanci projektu
Vytvořte objekt `Project`, který představuje soubor MS Project, který budete upravovat.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Krok 2: definovat nový kalendář
`Calendar` představuje sadu pracovních časů, výjimek a svátků pro projekt.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Krok 3: přidat standardní pracovní dny (pondělí‑čtvrtek)
`WeekDay` definuje pracovní čas pro konkrétní den v týdnu.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Krok 4: přidat víkendové pracovní dny
Pokud váš projekt běží o víkendech, přidejte sobotu a neděli jako běžné pracovní dny. Toto demonstruje **přidání víkendových pracovních dnů**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Krok 5: nastavit vlastní krátký pracovní den (pátek)
Nakonfigurujte pátek s ranní směnou (9 – 12) a odpolední směnou (13 – 16), aby se ilustrovalo **nastavení denních pracovních hodin** a vlastní krátký pracovní den.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Krok 6: uložit projekt jako XML
`SaveFileFormat` vyjmenovává podporované formáty souborů při ukládání projektu, jako je XML nebo MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Pracovní časy nebyly použity** | Ujistěte se, že `setDayWorking(true)` je voláno pro každý vlastní `WeekDay`. |
| **Soubor nebyl při ukládání nalezen** | Ověřte, že `dataDir` ukazuje na existující složku a že aplikace má oprávnění k zápisu. |
| **Kalendář se neprojevuje v úkolech** | Přiřaďte nově vytvořený kalendář zdrojům nebo úkolům pomocí `task.setCalendar(cal)`. |

## Často kladené otázky

**Q: Mohu definovat vlastní nepracovní dny pomocí Aspose.Tasks pro Javu?**  
A: Ano. Nastavte vlastnost `DayWorking` na `false` pro libovolný `WeekDay`, který chcete považovat za nepracovní den.

**Q: Jak mohu přidat svátky nebo celopodnikové výjimky?**  
A: Vytvořte objekty `CalendarException`, určete data výjimek a přidejte je do `cal.getExceptions()`.

**Q: Je knihovna kompatibilní se staršími verzemi MS Project?**  
A: Rozhodně. Aspose.Tasks podporuje formáty MPP, MPT a XML napříč různými verzemi Projectu.

**Q: Mohu upravit existující kalendář v importovaném projektu?**  
A: Načtěte projekt pomocí `new Project("existing.mpp")`, získejte požadovaný kalendář, proveďte změny a uložte.

**Q: Zvládá Aspose.Tasks také opakující se úkoly?**  
A: Ano, můžete vytvářet a upravovat opakující se úkoly pomocí třídy `RecurringTask`.

## Závěr
Nyní víte **jak nastavit kalendář ms project**, definovat pracovní dny, přidat víkendové pracovní dny a nakonfigurovat krátký páteční rozvrh — vše pomocí Aspose.Tasks pro Javu. Uložte výsledek jako XML a integrujte logiku kalendáře do jakéhokoli řešení pro řízení projektů založeného na Javě.

---

**Poslední aktualizace:** 2026-08-08  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose

## Související tutoriály

- [Přidat kalendář do projektu pomocí Aspose.Tasks pro Java](/tasks/java/calendars/create/)
- [Určit pracovní dny a pracovní hodiny pomocí Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Přidat svátky do kalendáře a uložit jako MPP pomocí Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}