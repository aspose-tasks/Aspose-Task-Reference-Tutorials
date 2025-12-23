---
date: 2025-12-23
description: Naučte se, jak pomocí Aspose.Tasks pro Javu aktualizovat harmonogram
  projektu, nastavit první den týdne, změnit počet dnů v měsíci a efektivně přizpůsobit
  kalendář projektu.
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: aspose tasks java – Správa vlastností pracovních dnů
url: /cs/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – Správa vlastností pracovních dnů

## Úvod
Aspose.Tasks for Java (aspose tasks java) je robustní API, které umožňuje vývojářům Java pracovat se soubory Microsoft Project, aniž by bylo nutné mít nainstalovaný Microsoft Project. V tomto tutoriálu se naučíte, jak **načíst soubor MPP**, **nastavit první den týdne**, **změnit počet dnů za měsíc** a jinak **přizpůsobit kalendář projektu** – vše jsou nezbytné kroky pro aktualizaci harmonogramu projektu. Na konci budete schopni programově upravit vlastnosti pracovních dnů a uložit změny v požadovaném formátu.

## Rychlé odpovědi
- **Jaká je hlavní třída pro práci s projekty?** `Project` z knihovny Aspose.Tasks.  
- **Jak změním první den týdne?** Použijte `project.set(Prj.WEEK_START_DAY, DayType.Monday)`.  
- **Mohu načíst existující soubor .mpp?** Ano – vytvořte instanci `Project` s cestou k souboru.  
- **Která metoda uloží projekt jako XML?** `project.save(path, SaveFileFormat.Xml)`.  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze stačí pro hodnocení; licence je vyžadována pro produkci.

## Požadavky
Před zahájením se ujistěte, že máte následující:

- **Java Development Kit (JDK)** – nainstalována nejnovější verze.  
- **Aspose.Tasks for Java knihovna** – stáhněte ji [zde](https://releases.aspose.com/tasks/java/).  
- **IDE** jako IntelliJ IDEA, Eclipse nebo NetBeans.  

## Import balíčků
Pro začátek importujte nezbytné třídy Aspose.Tasks:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Nyní projděme jednotlivé kroky správy vlastností pracovních dnů.

## Krok 1: Načtení souboru MPP
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*Zde **načteme existující soubor .mpp** (`load mpp file`), abychom mohli prozkoumat a upravit jeho nastavení kalendáře.*

## Krok 2: Zobrazení aktuálních vlastností pracovních dnů
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Tento kód vypíše aktuální **první den týdne**, **počet dnů za měsíc**, **minuty za den** a **minuty za týden** – základní prvky, které často potřebujete pro **přizpůsobení kalendáře projektu**.

## Krok 3: Nastavení nových vlastností pracovních dnů
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
V tomto kroku **nastavíme první den týdne** na pondělí, **změníme počet dnů za měsíc** na 24 a upravíme počty minut za den a týden. Tato nastavení jsou typická, když potřebujete **aktualizovat harmonogram projektu** tak, aby odpovídal nestandardnímu pracovnímu kalendáři.

## Krok 4: Uložení aktualizovaného projektu
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Upravený projekt je uložen jako XML soubor, což usnadňuje jeho sdílení nebo import do jiných nástrojů.

## Krok 5: Potvrzení operace
```java
System.out.println("Process completed Successfully");
```
Jednoduchá zpráva v konzoli vás informuje, že workflow skončilo bez chyb.

## Časté problémy a tipy
- **Nesprávná cesta k souboru** – Ověřte, že `dataDir` končí lomítkem, nebo použijte `Paths.get(...)` pro platformově nezávislé cesty.  
- **Licence není nastavena** – V produkčním prostředí zavolejte `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` před vytvořením `Project`.  
- **Neočekávaný první den týdne** – Ujistěte se, že používáte správnou hodnotu výčtu `DayType` (např. `DayType.Sunday`).  

## Často kladené otázky

**Q: Může Aspose.Tasks for Java zvládnout složité struktury projektů?**  
A: Ano, Aspose.Tasks for Java poskytuje komplexní podporu pro snadnou práci se složitými strukturami projektů.

**Q: Je Aspose.Tasks for Java kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Ano, Aspose.Tasks for Java podporuje různé verze souborů Microsoft Project, což zajišťuje kompatibilitu napříč platformami.

**Q: Mohu integrovat Aspose.Tasks for Java do svých existujících Java aplikací?**  
A: Ano, Aspose.Tasks for Java nabízí bezproblémové možnosti integrace, což vám umožní vylepšit vaše Java aplikace výkonnými funkcemi pro řízení projektů.

**Q: Poskytuje Aspose.Tasks for Java dokumentaci a podporu?**  
A: Ano, můžete získat rozsáhlou dokumentaci a komunitní podporu pro Aspose.Tasks for Java na jejich [webu](https://releases.aspose.com/).

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks for Java?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks for Java z jejich [webu](https://reference.aspose.com/tasks/java/), abyste si před zakoupením mohli vyzkoušet funkce.

---

**Poslední aktualizace:** 2025-12-23  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}