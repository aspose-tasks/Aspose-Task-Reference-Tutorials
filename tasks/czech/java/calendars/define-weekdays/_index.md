---
date: 2025-12-02
description: Naučte se, jak nastavit kalendář, definovat pracovní dny v MS Project
  a nastavit vlastní pracovní dny pomocí Aspose.Tasks pro Javu. Uložte projekt jako
  XML pomocí několika řádků kódu.
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak nastavit kalendář a definovat pracovní dny v MS Project pomocí Aspose.Tasks
url: /cs/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit kalendář a definovat pracovní dny v MS Project pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se dozvíte **jak nastavit kalendář** programově a jak definovat pracovní dny v souboru Microsoft Project pomocí knihovny Aspose.Tasks pro Java. Ať už potřebujete vytvořit standardní pracovní týden, přidat pracovní dny o víkendu nebo nastavit zkrácený páteční rozvrh, tento průvodce vás provede každým krokem – od vytvoření projektu až po uložení souboru jako XML.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Tasks pro Java  
- **Mohu přidat pracovní dny o víkendu?** Ano – stačí přidat sobotu a neděli jako pracovní dny.  
- **Jak uložit projekt?** Použijte `prj.save(..., SaveFileFormat.Xml)`.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkci.  
- **Jaká verze Javy je požadována?** Java 8 nebo vyšší.

## Co znamená „nastavit kalendář“ v kontextu MS Project?
Nastavení kalendáře v MS Project znamená definovat, které dny jsou pracovní, jaké jsou denní pracovní hodiny a jaké výjimky (např. svátky) existují. Tento kalendář řídí plánování úkolů, přidělování zdrojů a celkové časové osy projektu.

## Proč používat Aspose.Tasks pro manipulaci s kalendářem?
- **Plná kontrola** – programově vytvářet, upravovat nebo mazat kalendáře bez otevírání UI.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.  
- **Podporuje všechny formáty souborů** – MPP, MPT a XML, takže můžete *uložit projekt jako XML* pro snadnou integraci s ostatními systémy.  
- **Žádné závislosti na COM** – na rozdíl od knihovny Microsoft Project Interop.

## Předpoklady
1. **Java Development Kit (JDK) 8+** – stáhněte z [webu Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks pro Java** – získejte nejnovější JAR ze [stránky ke stažení Aspose.Tasks](https://releases.aspose.com/tasks/java/).  
3. IDE nebo nástroj pro sestavení (Maven/Gradle) pro přidání Aspose.Tasks JAR do classpath vašeho projektu.

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Tyto importy vám umožní přístup k objektům projektu, kalendáře a pracovního času.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Postupný návod

### Krok 1: Vytvořit instanci projektu
Vytvořte nový objekt `Project`. Tento objekt představuje soubor MS Project, který budete upravovat.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Krok 2: Definovat nový kalendář
Přidejte do projektu nový kalendář. Pojmenování pomáhá, když máte více kalendářů.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Krok 3: Přidat standardní pracovní dny (pondělí‑čtvrtek)
Použijte vestavěný pomocník `WeekDay.createDefaultWorkingDay` pro nastavení výchozího rozvrhu 9 am‑5 pm pro hlavní pracovní týden.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Krok 4: Přidat pracovní dny o víkendu
Pokud váš projekt probíhá i o víkendu, jednoduše přidejte sobotu a neděli jako běžné pracovní dny. Toto ukazuje **přidání pracovních dnů o víkendu**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Krok 5: Nastavit vlastní krátký pracovní den (pátek)
Zde **nastavíme vlastní pracovní dny** pro pátek: ranní směna (9 am‑12 pm) a odpolední směna (1 pm‑4 pm).

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

### Krok 6: Uložit projekt jako XML
Nakonec uložte provedené změny. Volba `SaveFileFormat.Xml` vám umožní **uložit projekt jako XML**, což je užitečné pro integraci s dalšími nástroji.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Pracovní časy nejsou aplikovány** | Ujistěte se, že je na vlastním `WeekDay` voláno `setDayWorking(true)`. |
| **Soubor nebyl při ukládání nalezen** | Ověřte, že `dataDir` ukazuje na existující složku a že má vaše aplikace oprávnění k zápisu. |
| **Kalendář se neprojevuje v úkolech** | Přiřaďte nově vytvořený kalendář zdrojům nebo úkolům pomocí `task.setCalendar(cal)`. |

## Často kladené otázky

**Q: Mohu definovat vlastní nepracovní dny pomocí Aspose.Tasks pro Java?**  
A: Ano. Nastavte vlastnost `DayWorking` na `false` pro libovolný `WeekDay`, který chcete označit jako nepracovní den.

**Q: Jak mohu přidat svátky nebo výjimky platné pro celou společnost?**  
A: Vytvořte objekty `CalendarException`, určete data výjimek a přidejte je do `cal.getExceptions()`.

**Q: Je knihovna kompatibilní se staršími verzemi MS Project?**  
A: Rozhodně. Aspose.Tasks podporuje formáty MPP, MPT a XML napříč různými verzemi Projectu.

**Q: Mohu upravit existující kalendář v importovaném projektu?**  
A: Načtěte projekt pomocí `new Project("existing.mpp")`, získejte požadovaný kalendář, proveďte změny a uložte.

**Q: Zvládá Aspose.Tasks také opakující se úkoly?**  
A: Ano, můžete vytvářet a upravovat opakující se úkoly pomocí třídy `RecurringTask`.

## Závěr
Nyní víte **jak nastavit kalendář** v MS Project, **definovat pracovní dny**, přidat pracovní dny o víkendu a vytvořit zkrácený páteční rozvrh – vše pomocí Aspose.Tasks pro Java. Výsledek můžete uložit jako XML a integrovat kalendářovou logiku do jakéhokoli Java‑založeného řešení pro řízení projektů.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}