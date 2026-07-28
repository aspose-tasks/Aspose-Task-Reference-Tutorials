---
date: 2026-02-05
description: Naučte se, jak určit pracovní dny a vypočítat dobu trvání úkolu extrahováním
  pracovních hodin z kalendářů MS Project pomocí Aspose.Tasks pro Javu.
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Určete pracovní dny a pracovní hodiny pomocí Aspose.Tasks
url: /cs/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Určování pracovních dnů a pracovních hodin pomocí Aspose.Tasks

## Úvod
Správa kalendářů projektů je základní součástí úspěšného plánování projektů. V tomto tutoriálu **určíte pracovní dny** pro libovolný úkol a **extrahujete pracovní hodiny** z kalendáře MS Project pomocí Aspose.Tasks pro Java. Na konci průvodce budete schopni **vypočítat trvání úkolu**, přizpůsobit pracovní hodiny a spolehlivě **načíst soubor MPP** a získat potřebná data. Také uvidíte, jak **číst soubory MS Project** bez nutnosti mít nainstalovaný Microsoft Project, což umožňuje automatizaci na jakékoli platformě.

## Rychlé odpovědi
- **Co znamená „určování pracovních dnů“?** Jedná se o identifikaci kalendářních dat, která jsou považována za pracovní dny pro daný úkol.  
- **Kterou knihovnu mám použít?** Aspose.Tasks pro Java poskytuje plnohodnotné API pro práci se soubory MS Project.  
- **Jak dlouho trvá implementace?** Obvykle 10–15 minut pro základní extrakci.  
- **Potřebuji licenci?** Je k dispozici bezplatná zkušební verze; pro produkční použití je vyžadována komerční licence.  
- **Mohu přizpůsobit pracovní hodiny?** Ano – můžete upravovat kalendáře, přidávat svátky a nastavovat vlastní časové intervaly práce.  

## Co znamená „určování pracovních dnů“?
Když je úkol naplánován, projektový kalendář určuje, které dny jsou pracovní a které ne‑pracovní (víkendy, svátky). Určování pracovních dnů znamená dotazování tohoto kalendáře, abyste přesně věděli, kdy může být práce vykonána, což je nezbytné pro přesné **výpočty trvání úkolu**.

## Proč použít Aspose.Tasks pro získání pracovních hodin?
- **Není potřeba Microsoft Project** – můžete číst soubory MS Project přímo z Java kódu.  
- **Kompletní podpora kalendářů** – zahrnuje výchozí, zdrojové i úkolové kalendáře.  
- **Vysoký výkon** – rychlé zpracování velkých projektů.  
- **Rozsáhlá dokumentace** – příklady a reference API jsou snadno dostupné.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks pro Java** – stáhněte nejnovější JAR z [zde](https://releases.aspose.com/tasks/java/).  
3. Základní znalosti programování v Javě.  

## Import balíčků
Nejprve importujte hlavní jmenný prostor Aspose.Tasks:

```java
import com.aspose.tasks.*;
```

## Jak načíst soubor MPP pomocí Aspose.Tasks?
Načtení projektového souboru je prvním krokem k jakékoli analýze kalendáře. API vám umožní **načíst soubor MPP** jedním řádkem kódu, aniž byste potřebovali uživatelské rozhraní MS Project.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Získání informací o úkolu a kalendáři
Vyberte úkol, který chcete analyzovat, a získejte jeho přiřazený kalendář. Zde **získáte pracovní hodiny** pro úkol:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Definování počátečního a koncového data
Nastavte časové okno, pro které chcete **určovat pracovní dny**. Použití startovního a koncového data úkolu zajistí, že budete hodnotit pouze relevantní období.

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Procházení dat
Projděte každé datum v trvání úkolu. Tento cyklus vám později umožní **přizpůsobit pracovní hodiny**, pokud bude potřeba:

```java
java.util.Calendar tempDate = calStartDate;
```

## Výpočet trvání
Během iterace kontrolujeme, zda je každý den pracovním dnem, sčítáme pracovní hodiny a nakonec vypočítáme trvání úkolu v minutách, hodinách a dnech. Tento krok ukazuje, jak programově **vypočítat pracovní dny** a **vypočítat trvání úkolu**.

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## Jak přizpůsobit pracovní hodiny a svátky
Aspose.Tasks vám umožní upravit časové intervaly pracovního času kalendáře a přidat výjimky, jako jsou svátky. Můžete volat `taskCalendar.addWorkingTime()` nebo `taskCalendar.addException()` a tak přizpůsobit rozvrh podle politiky vaší organizace. To je užitečné, když výchozí rozvrh 9‑5 neodpovídá realitě.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Task returns `null` for calendar** | Ujistěte se, že úkol má skutečně přiřazený kalendář; jinak dědí výchozí kalendář projektu. |
| **Incorrect duration because of holidays** | Ověřte, že svátky jsou definovány v kalendáři úkolu nebo v základním kalendáři projektu. |
| **Time zone mismatch** | Použijte `java.util.TimeZone` k nastavení časové zóny kalendáře podle vašeho systému, pokud je to nutné. |

## Často kladené otázky
### Q: Může Aspose.Tasks pro Java zvládnout složité struktury projektů?
A: Ano, Aspose.Tasks pro Java poskytuje komplexní podporu pro práci se složitými strukturami projektů, včetně úkolů, zdrojů a kalendářů.

### Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?
A: Rozhodně, Aspose.Tasks pro Java podporuje různé verze MS Project, což zajišťuje kompatibilitu napříč různými prostředími.

### Q: Mohu přizpůsobit pracovní hodiny a svátky v projektových kalendářích?
A: Ano, můžete snadno přizpůsobit pracovní hodiny a svátky podle požadavků vašeho projektu pomocí API Aspose.Tasks pro Java.

### Q: Nabízí Aspose.Tasks pro Java podporu a dokumentaci?
A: Ano, Aspose.Tasks pro Java poskytuje rozsáhlou dokumentaci a vyhrazená fóra podpory, která pomáhají vývojářům efektivně využívat jeho funkce.

### Q: Je k dispozici zkušební verze Aspose.Tasks pro Java?
A: Ano, bezplatnou zkušební verzi Aspose.Tasks pro Java získáte [zde](https://releases.aspose.com/).

## Závěr
V tomto průvodci jsme ukázali, jak **určovat pracovní dny**, **získávat pracovní hodiny** a **vypočítat trvání úkolu** z kalendáře MS Project pomocí Aspose.Tasks pro Java. Dodržením výše uvedených kroků můžete automatizovat analýzu rozvrhu, přizpůsobovat kalendáře a udržovat své projektové plány přesné a aktuální. Nyní máte nástroje k **čtení dat MS Project**, **načtení souboru MPP** a provádění přesných výpočtů trvání bez potřeby samotného Microsoft Project.

---

**Last Updated:** 2026-02-05  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}