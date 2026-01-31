---
date: 2026-01-31
description: Naučte se, jak nastavit kalendář v MS Project, definovat pracovní dny
  a nastavit vlastní pracovní dny pomocí Aspose.Tasks pro Javu. Uložte projekt jako
  XML pomocí jen několika řádků kódu.
linktitle: How to Set Calendar MS Project and Define Weekdays with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Jak nastavit kalendář v MS Project a definovat pracovní dny pomocí Aspose.Tasks
url: /cs/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit kalendář MS Project a definovat pracovní dny pomocí Aspose.Tasks

## Úvod
V tomto tutoriálu se dozvíte, jak programově **nastavit kalendář MS Project** a definovat pracovní dny v souboru Microsoft Project pomocí knihovny Aspose.Tasks pro Javuřid vás provede každým krokem – od vytvoření projektu až po **uložení projektu jako XML**.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Tasks for Java  
- **Mohu přidat pracovní dny o víkendu?** Ano – stačí přidat sobotu a neděli jako pracovní dny.  
- **Jak projekt uložit?** Použijte `prj.save(..., SaveFileFormat.Xml)`.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkci.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo vyšší.

## Co je nastavení kalendáře MS Project?
Nastavení kalendáře v MS Project znamená definovat, které dny jsou pracovní, denní pracovní hodiny a případné výjimky, jako jsou svátky. Tento kalendář řídí plánování úkolů, přidělování zdrojů a celkové časové osy projektu.

## Proč nastavit kalendář MS Project pomocí Aspose.Tasks?
- **Plná kontrola** – programově vytvářet, upravovat nebo mazat kalendáře bez otevření uživatelského rozhraní.  
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.  
- **Podporuje všechny formáty souborů** – MPP, MPT a XML, takže můžete *uložit projekt jako XML* pro snadnou integraci s jinými systémy.## Předpoklady
1. **Java Development Kit (JDK) 8+** – stáhněte z [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – získejte nejnovější JAR ze [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. IDE nebo nástroj pro sestavení (Maven/Gradle) pro přidání JAR Aspose.Tasks do classpath vašeho projektu.

## Import balíčků
Nejprve importujte třídy, které budete potřebovat. Tyto importy vám poskytují přístup k objektům projektu, kalendáře a pracovního času.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Průvodce krok za krokem

### Krok 1: Vytvořte instanci projektu
Vytvořte nový objekt `Project`. Tento objekt představuje soubor MS Project, který budete upravovat.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Krok 2: Definujte nový kalendář
Přidejte do projektu nový kalendář. Pojmenování pomáhá, když máte více kalendářů.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Krok 3: Přidejte standardní pracovní dny (pondělí‑čtvrtek)
Použijte vestavěnou pomoc `WeekDay.createDefaultWorkingDay` k nastavení výchozího rozvrhu 9 – 17 hod pro hlavní pracovní týden.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Krok 4: Přidejte pracovní dny o víkendu
Pokud váš projekt běží o víkendech, jednoduše přidejte sobotu a neděli jako běžné pracovní dny. Toto demonstruje **přidání pracovních dnů o víkendu**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Krok 5: Nastavte vlastní krátký pracovní den (pátek)
Zde **nastavujeme vlastní pracovní dny** pro pátek: ranní směna (9 – 12 hod) a odpolední směna (13 – 16 hod).

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

### K změny. Volba `SaveFileFormat což je užitečné pro integraci s dalšími nástroji.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Pracovní časy nebyly použity** | Ujistěte se, že na vlastním `WeekDay` je zavolána metoda `setDayWorking(true)`. |
| **Soubor nebyl při ukládání nalezen** | Ověřte, že `dataDir` ukazuje na existující složku a že má vaše aplikace oprávnění k zápisu. |
| **Kalendář se neprojevuje v úkolech** | Přiřaďte nově vytvořený kalendář zdrojůmtask.setCalendar(cal)`. |

## Často kladené otázky

**Q: Mohu definovat vlastní nepracovní dny pomocí Aspose.Tasks pro Javu?**  
A: Ano. Nastavte vlastnost `DayWorking` na `false` pro libovolný `WeekDay`, který chcete povaky nebo výjimky platné pro celou společnost?**  
A: Vytvořte objekty `CalendarException`, určete data výjimek a přidejte je do `cal.getExceptions()`.

**Q: Je knihovna kompatibilní se staršími Aspose.Tasks podporuje formáty MPP, MPT a XML napříč různými verzemi Projectu.

**Q: Mohu upravit existující kalendář v importovaném projektu?**  
A: Načtějte požadovaný kalendář, proveďte změny a uložte.

**Q: Zvládá Aspose.Tasks také opakující se úkoly?**  
A: Ano, můžete vytvářet a upravovat opakující se úkoly pomocí třídy `RecurringTask`.

## Závěr
Nyní víte, **jak nastavit kalendář MS Project**, **definovat pracovní dny MS Project**, přidat pracovní dny o víkendu a vytvořit krátký páteční rozvrh – vše pomoc. Uložte výsledek jako XML a integrujte logiku kalendáře do jakéhokoli řešení pro řízení projektů založeného na Javě.

---

**Poslední aktualizace:** 2026Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}